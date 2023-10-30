# Praktikum-4-dan-5
Nama	: Saktia Wardhana
NIM	: 5311421004

PRAKTIKUM 4 ARTIFICIAL INTELLIGENCE
1.	Tentukan bagaimana algoritma BFS di atas dapat menentukan node ke 8, 6, dan 7. 2. 
2.	Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.5 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 5. 
3.	Ubahlah method static void main sehingga bentuk tree seperti Gambar 4.6 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node 9. 
4.	Ubahlah kode program di atas sehingga bentuk tree seperti Gambar 4.7 dapat dibentuk. Kemudian tentukan bagaimana algoritma BFS dapat menemukan node C.

JAWAB
Tentukan bagaimana algoritma BFS di atas dapat menentukan node ke 8, 6, dan 7. 2.
1.	Algoritma BFS dimulai dengan node awal n3.
2.	Semua node dalam graf diinisialisasi sebagai putih (WHITE) kecuali n3, yang diwarnai abu-abu (GRAY) karena sedang diproses.
3.	Node awal n3 memiliki jarak (distance) 0.
4.	Node-node terhubung langsung dengan n3 adalah n2 dan n4. Keduanya dimasukkan ke dalam antrian (queue) untuk diproses selanjutnya.
5.	Algoritma BFS akan terus beriterasi selama antrian masih berisi node.
6.	Node yang sedang diproses adalah n3, dengan adjacency list berisi n2 dan n4.
7.	Node n2 dan n4 adalah putih (WHITE) karena belum diproses. Mereka diubah menjadi abu-abu (GRAY), jarak dihitung, dan n3 diatur sebagai pendahulunya.
-	n2 memiliki jarak 1 dari n3.
-	n4 memiliki jarak 1 dari n3.
8.	n2 dan n4 dimasukkan ke antrian (queue) untuk pemrosesan berikutnya.
9.	Algoritma akan terus melanjutkan dengan mengambil node dari antrian untuk diproses selanjutnya.
10.	 Ini akan berlangsung hingga seluruh node terhubung dalam graf telah diproses.
11.	Node-node yang selesai diproses akan diwarnai hitam (BLACK).
Hasil dari algoritma BFS adalah menemukan jarak terpendek dari n3 ke semua node lain dalam graf serta menetapkan node pendahulu untuk setiap node. Dengan informasi ini, Anda dapat menghitung jarak dari n3 ke n8, n6, dan n7.
Misalnya, n8 terhubung dengan n6, yang terhubung dengan n4, yang terhubung dengan n3. Jarak dari n3 ke n4 adalah 1, jarak dari n4 ke n6 adalah 1, dan jarak dari n6 ke n8 adalah 1. Jadi, jarak dari n3 ke n8 adalah 3. n7 juga terhubung dengan n6, n4, dan n3, dengan jarak yang sama.

Tentukan bagaimana algoritma BFS dapat menemukan node 5. 
Ubah pada bagian static void nya menjadi seperti berikut
public static void main(String[] args)

{
    BS graph = new BS();
    Node n0 = new Node(0);
    Node n1 = new Node(1);
    Node n2 = new Node(2);
    Node n3 = new Node(3);
    Node n4 = new Node(4);
    Node n5 = new Node(5);
    Node n6 = new Node(6);
    
    
    
    // Ganti graph dan edge sesuai dengan yang diinginkan
    graph.addEdge(n0, n1);
    graph.addEdge(n0, n2);
   
    graph.addEdge(n1, n0);
    graph.addEdge(n1, n3);
    graph.addEdge(n1, n4);

    graph.addEdge(n2, n0);
    graph.addEdge(n2, n5);
    graph.addEdge(n2, n6);
   
    graph.addEdge(n3, n1);
    graph.addEdge(n3, n4);

    graph.addEdge(n4, n3);
    graph.addEdge(n4, n1);

    graph.addEdge(n5, n2);
    graph.addEdge(n5, n6);
    graph.addEdge(n5, n1);

    graph.addEdge(n6, n2);
    graph.addEdge(n6, n5);
    graph.addEdge(n6, n1);
    
    graph.bfs(n0);
}
kode diatas memberikan output (0,d=0) (1,d=1) (2,d=1) (3,d=2) (4,d=2) (5,d=2) (6,d=2)
Berikut langkah langkah BFS menemukan node 5 :
1.	Langkah pertama, masukkan node 0 ke dalam antrian.
2.	Selanjutnya, periksa apakah node 5 sudah ada dalam antrian. Namun, pada langkah ini, node 5 tidak ditemukan dalam antrian.
3.	Kemudian, keluarkan node 0 dari antrian.
4.	Setelah itu, lakukan pemeriksaan terhadap semua node yang bertetangga dengan node 0. Pada tahap ini, node 1 dan 2 belum pernah dikunjungi.
5.	Node 2 dan 3 kemudian dimasukkan ke dalam antrian.
6.	Lanjutkan dengan pemeriksaan apakah node 5 telah ada dalam antrian. Namun, pada saat ini, node 5 masih belum ditemukan dalam antrian.
7.	Berikutnya, lakukan pengeluaran (dequeue) terhadap node 1.
8.	Setelah itu, periksa semua node yang bertetangga dengan node 1. Node 3 dan 4 adalah node yang belum pernah dikunjungi.
9.	Node 3 dan 4 kemudian dimasukkan ke dalam antrian.
10.	1Melakukan pemeriksaan kembali apakah node 5 sudah ada dalam antrian. Namun, node 5 masih belum ditemukan dalam antrian pada saat ini.
11.	Kembali ke node-node yang bertetangga dengan node 0, yaitu node 1 dan 2. Node 1 sudah pernah diperiksa sebelumnya.
12.	Selanjutnya, periksa semua node yang bertetangga dengan node 2. Node 5 dan 6 adalah node-node yang belum pernah dikunjungi.
13.	Node 5 dan 6 kemudian dimasukkan ke dalam antrian.
14.	 Pada tahap ini, akhirnya ditemukan bahwa node 5 sudah ada dalam antrian, sehingga node 5 ditemukan.


Tentukan bagaimana algoritma BFS dapat menemukan node 9.
Ubah static void nya menjadi seperti berikut
public static void main(String[] args)

{
    BS2 graph = new BS2();
    Node n1 = new Node(1);
    Node n2 = new Node(2);
    Node n3 = new Node(3);
    Node n4 = new Node(4);
    Node n5 = new Node(5);
    Node n6 = new Node(6);
    Node n7 = new Node(7);
    Node n8 = new Node(8);
    Node n9 = new Node(9);
    Node n10 = new Node(10);
    Node n11 = new Node(11);
    Node n12 = new Node(12);

    graph.addEdge(n1, n2);
    graph.addEdge(n1, n3);
    graph.addEdge(n1, n4);

    graph.addEdge(n2, n1);
    graph.addEdge(n2, n5);
    graph.addEdge(n2, n6);
    
    graph.addEdge(n3, n1);
    
    graph.addEdge(n4, n1);
    graph.addEdge(n4, n7);
    graph.addEdge(n4, n8);
    
    graph.addEdge(n5, n2);
    graph.addEdge(n5, n9);
    graph.addEdge(n5, n10);
    graph.addEdge(n5, n6);
    
    graph.addEdge(n6, n2);
    graph.addEdge(n6, n5);
    
    
    graph.addEdge(n7, n4);
    graph.addEdge(n7, n11);
    graph.addEdge(n7, n12);
    graph.addEdge(n7, n8);
    
    graph.addEdge(n8, n4);
    graph.addEdge(n8, n7);

    graph.addEdge(n9, n5);
    graph.addEdge(n9, n10);

    graph.addEdge(n10, n5);
    graph.addEdge(n10, n9);

    graph.addEdge(n11, n7);
    graph.addEdge(n11, n12);

    graph.addEdge(n12, n7);
    graph.addEdge(n12, n11);
    
    graph.bfs(n1);
}
kode diatas memberikan output (1,d=0) (2,d=1) (3,d=1) (4,d=1) (5,d=2) (6,d=2) (7,d=2) (8,d=2) (9,d=3) (10,d=3) (11,d=3) (12,d=3)
1.	1Langkah pertama, masukkan node 1 ke dalam antrian.
2.	Selanjutnya, lakukan pemeriksaan apakah node 9 sudah ada dalam antrian. Pada saat itu, node 9 tidak ditemukan dalam antrian.
3.	Kemudian, keluarkan node 1 dari antrian.
4.	Dilanjutkan dengan pemeriksaan terhadap semua node yang bertetangga dengan node 1. Node 2, 3, dan 4 adalah node yang belum pernah dikunjungi.
5.	Node 2, 3, dan 4 kemudian dimasukkan ke dalam antrian.
6.	Berikutnya, periksa kembali apakah node 9 sudah ada dalam antrian. Pada langkah ini, node 9 masih belum ditemukan dalam antrian.
7.	Selanjutnya, keluarkan node 2 dari antrian.
8.	Lakukan pemeriksaan terhadap semua node yang bertetangga dengan node 2. Node 5 dan 6 adalah node yang belum pernah dikunjungi.
9.	Node 5 dan 6 kemudian dimasukkan ke dalam antrian.
10.	1Melakukan pemeriksaan kembali apakah node 9 sudah ada dalam antrian. Pada saat ini, node 9 masih belum ditemukan dalam antrian.
11.	Lalu, keluarkan node 5 dari antrian.
12.	Periksa semua node yang bertetangga dengan node 5. Node 9 dan 10 adalah node yang belum pernah dikunjungi.
13.	Node 9 dan 10 kemudian dimasukkan ke dalam antrian.
14.	Pada tahap ini, dilakukan pemeriksaan apakah node 9 sudah ada dalam antrian.


Tentukan bagaimana algoritma BFS dapat menemukan node C.
ubah static void nya menjadi seperti dibawah
public static void main(String[] args)

{
    BS3 graph = new BS3();
    Node n1 = new Node('A');
    Node n2 = new Node('B');
    Node n3 = new Node('C');
    Node n4 = new Node('D');
    Node n5 = new Node('E');
    Node n6 = new Node('F');
    Node n7 = new Node('G');
    Node n8 = new Node('H');
    Node n9 = new Node('I');
    
    graph.addEdge(n1, n2);
    graph.addEdge(n1, n4);

    graph.addEdge(n2, n6);
    graph.addEdge(n2, n1);
    graph.addEdge(n2, n4);
    
    graph.addEdge(n3, n4);
    graph.addEdge(n3, n5);
    
    graph.addEdge(n4, n2);
    graph.addEdge(n4, n3);
    graph.addEdge(n4, n5);
    
    
    graph.addEdge(n5, n4);
    graph.addEdge(n5, n3);
    
    
    graph.addEdge(n6, n2);
    graph.addEdge(n6, n7);
   
    
    
    graph.addEdge(n7, n6);
    graph.addEdge(n7, n9);
    
    graph.addEdge(n8, n9);
    
    graph.addEdge(n9, n8);
    
    graph.bfs(n6);
}

Dan juga pada bagian yang bertuliskan int data yaitu pada public class dan public Node diganti dengan char karena kita menggunakan huruf bukan menggunakan angka
public class BS3 {
  public enum NodeColour {
      WHITE, GRAY, BLACK
  }

  public static class Node {
      char data;
      int distance;
      Node predecessor;
      NodeColour colour;

  public Node(char data)

  {
    this.data = data;
  }

    public String toString() {
        return "(" + data + ",d=" + distance + ")";
    }
  }

kode diatas memberikan output (F,d=0) (B,d=1) (G,d=1) (A,d=2) (D,d=2) (I,d=2) (C,d=3) (E,d=3) (H,d=3)
1.	Langkah pertama, masukkan node F ke dalam antrian.
2.	Selanjutnya, lakukan pemeriksaan apakah node C sudah ada dalam antrian. Pada saat itu, node C tidak ditemukan dalam antrian.
3.	Kemudian, keluarkan node F dari antrian.
4.	 Dilanjutkan dengan pemeriksaan terhadap semua node yang bertetangga dengan node F. Node B dan G adalah node yang belum pernah dikunjungi.
5.	Node B dan G kemudian dimasukkan ke dalam antrian.
6.	Berikutnya, periksa kembali apakah node C sudah ada dalam antrian. Pada langkah ini, node C masih belum ditemukan dalam antrian.
7.	Selanjutnya, keluarkan node B dari antrian.
8.	Lakukan pemeriksaan terhadap semua node yang bertetangga dengan node B. Node A dan D adalah node yang belum pernah dikunjungi.
9.	Node A dan D kemudian dimasukkan ke dalam antrian.
10.	Melakukan pemeriksaan kembali apakah node C sudah ada dalam antrian. Pada saat ini, node C masih belum ditemukan dalam antrian.
11.	1Lalu, keluarkan node A dari antrian.
12.	Dilanjutkan dengan pemeriksaan, tetapi tidak ada node yang bertetangga dengan node A.
13.	1Kemudian, keluarkan node D dari antrian.
14.	Selanjutnya, periksa node-node yang bertetangga dengan node D. Node C dan E adalah node yang belum pernah dikunjungi.
15.	Node C dan E kemudian dimasukkan ke dalam antrian.
16.	Pada tahap ini, dilakukan pemeriksaan apakah node C sudah ada dalam antrian, dan pada akhirnya, node C ditemukan.



LAMPIRAN
1.	
 
Gambar 4.5 Tree 1
2.	
 
Gambar 4.6 Tree 2
3.	
 
Gambar 4.7 Tree 3



















MODUL 5 TEKNIK HEURISTIC SEARCH

1.	Pelajari class EightPuzzleSearch, EightPuzzleSpace, dan Node. 
2.	Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya Gambar 8. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1. 
3.	Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya Gambar 5.9. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1 dan 2. 
4.	Ubahlah initial dan goal state dari program di atas sehingga bentuk initial dan goal statenya Gambar 5.10. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal state. Analisa dan bedakan dengan solusi pada point 1, 2, dan 3. 
5.	Ubahlah initial dan goal state dari program dan class-class di atas sehingga bentuk initial dan goal statenya Gambar 5.11. Kemudian tentukan langkah-langkah mana saja sehingga puzzlenya mencapai goal statezle.

Pelajari class EightPuzzleSearch, EightPuzzleSpace, dan Node.
Kelas Node:
1.	Kelas ini menggambarkan suatu node atau keadaan dalam ruang pencarian, terutama dalam konteks penyelesaian masalah 8-puzzle.
2.	Bidang 'state' adalah sebuah larik yang terdiri dari 9 bilangan bulat yang menggambarkan keadaan atau posisi ubin dalam papan permainan.
3.	Bidang 'cost' mencerminkan biaya yang terkait dengan mencapai node ini.
4.	Bidang 'parent' merujuk kepada node induk dalam pohon pencarian.
5.	Bidang 'successors' adalah kumpulan node-node anak.

Metode:
1.	Konstruktor Node(int s[], Node parent) digunakan untuk menginisialisasi simpul dengan keadaan khusus dan simpul induk.
2.	Metode toString() menghasilkan representasi string dari keadaan simpul.
3.	Metode equals(Object node) digunakan untuk membandingkan dua simpul dan menentukan apakah mereka memiliki keadaan yang sama.
4.	Metode getPath(Vector<Node> v) memberikan jalur dari simpul akar ke simpul saat ini dalam bentuk vektor.
5.	Metode getPath() menghasilkan jalur dalam bentuk vektor yang baru.

Kelas EightPuzzleSearch:
1.	Kelas ini memiliki tanggung jawab untuk melakukan pencarian solusi pada masalah 8-puzzle. 
2.	Vektor open berperan dalam menyimpan simpul-simpul yang perlu dijelajahi, sementara vektor closed digunakan untuk menyimpan simpul-simpul yang sudah dijelajahi. 
3.	Terdapat dua metode heuristik dalam kelas ini, yaitu h1Cost() dan h2Cost(), yang digunakan untuk menghitung biaya simpul dengan pendekatan heuristik yang berbeda. 
4.	Metode hCost(Node node) berfungsi untuk memilih heuristik yang akan digunakan (h1 atau h2) dalam perhitungan biaya.

Metode:
1.	Metode getBestNode(Vector nodes) menghasilkan simpul yang memiliki biaya terendah dari vektor simpul yang diberikan. 
2.	Metode getPreviousCost(Node node) mengembalikan biaya simpul jika simpul tersebut terdapat dalam daftar open atau closed.
3.	 Metode printPath(Vector path) mencetak jalur dari simpul awal ke simpul tujuan. 
4.	 Metode run() adalah metode utama yang mengeksekusi algoritma pencarian.
Kelas EightPuzzleSpace:
1.	Kelas ini menentukan keadaan awal dan tujuan dalam masalah 8-puzzle dan juga menghasilkan simpul-simpul penerus. 
2.	Metode getRoot() mengembalikan keadaan awal sebagai simpul. 
3.	Metode getGoal() mengembalikan keadaan tujuan sebagai simpul. 
4.	Metode getSuccessors(Node parent) menghasilkan simpul-simpul penerus berdasarkan pergeseran ubin kosong. 
5.	Metode transformState() digunakan untuk menciptakan simpul baru dengan pertukaran dua ubin dalam keadaan.
Kode ini mengimplementasikan algoritma pencarian yang menjalankan tugas mencari solusi dalam masalah 8-puzzle. Ini mencakup eksplorasi berbagai kemungkinan keadaan, mengevaluasi biaya menggunakan heuristik, dan memilih simpul-simpul yang menjanjikan untuk lebih lanjut dieksplorasi. Pencarian akan terus berlanjut hingga solusi ditemukan atau semua kemungkinan telah dijelajahi.

Hasil Program:
 
Ubahlah keadaan awal (initial state) dan keadaan tujuan (goal state) dalam program di atas untuk mencocokkan Gambar 5.8. Selanjutnya, tentukan langkah-langkah yang diperlukan agar puzzle mencapai keadaan tujuan. Lalu, analisis dan perbandingkan solusi ini dengan solusi pada poin 1.
Hasil Program:
 
Ubahlah keadaan awal (initial state) dan keadaan tujuan (goal state) dalam program di atas agar sesuai dengan Gambar 5.9. Selanjutnya, identifikasikan langkah-langkah yang diperlukan untuk mencapai keadaan tujuan dalam puzzle. Lakukan analisis dan perbandingan dengan solusi pada poin 1 dan 2.
Hasil Program:
 
Ubahlah keadaan awal (initial state) dan keadaan tujuan (goal state) dalam program di atas dengan Gambar 5.10. Selanjutnya, tentukan langkah-langkah yang perlu diambil agar puzzle mencapai keadaan tujuan tersebut. Selanjutnya, lakukan analisis dan perbandingan dengan solusi pada poin 1, 2, dan 3.
Hasil Program:
 
Ubahlah keadaan awal (initial state) dan keadaan tujuan (goal state) dalam program dan kelas-kelas di atas agar sesuai dengan Gambar 5.11. Selanjutnya, identifikasikan langkah-langkah yang diperlukan untuk mencapai keadaan tujuan dalam puzzle.
Hasil Program:


