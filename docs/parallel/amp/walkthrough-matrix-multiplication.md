---
title: 'İzlenecek yol: Matris Çarpım'
ms.date: 04/23/2019
ms.assetid: 61172e8b-da71-4200-a462-ff3a908ab0cf
ms.openlocfilehash: f30f8dc235bf0e76c342bea26a35bcbb36cfa237
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366807"
---
# <a name="walkthrough-matrix-multiplication"></a>İzlenecek yol: Matris Çarpım

Bu adım adım gözden geçirme, matris çarpımının gerçekleştirilmeye nasıl hızlandırılabildiğini gösterir. İki algoritma, bir fayans ve fayans ile bir sunulmaktadır.

## <a name="prerequisites"></a>Ön koşullar

Başlamadan önce:

- [C++ AMP Genel Bakış'ı](../../parallel/amp/cpp-amp-overview.md)okuyun.

- [Kutucukları Kullanarak](../../parallel/amp/using-tiles.md)Okuyun.

- En az Windows 7 veya Windows Server 2008 R2 çalıştırdığınızdan emin olun.

### <a name="to-create-the-project"></a>Proje oluşturmak için

Yeni bir proje oluşturma yönergeleri Visual Studio'nun hangi sürümünü yüklediğinize bağlı olarak değişir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-the-project-in-visual-studio-2019"></a>Visual Studio 2019'da proje oluşturmak

1. Menü çubuğunda, **Yeni Proje Oluştur** iletişim kutusunu açmak için **Yeni** > **Proje** **Dosyası'nı** > seçin.

1. İletişim kutusunun üst kısmında, **Dil'i** **C++** olarak ayarlayın, **Platform'u** **Windows'a**ayarlayın ve **Project türünü** **Konsol'a**ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **Boş Proje'yi** seçin ve **ardından İleri'yi**seçin. Bir sonraki sayfada, proje için bir ad belirtmek için **Ad** kutusuna *MatrixMultiply'i* girin ve istenirse proje konumunu belirtin.

   ![Yeni konsol uygulaması](../../build/media/mathclient-project-name-2019.png "Yeni konsol uygulaması")

1. İstemci projesini oluşturmak için **Oluştur** düğmesini seçin.

1. **Çözüm Gezgini'nde,** Kaynak **Dosyalar**için kısayol menüsünü açın ve ardından **Yeni Öğe** **Ekle'yi** > seçin.

1. Yeni **Öğe Ekle** iletişim kutusunda **C++ Dosyası (.cpp) seçeneğini**belirleyin, **Ad** kutusuna *MatrixMultiply.cpp* girin ve sonra **Ekle** düğmesini seçin.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-project-in-visual-studio-2017-or-2015"></a>Visual Studio 2017 veya 2015'te bir proje oluşturmak için

1. Visual Studio'daki menü çubuğunda **Yeni** > **Dosya** > **Projesi'ni**seçin.

1. **Şablonlar** bölmesinde Yüklü altında **Visual C++** seçeneğini belirleyin.

1. **Boş Proje'yi**seçin, **Ad** kutusuna *MatrixMultiply'i* girin ve ardından **Tamam** düğmesini seçin.

1. **İleri** düğmesini seçin.

1. **Çözüm Gezgini'nde,** Kaynak **Dosyalar**için kısayol menüsünü açın ve ardından **Yeni Öğe** **Ekle'yi** > seçin.

1. Yeni **Öğe Ekle** iletişim kutusunda **C++ Dosyası (.cpp) seçeneğini**belirleyin, **Ad** kutusuna *MatrixMultiply.cpp* girin ve sonra **Ekle** düğmesini seçin.

::: moniker-end

## <a name="multiplication-without-tiling"></a>Fayans olmadan çarpma

Bu bölümde, aşağıdaki gibi tanımlanan iki matris, A ve B, çarpılması düşünün:

![&#45;2 matris A tarafından 3&#45;](../../parallel/amp/media/campmatrixanontiled.png "&#45;2 matris A tarafından 3&#45;")

![2&#45;3 matris B tarafından&#45;](../../parallel/amp/media/campmatrixbnontiled.png "2&#45;3 matris B tarafından&#45;")

A 3'e 2 matris, B ise 2'ye 3 matristir. A'yı B ile çarpmanın çarpımı aşağıdaki 3'e 3 matristir. Ürün, A satırlarının B öğesisütunları ile elemanla çarpılmasıyla hesaplanır.

![3 ürün matrisi&#45;3&#45;](../../parallel/amp/media/campmatrixproductnontiled.png "3 ürün matrisi&#45;3&#45;")

### <a name="to-multiply-without-using-c-amp"></a>C++ AMP kullanmadan çarpmak için

1. MatrixMultiply.cpp'yi açın ve varolan kodu değiştirmek için aşağıdaki kodu kullanın.

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

   Algoritma matris çarpma tanımının basit bir uygulamasıdır. Hesaplama süresini azaltmak için herhangi bir paralel veya iş parçacığı algoritması kullanmaz.

1. Menü çubuğunda**Tümlerini Kaydet'i** **seçin.** > 

1. Hata ayıklamaya başlamak ve çıktının doğru olup olmadığını doğrulamak için **F5** klavye kısayolu'nu seçin.

1. Uygulamadan çıkmak için **Enter'u** seçin.

### <a name="to-multiply-by-using-c-amp"></a>C++ AMP kullanarak çarpmak için

1. MatrixMultiply.cpp'de yöntemden `main` önce aşağıdaki kodu ekleyin.

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

   AMP kodu AMP olmayan kodu andırır. Arama, `parallel_for_each` her öğe `product.extent`için bir iş parçacığı `for` başlatır ve satır ve sütun için döngüler değiştirir. Satır ve sütundaki hücrenin değeri `idx`. İşleç ve dizin değişkeni veya `array_view` `()` işleç ve satır ve sütun değişkenlerini kullanarak nesnenin öğelerine erişebilirsiniz. `[]` Örnek, her iki yöntemi de gösterir. Yöntem, `array_view::synchronize` `product` değişkenin değerlerini `productMatrix` değişkene kopyalar.

1. MatrixMultiply.cpp'nin üst kısmındaaşağıdaki `include` leri ve `using` ifadeleri ekleyin.

   ```cpp
   #include <amp.h>
   using namespace concurrency;
   ```

1. `main` Yöntemi çağırmak için `MultiplyWithAMP` yöntemi değiştirin.

   ```cpp
   int main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       getchar();
   }
   ```

1. Hata ayıklamaya başlamak ve çıktının doğru olup olmadığını doğrulamak için **Ctrl**+**F5** klavye kısayolu'na basın.

1. Uygulamadan çıkmak için **Spacebar** tuşuna basın.

## <a name="multiplication-with-tiling"></a>Fayans ile çarpma

Döşeme, verileri döşeme olarak bilinen eşit boyutlu alt kümelere bölmeniz indeki bir tekniktir. Fayans kullandığınızda üç şey değişir.

- Değişkenler `tile_static` oluşturabilirsiniz. Uzaydaki `tile_static` verilere erişim, küresel alandaki verilere erişimden kat kat daha hızlı olabilir. Her döşeme `tile_static` için bir değişken örneği oluşturulur ve döşemedeki tüm iş parçacıkları değişkene erişebilir. Fayans birincil yararı `tile_static` erişim nedeniyle performans artışı.

- [Tile_barrier çağırabilirsiniz::belirli](reference/tile-barrier-class.md#wait) bir kod satırında tek bir döşemedeki tüm iş parçacıklarını durdurmak için bekleme yöntemi. İş parçacıklarının çalışacağı sırayı garanti edemezsiniz, yalnızca bir döşemedeki tüm iş parçacıklarının `tile_barrier::wait` yürütmeye devam etmeden önce çağrıda duracağını garanti edemezsiniz.

- Tüm `array_view` nesneye göre iş parçacığı dizine ve döşemeye göre dizine erişiminiz var. Yerel dizini kullanarak, kodunuzu okumayı ve hata ayıklamayı kolaylaştırabilirsiniz.

Matris çarpımında döşemeden yararlanmak için algoritmanın matrisi karolara bölmesi `tile_static` ve daha hızlı erişim için döşeme verilerini değişkenlere kopyalaması gerekir. Bu örnekte, matris eşit boyutta submatrices bölümlenir. Ürün submatrices çarpılarak bulunur. Bu örnekte iki matris ve bunların ürünü şunlardır:

![4&#45;&#45;4 matris A](../../parallel/amp/media/campmatrixatiled.png "4&#45;&#45;4 matris A")

![4&#45;&#45;4 matris B](../../parallel/amp/media/campmatrixbtiled.png "4&#45;&#45;4 matris B")

![4 ürün matrisinin&#45;4&#45;](../../parallel/amp/media/campmatrixproducttiled.png "4 ürün matrisinin&#45;4&#45;")

Matrisler aşağıdaki gibi tanımlanan dört 2x2 matris, ayrılır:

![4&#45;4 matris tarafından 4&#45;2 2 alt&#45;matris&#45;ler tarafından 2&#45;bölümlenmiş](../../parallel/amp/media/campmatrixapartitioned.png "4&#45;4 matris tarafından 4&#45;2 2 alt&#45;matris&#45;ler tarafından 2&#45;bölümlenmiş")

![4&#45;&#45;4 matris B 2 alt&#45;matrisler tarafından&#45;&#45;bölümlenmiş](../../parallel/amp/media/campmatrixbpartitioned.png "4&#45;&#45;4 matris B 2 alt&#45;matrisler tarafından&#45;&#45;bölümlenmiş")

A ve B'nin ürünü artık aşağıdaki gibi yazılabilir ve hesaplanabilir:

![4&#45;&#45;4 matris A B 2&#45;&#45;2 alt&#45;matrisler tarafından bölümlenmiş](../../parallel/amp/media/campmatrixproductpartitioned.png "4&#45;&#45;4 matris A B 2&#45;&#45;2 alt&#45;matrisler tarafından bölümlenmiş")

Matrisler `a` 2x2 `h` matrice olduğundan, tüm ürünler ve bunların toplamları da 2x2 matris vardır. Ayrıca, A ve B ürününün beklendiği gibi 4x4 matris ilerler. Algoritmayı hızlı bir şekilde denetlemek için, ilk satırdaki öğenin değerini, üründeki ilk sütunu hesaplayın. Örnekte, bu ilk satırve ilk sütundaki öğenin değeri `ae + bg`olacaktır. Yalnızca ilk sütunu, ilk satırı `ae` ve `bg` her dönem için hesaplamanız gerekir. Bu `ae` `(1 * 1) + (2 * 5) = 11`değer. Değeri `bg` . `(3 * 1) + (4 * 5) = 23` Son değer `11 + 23 = 34`, doğrudur.

Bu algoritmayı uygulamak için, kod:

- Çağrıda `tiled_extent` nesne yerine `extent` nesne kullanır. `parallel_for_each`

- Çağrıda `tiled_index` nesne yerine `index` nesne kullanır. `parallel_for_each`

- Submatrices tutmak için değişkenler oluşturur. `tile_static`

- Submatrices ürünlerinin hesaplanması için konuları durdurmak için `tile_barrier::wait` yöntemi kullanır.

### <a name="to-multiply-by-using-amp-and-tiling"></a>AMP ve fayans kullanarak çarpmak için

1. MatrixMultiply.cpp'de yöntemden `main` önce aşağıdaki kodu ekleyin.

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

   Bu örnek, döşeme olmadan örnek önemli ölçüde farklıdır. Kod şu kavramsal adımları kullanır:
   1. Kiremit[0,0] öğelerini `a` `locA`kopyalayın. Kiremit[0,0] öğelerini `b` `locB`kopyalayın. Döşenmiş olduğuna `a` dikkat `b`edin, `product` değil ve. Bu nedenle, erişmek `a, b`için genel endeksleri kullanırsınız ve `product`. Çağrı `tile_barrier::wait` çok önemli. Her ikisi de `locA` `locB` doldurulana kadar döşemedeki tüm iş parçacıklarını durdurur.

   1. `locA` Çarpın `locB` ve sonuçları `product`.

   1. Kiremit[0,1] öğelerini `a` `locA`kopyalayın. Döşeme [1,0] öğelerini `b` kopyalayın. `locB`

   1. `locA` Çarpın `locB` ve bunları zaten bulunan `product`sonuçlara ekleyin.

   1. Kiremit[0,0] çarpımı tamamlandı.

   1. Diğer dört fayans için tekrarlayın. Karolar için özel bir dizin oluşturma yoktur ve iş parçacıkları herhangi bir sırada çalıştırılabilir. Her iş parçacığı yürütülür gibi, `tile_static` değişkenler uygun her döşeme `tile_barrier::wait` için oluşturulur ve program akışını kontrol etmek için çağrı.

   1. Algoritmayı yakından incelerken, her alt matrisin bir `tile_static` belleğe iki kez yüklendiğini fark edin. Bu veri aktarımı zaman alır. Ancak, veriler bellekte `tile_static` olduğunda, verilere erişim çok daha hızlıdır. Ürünlerin hesaplanması submatrices değerlerine tekrar tekrar erişim gerektirdiğinden, genel bir performans kazancı vardır. Her algoritma için, en iyi algoritmayı ve döşeme boyutunu bulmak için deneme gereklidir.

   AMP olmayan ve döşemeolmayan örneklerde, Ürünü hesaplamak için A ve B'nin her öğesine global bellekten dört kez erişilir. Döşeme örneğinde, her öğeye genel bellekten iki kez ve `tile_static` bellekten dört kez erişilir. Bu önemli bir performans artışı değil. Ancak, A ve B 1024x1024 matris ve kiremit boyutu 16 olsaydı, önemli bir performans artışı olurdu. Bu durumda, her öğe `tile_static` yalnızca 16 kez belleğe kopyalanır ve bellekten `tile_static` 1024 kez erişilir.

1. Gösterildiği gibi `MultiplyWithTiling` yöntemi çağırmak için ana yöntemi değiştirin.

   ```cpp
   int main() {
       MultiplyWithOutAMP();
       MultiplyWithAMP();
       MultiplyWithTiling();
       getchar();
   }
   ```

1. Hata ayıklamaya başlamak ve çıktının doğru olup olmadığını doğrulamak için **Ctrl**+**F5** klavye kısayolu'na basın.

1. Uygulamadan çıkmak için **Boşluk** çubuğuna basın.

## <a name="see-also"></a>Ayrıca bkz.

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[İzlenecek yol: C++ AMP Uygulamasında Hata Ayıklama](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)
