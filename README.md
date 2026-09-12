🧵 Multithreading Assignment
📌 Overview
This project demonstrates two multithreading problems:

Producer-Consumer Problem using Python Threads
Matrix Multiplication using Python Threads + TensorFlow with Animation

📂 Files in this Repository
| File | Description |
|---|---|
| producer_consumer.py | Producer-Consumer problem using Python threads and a shared Queue |
| matrix_to_gif.py | 100×100 matrix multiplication using Threads + TensorFlow with animation |
| matrix_multiplication.gif | GIF demonstration of the matrix multiplication |
| README.md | Project documentation |

1️⃣ Producer-Consumer Problem
The Producer-Consumer problem is implemented using Python threads and a shared thread-safe queue.Queue as the buffer.

The Producer adds items to the buffer.
The Consumer removes items from the buffer.
queue.Queue handles thread-safe access to the shared buffer internally.
put() blocks automatically when the buffer is full.
get() blocks automatically when the buffer is empty.
A sentinel value (-1) signals the consumer to stop.

The program uses a buffer of capacity 5 and produces/consumes 10 items.

🔹 Concepts Used
Python Threads
Shared Resource
queue.Queue
Thread-safe put()/get()
Producer/Consumer Synchronization
Sentinel Value Signaling

▶️ How to Run
Using the terminal:

python producer_consumer.py

🖥️ Sample Output
Produced: 1
Consumed: 1
Produced: 2
Produced: 3
Consumed: 2
Produced: 4
Consumed:Produced: 5
 3
Produced: 6
Consumed: 4
Produced: 7
Produced: 8
Consumed: 5
Produced: 9
Produced: 10
Consumed: 6
Produced: -1
Consumed: 7
Consumed: 8
Consumed: 9
Consumed: 10
Consumed: -1
Producer-Consumer process completed.

2️⃣ Matrix Multiplication using Threads + TensorFlow
Three pairs of 100×100 matrices are multiplied using Python threads and TensorFlow.

The program creates 3 threads, one per matrix pair. Each thread calculates its full result matrix row by row.

Matrix A (100×100) × Matrix B (100×100)
                    ↓
             Matrix C (100×100)

🔹 How It Works
threading.Thread creates one worker thread per matrix pair.
Each thread processes its matrix row by row using tf.expand_dims, tf.multiply, and tf.reduce_sum.
TensorFlow performs the multiplication and summation.
Results are verified against tf.matmul() for correctness.
Matplotlib displays the multiplication process through animation.

🎬 Animation
The animation shows:

🔵 Matrix A – a blue outline indicates the current row.
🟢 Matrix B – a green outline indicates the current column.
🟠 Matrix C – the result matrix fills in as cells are completed, shown with an orange outline.

The animation is generated for the first matrix pair (A1 × B1 = C1) and saved as a GIF.

🎬 Animation Output
matrix_multiplication.gif

▶️ Installation
Install the required packages:

pip install tensorflow numpy matplotlib pillow

▶️ Run
python matrix_to_gif.py

The program first performs the threaded matrix multiplication and prints the execution time and verification results. The animation is then generated and saved automatically as matrix_multiplication.gif.

🖥️ Sample Output
=================================================================
MATRIX MULTIPLICATION USING PYTHON THREADS + TENSORFLOW
=================================================================

Matrix size : 100 x 100
Number of simultaneous multiplications : 3
Framework : TensorFlow

TensorFlow version : x.x.x
GPU not detected - CPU will be used

=================================================================
STARTING 3 MATRIX MULTIPLICATIONS
=================================================================
Thread 1 started
Matrix 1: A1 x B1
Thread 2 started
Matrix 2: A2 x B2
Thread 3 started
Matrix 3: A3 x B3
...
Thread 1 FINISHED
Thread 2 FINISHED
Thread 3 FINISHED

=================================================================
ALL 3 THREADS COMPLETED
=================================================================
Total execution time : 0.xxxx seconds

=================================================================
VERIFYING RESULTS
=================================================================
C1 maximum error : 0.00xxxxx
C2 maximum error : 0.00xxxxx
C3 maximum error : 0.00xxxxx

All results verified using TensorFlow.

🛠️ Technologies Used
Python
TensorFlow
threading
NumPy
Matplotlib
Multithreading

📋 Requirements
Python
Python 3.9 or above
TensorFlow
NumPy
Matplotlib
Pillow

Install Python dependencies using:

pip install tensorflow numpy matplotlib pillow
