### NAMA : Sapta Adzani Purnama
### NRP : 3123521014
### Prodi : D3 Teknik Informatika-LA
### KELAS : A

# dining problem dan reader writer problem

## Dining Problem
#### Dining Problem adalah masalah klasik dalam ilmu komputer yang menggambarkan sinkronisasi dan deadlock dalam sistem konkuren. Diperkenalkan oleh Edsger Dijkstra pada tahun 1965, masalah ini menggambarkan situasi di mana lima filsuf duduk di meja bundar dengan satu piring spaghetti di depan masing-masing. Ada garpu di antara setiap dua filsuf, dan setiap filsuf membutuhkan dua garpu untuk makan.
### Solusi dengan Sinkronisasi
#### Salah satu solusi sederhana menggunakan mutex dan semaphores:

     #include <pthread.h>
     #include <semaphore.h>
     #include <stdio.h>
     #include <unistd.h>

     #define N 5

     sem_t forks[N];

     void* philosopher(void* num) {
     int id = *(int*)num;
    
     while (1) {
        printf("Philosopher %d is thinking\n", id);
        sleep(1);
        
        // Take forks
        sem_wait(&forks[id]);
        sem_wait(&forks[(id + 1) % N]);

        printf("Philosopher %d is eating\n", id);
        sleep(1);

        // Put down forks
        sem_post(&forks[id]);
        sem_post(&forks[(id + 1) % N]);
       }
     }  

     int main() {
     pthread_t thread[N];
     int ids[N];
    
     for (int i = 0; i < N; i++)
        sem_init(&forks[i], 0, 1);

     for (int i = 0; i < N; i++) {
        ids[i] = i;
        pthread_create(&thread[i], NULL, philosopher, &ids[i]);
     }

     for (int i = 0; i < N; i++)
        pthread_join(thread[i], NULL);

     for (int i = 0; i < N; i++)
        sem_destroy(&forks[i]);

      return 0;
     }

## Reader-Writer Problem
#### Reader-Writer Problem adalah masalah klasik yang berhubungan dengan sinkronisasi dalam sistem konkuren. Ini menggambarkan situasi di mana beberapa proses (pembaca dan penulis) harus mengakses sumber daya bersama (misalnya, basis data) dengan cara tertentu:Pembaca: Beberapa pembaca dapat membaca data secara bersamaan.Penulis: Penulis membutuhkan akses eksklusif ke data. Ketika penulis sedang menulis, tidak ada pembaca atau penulis lain yang boleh mengakses data.
### Solusi dengan Sinkronisasi
#### Salah satu solusi umum menggunakan semaphores dan mutex untuk mengelola akses ke sumber daya bersama.

     #include <pthread.h>
     #include <semaphore.h>
     #include <stdio.h>
     #include <unistd.h>

     sem_t rw_mutex;  // Semaphore for writers
     sem_t mutex;     // Semaphore for reader count
     int read_count = 0;

     void* reader(void* arg) {
     int id = *(int*)arg;
    
     while (1) {
        sem_wait(&mutex);
        read_count++;
        if (read_count == 1)
            sem_wait(&rw_mutex);
        sem_post(&mutex);

        printf("Reader %d is reading\n", id);
        sleep(1);

        sem_wait(&mutex);
        read_count--;
        if (read_count == 0)
            sem_post(&rw_mutex);
        sem_post(&mutex);

        sleep(1);
      }
     }

     void* writer(void* arg) {
     int id = *(int*)arg;

     while (1) {
        sem_wait(&rw_mutex);

        printf("Writer %d is writing\n", id);
        sleep(1);

        sem_post(&rw_mutex);

        sleep(1);
      }
     }

     int main() {
     pthread_t rtid[5], wtid[2];
     int ids[5] = {1, 2, 3, 4, 5};
     int writer_ids[2] = {1, 2};

     sem_init(&rw_mutex, 0, 1);
     sem_init(&mutex, 0, 1);

     for (int i = 0; i < 5; i++)
        pthread_create(&rtid[i], NULL, reader, &ids[i]);
     for (int i = 0; i < 2; i++)
        pthread_create(&wtid[i], NULL, writer, &writer_ids[i]);

     for (int i = 0; i < 5; i++)
        pthread_join(rtid[i], NULL);
     for (int i = 0; i < 2; i++)
        pthread_join(wtid[i], NULL);

     sem_destroy(&rw_mutex);
     sem_destroy(&mutex);

     return 0;
     }

## Kesimpulan
#### Dining Problem berfokus pada menghindari deadlock saat beberapa proses mencoba mengakses sumber daya terbatas (garpu).
#### Reader-Writer Problem berfokus pada mengatur akses bersamaan antara proses pembaca dan penulis, memastikan bahwa pembaca dapat mengakses data bersama secara paralel sementara penulis memerlukan akses eksklusif.

