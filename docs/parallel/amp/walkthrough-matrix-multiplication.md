---
title: 'İzlenecek yol: Matris Çarpım'
ms.date: 11/19/2018
ms.assetid: 61172e8b-da71-4200-a462-ff3a908ab0cf
ms.openlocfilehash: ae86ff5a111348404616c8bb4fecd3bf22afc90c
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176165"
---
# <a name="walkthrough-matrix-multiplication"></a>İzlenecek yol: Matris Çarpım

Bu adım adım izlenecek yol, C++ AMP matris çarpım yürütülmesini hızlandırmak için nasıl kullanılacağını gösterir. İki algoritması sunulur, döşeme olmayan ve döşeme ile.

## <a name="prerequisites"></a>Önkoşullar

Başlamadan önce:

- Okuma [C++ AMP'ye genel bakış](../../parallel/amp/cpp-amp-overview.md).

- Okuma [döşemeleri kullanma](../../parallel/amp/using-tiles.md).

- Windows 7, Windows 8, Windows Server 2008 R2 veya Windows Server 2012, bilgisayarınızda yüklü olduğundan emin olun.

### <a name="to-create-the-project"></a>Proje oluşturmak için

1. Visual Studio menü çubuğunda seçin **dosya** > **yeni** > **proje**.

1. Altında **yüklü** Şablonlar bölmesinde seçin **Visual C++**.

1. Seçin **boş proje**, girin *MatrixMultiply* içinde **adı** kutusuna ve ardından **Tamam** düğmesi.

1. Seçin **sonraki** düğmesi.

1. İçinde **Çözüm Gezgini**, kısayol menüsünü açın **kaynak dosyaları**ve ardından **Ekle** > **yeni öğe**.

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda **C++ dosyası (.cpp)**, girin *MatrixMultiply.cpp* içinde **adı** kutusuna ve ardından  **Ekleme** düğmesi.

## <a name="multiplication-without-tiling"></a>Çarpma döşeme olmadan

Bu bölümde, şu şekilde tanımlanır A ve B olmak üzere iki matrislerde çarpımı göz önünde bulundurun:

![3&#45;tarafından&#45;2 matris A](../../parallel/amp/media/campmatrixanontiled.png "3&#45;tarafından&#45;2 matris A")

![2&#45;tarafından&#45;3 matris B](../../parallel/amp/media/campmatrixbnontiled.png "2&#45;tarafından&#45;3 matris B")

Bir 3-tarafından-2 matris ve B ise 2 x 3 matris. 3-x-3 matris çarpılması A B ürünüdür. Ürün A satırlarını sütun b öğeye göre çarpılarak hesaplanır.

![3&#45;tarafından&#45;3 ürün matris](../../parallel/amp/media/campmatrixproductnontiled.png "3&#45;tarafından&#45;3 ürün Matrisi")

### <a name="to-multiply-without-using-c-amp"></a>C++ AMP kullanmadan çarpmak için

1. MatrixMultiply.cpp açın ve varolan kodu değiştirmek için aşağıdaki kodu kullanın.

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

void main() {
    MultiplyWithOutAMP();
    getchar();
}
```

   Algoritma, matris çarpım tanımını basit bir uygulamadır. Bunu tüm paralel veya iş parçacıklı algoritmaları hesaplama süreyi azaltmak üzere kullanmaz.

1. Menü çubuğunda, **dosya** > **Tümünü Kaydet**.

1. Seçin **F5** klavye kısayolu hata ayıklamayı başlatmak ve çıkış doğru olduğundan emin olun.

1. Seçin **Enter** uygulamadan çıkmak için.

### <a name="to-multiply-by-using-c-amp"></a>C++ AMP kullanarak çarpmak için

1. MatrixMultiply.cpp önce aşağıdaki kodu ekleyin `main` yöntemi.

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

   AMP kodu, AMP olmayan koda benzer. Çağrı `parallel_for_each` her öğe için bir iş parçacığı başlattığını `product.extent`ve değiştirir `for` satır ve sütun for döngüleri. Hücre, satır ve sütun değeri kullanılabilir `idx`. Öğelerine erişebilirsiniz bir `array_view` kullanın ya da nesne `[]` işleci ve bir dizin değişkeni veya `()` işleci ve satır ve sütun değişkenleri. Örnek, her iki yöntem de gösterir. `array_view::synchronize` Yöntemi kopyalar değerlerini `product` geri değişken `productMatrix` değişkeni.

1. Aşağıdaki `include` ve `using` MatrixMultiply.cpp üst kısmındaki deyimleri.

```cpp
#include <amp.h>
using namespace concurrency;
```

1. Değiştirme `main` çağrılacak yöntem `MultiplyWithAMP` yöntemi.

```cpp
void main() {
    MultiplyWithOutAMP();
    MultiplyWithAMP();
    getchar();
}
```

1. Seçin **Ctrl**+**F5** klavye kısayolu hata ayıklamayı başlatmak ve çıkış doğru olduğundan emin olun.

1. Seçin **boşluk** uygulamadan çıkmak için.

## <a name="multiplication-with-tiling"></a>Çarpma ile döşeme

Döşeme içinde halinde kutucuk olarak bilinen eşit boyutlu alt kümeler, veri bölümleme bir tekniktir. Döşeme kullandığınızda üç şeyi değiştirin.

- Oluşturabileceğiniz `tile_static` değişkenleri. Veri erişimi `tile_static` alanı erişim genel alandaki verilere kıyasla çok sayıda kat daha hızlı olabilir. Örneği bir `tile_static` değişken her döşeme için oluşturulur ve döşemedeki tüm iş parçacıkları değişkene erişimi vardır. Birincil döşeme nedeniyle performans kazancı avantajdır `tile_static` erişim.

- Çağırabilirsiniz [tile_barrier::wait](reference/tile-barrier-class.md#wait) belirtilen kod satırında bir döşeme içindeki iş parçacıklarının tümünü durdurmak için yöntemi. İş parçacıklarının, yalnızca çalışacağı sırayı belirleyemezsiniz. tüm iş parçacıklarının bir kutucuk için çağrıda durdurur `tile_barrier::wait` , yürütme devam etmeden önce.

- Dizini iş parçacığının tüm göre erişimi `array_view` nesne ve döşemeye göreceli dizinine. Yerel dizinini kullanarak, kodunuzu ve hata ayıklaması kolaylaştırabilir.

Matris çarpım içinde döşemeden yararlanmak için algoritma gerekir matris döşemesine bölümlemek ve ardından döşeme verilerini kopyalayın `tile_static` değişkenleri daha hızlı erişim için. Bu örnekte, matris eşit boyutta submatrices bölümlenir. Ürün submatrices çarpılarak bulunur. İki matrislerde ve bu örnekte, ürün şunlardır:

![4&#45;tarafından&#45;4 matris A](../../parallel/amp/media/campmatrixatiled.png "4&#45;tarafından&#45;4 matris A")

![4&#45;tarafından&#45;4 matris B](../../parallel/amp/media/campmatrixbtiled.png "4&#45;tarafından&#45;4 matris B")

![4&#45;tarafından&#45;4 ürün matris](../../parallel/amp/media/campmatrixproducttiled.png "4&#45;tarafından&#45;4 ürün Matrisi")

Matrisler şu şekilde tanımlanır dört 2 x 2 matrislerde bölümlenir:

![4&#45;tarafından&#45;4 matris 2 bölümlenmiş bir&#45;tarafından&#45;2 alt&#45;matrislerde](../../parallel/amp/media/campmatrixapartitioned.png "4&#45;tarafından&#45;4 matris 2 bölümlenmiş bir&#45;tarafından&#45;2 alt&#45;Matrisi")

![4&#45;tarafından&#45;4 matris B bölümlenmiş 2&#45;tarafından&#45;2 alt&#45;matrislerde](../../parallel/amp/media/campmatrixbpartitioned.png "4&#45;tarafından&#45;4 matris B bölümlenmiş 2&#45;tarafından&#45;2 alt&#45;Matrisi")

Ürün a ve B artık yazılmış ve şu şekilde hesaplanır:

![4&#45;tarafından&#45;4 matris A B 2 bölümlenmiş&#45;tarafından&#45;2 alt&#45;matrislerde](../../parallel/amp/media/campmatrixproductpartitioned.png "4&#45;tarafından&#45;4 matris A B 2 bölümlenmiş&#45;tarafından&#45;2 alt&#45;Matrisi")

Çünkü matrislerde `a` aracılığıyla `h` 2 x 2 matrisler, tüm ürünlerin ve bunların toplamı de 2 x 2 matrislerde. Ayrıca, takip eden ürün a ve B 4 x 4 matrisi, beklendiği gibi. Algoritma hemen kontrol etmek için ürün ilk sütunda, ilk satırındaki öğenin değerini hesaplayın. Bu örnekte, olacaktır öğenin değeri ilk satır ve ilk sütununu `ae + bg`. Yalnızca ilk sütun, ilk satırında hesaplanacak olan `ae` ve `bg` her dönem. Bu değer için `ae` olduğu `(1 * 1) + (2 * 5) = 11`. Değeri `bg` olduğu `(3 * 1) + (4 * 5) = 23`. Son değer `11 + 23 = 34`, doğru olduğu.

Bu algoritma, kodu uygulamak için:

- Kullanan bir `tiled_extent` yerine Nesne bir `extent` nesnesine `parallel_for_each` çağırın.

- Kullanan bir `tiled_index` yerine Nesne bir `index` nesnesine `parallel_for_each` çağırın.

- Oluşturur `tile_static` submatrices tutması için değişkenleri.

- Kullanan `tile_barrier::wait` submatrices ürünlerin hesaplaması için iş parçacıklarının durdurmak için yöntemi.

### <a name="to-multiply-by-using-amp-and-tiling"></a>AMP kullanarak ve döşeme ile çarpılacak

1. MatrixMultiply.cpp önce aşağıdaki kodu ekleyin `main` yöntemi.

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

    This example is significantly different than the example without tiling. The code uses these conceptual steps:

    1. [0,0] parçasına öğeleri Kopyala `a` içine `locA`. [0,0] parçasına öğeleri Kopyala `b` içine `locB`. Dikkat `product` döşenmiş değil `a` ve `b`. Bu nedenle, genel dizinlerini erişmek için kullandığınız `a, b`, ve `product`. Çağrı `tile_barrier::wait` gereklidir. Erene kadar tüm döşemedeki iş parçacıkları durmadan `locA` ve `locB` doldurulur.

    2. Çarp `locA` ve `locB` ve sonuçları koymak `product`.

    3. [0,1] parçasına öğeleri Kopyala `a` içine `locA`. [1,0] parçasına öğeleri Kopyala `b` içine `locB`.

    4. Çarp `locA` ve `locB` ve önceden yer sonuçları eklemesini `product`.

    5. Kutucuğun [0,0] çarpma işlemi tamamlanmış olur.

    6. Diğer dört kutucuklar için yineleyin. Dizin oluşturma için özel kutucuklar yoktur ve iş parçacığı herhangi bir sırayla çalıştırabilirsiniz. Her iş parçacığı yürütme sırasında `tile_static` değişkenleri oluşturulan her bölme için uygun şekilde ve çağrısı `tile_barrier::wait` program akışını denetler.

    7. Algoritma yakından incelemek gibi her submatrix yüklendiği fark bir `tile_static` iki kez bellek. Bu veri aktarımı uzun mu sürer. Ancak, veriler sonra `tile_static` bellek, verilere erişim çok daha hızlı. Ürünleri hesaplama submatrices değerleri yinelenen erişim gerektirdiğinden, genel bir performans kazancı yoktur. Her bir algoritmanın deneme en iyi algoritmayı bulup döşeme boyutu gereklidir.

         AMP olmayan ve döşeme olmayan örneklerde, her öğe a ve B ürün hesaplamak için genel bellekten dört kez erişilebilir. Kutucuk örnekte, her öğe genel bellekten iki kez ve dört kez erişilen `tile_static` bellek. Bu önemli bir performans kazancı değil. Ancak, A ve B 1024 x 1024, matrislerde ve döşeme boyutu 16 olan, önemli bir performans kazancı olacaktır. Bu durumda, her öğe içine kopyalanacak `tile_static` bellek yalnızca 16 erişilen ve kat `tile_static` bellek 1024 kez.

2. Main yöntemini çağırmak için değiştirme `MultiplyWithTiling` gösterildiği yöntemi.

```cpp
void main() {
    MultiplyWithOutAMP();
    MultiplyWithAMP();
    MultiplyWithTiling();
    getchar();
}
```

3. Seçin **Ctrl**+**F5** klavye kısayolu hata ayıklamayı başlatmak ve çıkış doğru olduğundan emin olun.

4. Seçin **alanı** çubuğundaki uygulamadan çıkın.

## <a name="see-also"></a>Ayrıca Bkz.

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[İzlenecek yol: C++ AMP Uygulamasında Hata Ayıklama](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)