# Veri-Yapilari-ve-Algoritmalar
<h1>1-Insertion Sort Projesi</h1>

22,27,16,2,18,6] şeklinde 6 elemanlı bir dizi. Bu diziyi Insertion Sort yöntemi ile sıralamak istiyoruz.

1- Insertion Sort yönteminde dizinin ilk elemanı atlanır. Çünkü ilk elemanı karşılaştırabileceğimiz bir başka önceki eleman yoktur. Atlanılan bu eleman, sayı grubunun sorted kısmında olduğu varsayılır. 

Yukarıdaki örnek ele alındığında:
[22|27,16,2,18,6] şeklinde bir başlangıç yapılır. "|" atama operatörü, sorted ve unsorted kısımların ayrımını göstermek amacıyla kullanılır.

2- Kendini yineleyen iteratif işlemler. 
Genellikle programlamada bu kısımda iç içe geçmiş iki adet "While" döngüsü kullanılır. Burada aşamalar şu şekilde ilerler;

 Unsorted kısımdaki ilk elemanı al, sorted alandaki son elemandan başlayarak karşılaştır. Karşılaştırma, daha küçük bir eleman bulunamayıncaya kadar devam et. 
 Bu süreçte kaydırma işlemi uygulanır.

a) Unsorted alanda bulunan 16 sayısı için:
[22,27|16,2,18,6] (Unsorted alandaki ilk eleman 16 alınır.)
[22,27,16|2,18,6] (Sorted alandaki ilk eleman 27 ile kıyaslanır. ve yerleri değiştirilir. Çünkü 16 daha küçüktür. 27 sayısının soluna kaydırılır.)
[22,16,27|2,18,6] (Tekrar soldaki elemanla kıyaslanır. 22'den küçük olduğu için yer değiştirme uygulanır. 16 sayısı 22 sayısının soluna kaydırılır.)
[16,22,27|2,18,6] (Kendinden küçük eleman kalmadığı için döngü biter. Bir sonraki unsorted eleman için işlemler başlar.)

b) Unsorted alanda bulunan 27 sayısı için:
[22|27,16,2,18,6] (Unsorted alandaki ilk eleman 27 alınır.)
[22,27|16,2,18,6] (Kendisinden daha küçük elemanın sağında olduğu için işlemden çıkılır.)


İteratif adımlar bu şekilde kendini tekrar eder ve unsorted alanda eleman kalmayınca iteratif adımlardan çıkılır. Artık elimizde sıralanmış bir dizi vardır.


<h2>3-Big-O Gösterimi</h2> 

Big-O gösterimlerinde worst case analiz edilir. Worst case analizinde ise input(girdi) "n" kabul edilerek gösterilir. 

- Worst Case : Dizinin tersten sıralanmış olarak verilmesi durumudur.

Worst Case durumunda dizimiz [27,22,18,16,6,2] şeklinde verilmiş olurdu. Bu durumda en küçük sayı en başa getirilene kadar işlem yapılacak dolayısıyla (n.(n+1))/2 

Dolayısıyla  O(n^2)

<h2>3-Time Complexity</h2>

Bu kısımda sorunun soruluş biçimi hatalı. Biz search değil sort işlemi yapıyoruz. Sayı aramıyoruz. Dolayısıyla Insertion sort hesaplamasında aradığımız bir sayı yok, ortada başta olması durumu da yok.

- Best Case : Dizinin zaten küçükten büyüğe sıralı verilmesi. Böyle bir durumda yapılacak tek şey sıralı  çubuğunu sağa kaydırmak. n tane sayı üzerinden geçeriz. O(n)
- Worst Case : Dizinin Büyükten küçüğe sıralı verilmesi. O(n^2)
- Average Case : Best case ile worst case'in ortalamasıdır. = (n+n^2)/2 = (n.(n+1))/2 = O(n^2)



<h3>Örnek Kod</h3>


 int i = 1,j,swap;
        while(i< array.length){
            j=i;
            while ( (j>0) && (array[j-1]>array[j]) ) {
           
                swap = array[j-1];
                array[j-1] = array[j];
                array[j] = swap;
                j--;  }
            i++; }
       


<h2>4</h2>
Dizi sıralandıktan sonra 18 sayısı hangi case'e girer ? 

Cevap : 18 sayısı herhangi bir case'e girmez, çünkü arama algoritması çözmüyoruz. 
