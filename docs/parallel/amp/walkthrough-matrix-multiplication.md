---
title: 'İzlenecek yol: Matris Çarpım'
ms.date: 04/23/2019
ms.assetid: 61172e8b-da71-4200-a462-ff3a908ab0cf
ms.openlocfilehash: 6387e68304c7b1dbf0531729b7b73b519f40d159
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215874"
---
# <a name="walkthrough-matrix-multiplication"></a>İzlenecek yol: Matris Çarpım

Bu adım adım izlenecek yol, matris çarpma 'nın yürütülmesini hızlandırmak için C++ AMP nasıl kullanacağınızı gösterir. İki algoritma sunulur, biri döşeme ve döşeme olmadan bir tane.

## <a name="prerequisites"></a>Önkoşullar

Başlamadan önce:

- [C++ amp genel bakış](../../parallel/amp/cpp-amp-overview.md)konusunu okuyun.

- [Kutucukları kullanarak](../../parallel/amp/using-tiles.md)okuyun.

- En az Windows 7 veya Windows Server 2008 R2 çalıştırdığınızdan emin olun.

### <a name="to-create-the-project"></a>Proje oluşturmak için

Yeni bir proje oluşturmak için yönergeler, yüklediğiniz Visual Studio sürümüne bağlı olarak farklılık gösterir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-the-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de proje oluşturmak için

1. **File** > **New** > **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda dosya yeni **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında, **dili** **C++** olarak ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **konsol**olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **boş proje** ' yi seçin ve ardından **İleri**' yi seçin. Bir sonraki sayfada, proje için bir ad belirtmek üzere **ad** kutusuna *matrixçarp* girin ve isterseniz proje konumunu belirtin.

   ![Yeni konsol uygulaması](../../build/media/mathclient-project-name-2019.png "Yeni konsol uygulaması")

1. İstemci projesini oluşturmak için **Oluştur** düğmesini seçin.

1. **Çözüm Gezgini**' de, **kaynak dosyaları**için kısayol menüsünü açın ve **Add** > **Yeni öğe**Ekle ' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda, **C++ dosyası (. cpp)** öğesini seçin, **ad** kutusuna *Matrixçarp. cpp* girin ve sonra **Ekle** düğmesini seçin.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-project-in-visual-studio-2017-or-2015"></a>Visual Studio 2017 veya 2015 ' de bir proje oluşturmak için

1. Visual Studio 'daki menü çubuğunda **Dosya** > **Yeni** > **Proje**' yi seçin.

1. Şablonlar bölmesinde **yüklü** altında **Visual C++**' yi seçin.

1. **Boş proje**' yi seçin, **ad** kutusuna *matrixçarp* girin ve **Tamam** düğmesini seçin.

1. **İleri** düğmesini seçin.

1. **Çözüm Gezgini**' de, **kaynak dosyaları**için kısayol menüsünü açın ve **Add** > **Yeni öğe**Ekle ' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda, **C++ dosyası (. cpp)** öğesini seçin, **ad** kutusuna *Matrixçarp. cpp* girin ve sonra **Ekle** düğmesini seçin.

::: moniker-end

## <a name="multiplication-without-tiling"></a>Döşeme olmadan çarpma

Bu bölümde, A ve B olmak üzere aşağıdaki şekilde tanımlanan iki matrisin çarpma sayısını göz önünde bulundurun:

![3&#45;&#45;2 matris A](../../parallel/amp/media/campmatrixanontiled.png "3&#45;&#45;2 matris A")

![2&#45;&#45;3 matris B](../../parallel/amp/media/campmatrixbnontiled.png "2&#45;&#45;3 matris B")

, 3-2 matrisi ve B, 2-3 matrisine sahiptir. B ile çarpılın çarpımı, aşağıdaki 3-3 matrisine sahiptir. Ürün, bir A öğesinin satırları ile B öğesi arasındaki sütunları çarpılarak hesaplanır.

![3&#45;&#45;3 ürün matrisi](../../parallel/amp/media/campmatrixproductnontiled.png "3&#45;&#45;3 ürün matrisi")

### <a name="to-multiply-without-using-c-amp"></a>C++ AMP kullanmadan çarpmak için

1. Matrixçarp. cpp ' i açın ve mevcut kodu değiştirmek için aşağıdaki kodu kullanın.

   ```cpp
   #include <iostream>

   void MultiplyWithOutAMP() {
       int aMatrix[3][2] = {{1, 4}, {2, 5}, {3, 6}};
       int bMatrix[2][3] = {{7, 8, 9}, {10, 11, 12}};
       int product[3][3] = {{0, 0, 0}, {0, 0, 0}, {0, 0, 0}};

       for (int row = 0; row < 3; row++) {
           for (int col = 0; col < 3; col++) {
               // Multiply the row of A by the column of B to get the row, column of product.
               for (int inner = 0; inner < 2; inner++) {
                   product[row][col] += aMatrix[row][inner] * bMatrix[inner][col];
               }
               std::cout << product[row][col] << "  ";
           }
           std::cout << "\n";
       }
   }

   int main() {
       MultiplyWithOutAMP();
       getchar();
   }
   ```

   Algoritma, matris çarpma tanımının kolay bir uygulamasıdır. Hesaplama süresini azaltmak için herhangi bir paralel veya iş parçacıklı algoritma kullanmaz.

1. Menü çubuğunda **Dosya**  >  **Tümünü Kaydet**' i seçin.

1. Hata ayıklamayı başlatmak için **F5** klavye kısayolunu seçin ve çıktının doğru olduğunu doğrulayın.

1. Uygulamadan çıkmak için **ENTER** ' ı seçin.

### <a name="to-multiply-by-using-c-amp"></a>C++ AMP kullanarak çarpmak için

1. Matrixçarp. cpp içinde, yönteminin önüne aşağıdaki kodu ekleyin `main` .

   ```cpp
   void MultiplyWithAMP() {
   int aMatrix[] = { 1, 4, 2, 5, 3, 6 };
   int bMatrix[] = { 7, 8, 9, 10, 11, 12 };
   int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0 };

   array_view<int, 2> a(3, 2, aMatrix);

   array_view<int, 2> b(2, 3, bMatrix);

   array_view<int, 2> product(3, 3, productMatrix);

   parallel_for_each(product.extent,
      [=] (index<2> idx) restrict(amp) {
          int row = idx[0];
          int col = idx[1];
          for (int inner = 0; inner <2; inner++) {
              product[idx] += a(row, inner)* b(inner, col);
          }
      });

   product.synchronize();

   for (int row = 0; row <3; row++) {
      for (int col = 0; col <3; col++) {
          //std::cout << productMatrix[row*3 + col] << "  ";
          std::cout << product(row, col) << "  ";
      }
      std::cout << "\n";
     }
   }
   ```

   AMP kodu AMP olmayan koda benzer. ' A çağrı, `parallel_for_each` içindeki her öğe için bir iş parçacığı başlatır `product.extent` ve **`for`** satır ve sütun döngülerinin yerini alır. Satır ve sütundaki hücrenin değeri ' de kullanılabilir `idx` . Bir `array_view` nesnenin öğelerine `[]` işleç ve bir dizin değişkeni ya da `()` işlecini ve satır ve sütun değişkenlerini kullanarak erişebilirsiniz. Örnek her iki yöntemi gösterir. `array_view::synchronize`Yöntemi, `product` değişkeninin değerlerini değişkenine geri kopyalar `productMatrix` .

1. Aşağıdaki `include` ve **`using`** deyimlerini matrixçarp. cpp üst kısmına ekleyin.

   ```cpp
   #include <amp.h>
   using namespace concurrency;
   ```

1. Yöntemini `main` çağırmak için yöntemini değiştirin `MultiplyWithAMP` .

   ```cpp
   int main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       getchar();
   }
   ```

1. **Ctrl** + Hata ayıklamayı başlatmak için CTRL**F5** klavye kısayoluna basın ve çıktının doğru olduğunu doğrulayın.

1. Uygulamadan çıkmak için **Ara çubuğuna** basın.

## <a name="multiplication-with-tiling"></a>Döşeme ile çarpma

Döşeme, verileri, kutucuk olarak bilinen eşit ölçekli alt kümeler halinde bölümleyerek bir tekniktir. Döşeme kullandığınızda üç şey değişir.

- `tile_static`Değişkenler oluşturabilirsiniz. Boşluk alanındaki verilere erişim `tile_static` , genel alanda verilere erişimden çok daha hızlı olabilir. `tile_static`Her kutucuk için bir değişken örneği oluşturulur ve kutucuktaki tüm iş parçacıkları değişkene erişebilir. Erişim nedeniyle, döşeme 'nin birincil avantajı, performans kazandır `tile_static` .

- Belirli bir kod satırında tek bir kutucukta tüm iş parçacıklarını durdurmak için [tile_barrier:: wait](reference/tile-barrier-class.md#wait) yöntemini çağırabilirsiniz. İş parçacıklarının çalışacağı sırayı garanti edemezsiniz, ancak yalnızca bir kutucuktaki tüm iş parçacıklarının `tile_barrier::wait` yürütmeye devam etmeden önce yapılan çağrıda duracaktır.

- `array_view`Nesnenin tamamına ve kutucuğa göre dizine göre iş parçacığının dizinine erişebilirsiniz. Yerel dizini kullanarak, kodunuzun okunmasını ve hata ayıklamasını daha kolay hale getirebilirsiniz.

Matris çarpma aşamasında döşeme avantajlarından yararlanmak için, algoritmanın matrisi kutucuklara bölümlemek ve sonra kutucuk verilerini `tile_static` daha hızlı erişim için değişkenlere kopyalaması gerekir. Bu örnekte, matris eşittir boyutunun alt matrislerine bölümlenir. Ürün, alt matrisleri çarpılarak bulunur. Bu örnekteki iki matrisler ve çarpımı şunlardır:

![4&#45;&#45;4 matris A](../../parallel/amp/media/campmatrixatiled.png "4&#45;&#45;4 matris A")

![4&#45;&#45;4 matris B](../../parallel/amp/media/campmatrixbtiled.png "4&#45;&#45;4 matris B")

![4&#45;&#45;4 ürün matrisi](../../parallel/amp/media/campmatrixproducttiled.png "4&#45;&#45;4 ürün matrisi")

Matrisler, aşağıdaki gibi tanımlanan dört 2x2 matriste bölümlenir:

![4&#45;&#45;4 matris,&#45;2 alt&#45;matrisleriyle 2&#45;bölümlenmiş](../../parallel/amp/media/campmatrixapartitioned.png "4&#45;&#45;4 matris,&#45;2 alt&#45;matrisleriyle 2&#45;bölümlenmiş")

![4&#45;&#45;4 matris B&#45;2 alt&#45;matrisleri tarafından 2&#45;bölümlenmiş](../../parallel/amp/media/campmatrixbpartitioned.png "4&#45;&#45;4 matris B&#45;2 alt&#45;matrisleri tarafından 2&#45;bölümlenmiş")

A ve B ürünleri artık aşağıdaki gibi yazılabilir ve hesaplanabilir:

![4&#45;&#45;4 matris,&#45;2 alt&#45;matrisleriyle 2&#45;bölümlenmiş](../../parallel/amp/media/campmatrixproductpartitioned.png "4&#45;&#45;4 matris,&#45;2 alt&#45;matrisleriyle 2&#45;bölümlenmiş")

Matrisler `a` `h` , 2x2 matrisleri olduğundan, bunların tüm ürünleri ve toplamları de 2x2 matrisleri vardır. Ayrıca, A ve B ürününün beklenen şekilde bir 4x4 matrisi olması gerekir. Algoritmayı hızlıca denetlemek için, ilk satırdaki, ürünün ilk sütununda öğenin değerini hesaplayın. Örnekte, bu, öğesinin ilk satırdaki ve ilk sütunundaki değeri olacaktır `ae + bg` . `ae`Her dönem için yalnızca ilk sütunu ve ilk satırını hesaplamanız yeterlidir `bg` . İçin bu değer `ae` `(1 * 1) + (2 * 5) = 11` . İçin değeri `bg` `(3 * 1) + (4 * 5) = 23` . Son değer `11 + 23 = 34` , doğru.

Bu algoritmayı uygulamak için kod:

- Çağrısındaki bir `tiled_extent` nesne yerine bir nesne kullanır `extent` `parallel_for_each` .

- Çağrısındaki bir `tiled_index` nesne yerine bir nesne kullanır `index` `parallel_for_each` .

- `tile_static`Alt matrisleri tutacak değişkenler oluşturur.

- `tile_barrier::wait`Alt Matrislerin ürünlerinin hesaplanmasıyla ilgili iş parçacıklarını durdurmak için yöntemini kullanır.

### <a name="to-multiply-by-using-amp-and-tiling"></a>AMP ve döşeme kullanarak çarpmak için

1. Matrixçarp. cpp içinde, yönteminin önüne aşağıdaki kodu ekleyin `main` .

   ```cpp
   void MultiplyWithTiling() {
       // The tile size is 2.
       static const int TS = 2;

       // The raw data.
       int aMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };
       int bMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };
       int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 };

       // Create the array_view objects.
       array_view<int, 2> a(4, 4, aMatrix);
       array_view<int, 2> b(4, 4, bMatrix);
       array_view<int, 2> product(4, 4, productMatrix);

       // Call parallel_for_each by using 2x2 tiles.
       parallel_for_each(product.extent.tile<TS, TS>(),
           [=] (tiled_index<TS, TS> t_idx) restrict(amp)
           {
               // Get the location of the thread relative to the tile (row, col)
               // and the entire array_view (rowGlobal, colGlobal).
               int row = t_idx.local[0];
               int col = t_idx.local[1];
               int rowGlobal = t_idx.global[0];
               int colGlobal = t_idx.global[1];
               int sum = 0;

               // Given a 4x4 matrix and a 2x2 tile size, this loop executes twice for each thread.
               // For the first tile and the first loop, it copies a into locA and e into locB.
               // For the first tile and the second loop, it copies b into locA and g into locB.
               for (int i = 0; i < 4; i += TS) {
                   tile_static int locA[TS][TS];
                   tile_static int locB[TS][TS];
                   locA[row][col] = a(rowGlobal, col + i);
                   locB[row][col] = b(row + i, colGlobal);
                   // The threads in the tile all wait here until locA and locB are filled.
                   t_idx.barrier.wait();

                   // Return the product for the thread. The sum is retained across
                   // both iterations of the loop, in effect adding the two products
                   // together, for example, a*e.
                   for (int k = 0; k < TS; k++) {
                       sum += locA[row][k] * locB[k][col];
                   }

                   // All threads must wait until the sums are calculated. If any threads
                   // moved ahead, the values in locA and locB would change.
                   t_idx.barrier.wait();
                   // Now go on to the next iteration of the loop.
               }

               // After both iterations of the loop, copy the sum to the product variable by using the global location.
               product[t_idx.global] = sum;
           });

       // Copy the contents of product back to the productMatrix variable.
       product.synchronize();

       for (int row = 0; row <4; row++) {
           for (int col = 0; col <4; col++) {
               // The results are available from both the product and productMatrix variables.
               //std::cout << productMatrix[row*3 + col] << "  ";
               std::cout << product(row, col) << "  ";
           }
           std::cout << "\n";
       }
   }
   ```

   Bu örnek, döşeme olmadan örnekteki önemli ölçüde farklıdır. Kod şu kavramsal adımları kullanır:
   1. [0, 0] kutucuğunun öğelerini `a` içine kopyalayın `locA` . [0, 0] kutucuğunun öğelerini `b` içine kopyalayın `locB` . `product`Döşeli, `a` ve değildir `b` . Bu nedenle, ve erişmek için genel dizinleri kullanırsınız `a, b` `product` . Çağrısı `tile_barrier::wait` önemlidir. Her ikisi de dolduruluncaya kadar kutucuktaki tüm iş parçacıklarını `locA` sonlandırır `locB` .

   1. `locA`Sonuçları çarpın ve `locB` içine koyun `product` .

   1. [0, 1] kutucuğunun öğelerini `a` içine kopyalayın `locA` . [1, 0] kutucuğunun öğelerini `b` içine kopyalayın `locB` .

   1. `locA`Ve ' `locB` de zaten olan sonuçlara ekleyin ve bunları çarpın `product` .

   1. [0, 0] kutucuğunun çarpma işlemi tamamlanmıştır.

   1. Diğer dört kutucuk için tekrarlayın. Özellikle kutucuklar için dizin oluşturma yoktur ve iş parçacıkları herhangi bir sırada çalıştırılabilir. Her iş parçacığı yürütüldüğünde, `tile_static` değişkenler her kutucuk için uygun şekilde oluşturulur ve `tile_barrier::wait` program akışını denetler.

   1. Algoritmayı yakından inceleyerek, her bir alt matrisin bir belleğe iki kez yüklendiğine dikkat edin `tile_static` . Bu veri aktarımı zaman alır. Ancak, veriler belleğe alındıktan sonra `tile_static` verilere erişim çok daha hızlıdır. Ürünlerin hesaplanması alt matrislerdeki değerlere yinelenen erişim gerektirdiğinden, genel bir performans kazancı vardır. Her algoritma için, en uygun algoritmayı ve döşeme boyutunu bulmak için deneme gerekir.

   AMP olmayan ve kutucuk olmayan örneklerde, A ve B öğelerinin her öğesine, ürünü hesaplamak için genel bellekten dört kez erişilir. Kutucuk örneğinde, her öğe genel bellekten iki kez ve bellekten dört kez erişilir `tile_static` . Bu önemli bir performans kazancı değildir. Ancak, A ve B 'nin 1024x1024 matrisi ve döşeme boyutu 16 ise, önemli bir performans kazancı elde edersiniz. Bu durumda, her öğe `tile_static` yalnızca 16 kez belleğe kopyalanıp `tile_static` bellek 1024 katından erişilir.

1. Gösterildiği gibi, yöntemi çağırmak için Main metodunu değiştirin `MultiplyWithTiling` .

   ```cpp
   int main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       MultiplyWithTiling();
       getchar();
   }
   ```

1. **Ctrl** + Hata ayıklamayı başlatmak için CTRL**F5** klavye kısayoluna basın ve çıktının doğru olduğunu doğrulayın.

1. Uygulamadan çıkmak için **boşluk** çubuğuna basın.

## <a name="see-also"></a>Ayrıca bkz.

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[İzlenecek yol: C++ AMP uygulamasında hata ayıklama](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)
