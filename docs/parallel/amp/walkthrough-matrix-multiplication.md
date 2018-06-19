---
title: 'İzlenecek yol: Matris çarpım | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 61172e8b-da71-4200-a462-ff3a908ab0cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0c61bff6251d5ae833611161ef7b1bb06e6f39a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693201"
---
# <a name="walkthrough-matrix-multiplication"></a>İzlenecek yol: Matris Çarpım
Bu adım adım C++ AMP matris çarpım yürütülmesi hızlandırmak için nasıl kullanılacağını gösterir. İki algoritmaları sunulur, döşeme olmadan diğeri döşeme ile.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Başlamadan önce:  
  
-   Okuma [C++ AMP'ye genel bakış](../../parallel/amp/cpp-amp-overview.md).  
  
-   Okuma [döşemeleri kullanma](../../parallel/amp/using-tiles.md).  
  
-   Olduğundan emin olun [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/reference/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../../parallel/amp/includes/winsvr08_r2_md.md)], veya [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)] bilgisayarınızda yüklü.  
  
### <a name="to-create-the-project"></a>Proje oluşturmak için  
  
1.  Visual Studio menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  Altında **yüklü** Şablonlar bölmesinde seçin **Visual C++**.  
  
3.  Seçin **boş proje**, girin `MatrixMultiply` içinde **adı** kutusuna ve ardından **Tamam** düğmesi.  
  
4.  Seçin **sonraki** düğmesi.  
  
5.  İçinde **Çözüm Gezgini**, kısayol menüsünü açın **kaynak dosyaları**ve ardından **Ekle**, **yeni öğe**.  
  
6.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **C++ dosyasına (.cpp)**, girin `MatrixMultiply.cpp` içinde **adı** kutusuna ve ardından **Ekle** düğme.  
  
## <a name="multiplication-without-tiling"></a>Çarpma döşeme olmadan  
 Bu bölümde, iki matrisi, şu şekilde tanımlanır A ve B çarpma göz önünde bulundurun:  
  
 ![3&#45;tarafından&#45;2 matris](../../parallel/amp/media/campmatrixanontiled.png "campmatrixanontiled")  
  
 ![2&#45;tarafından&#45;3 matris](../../parallel/amp/media/campmatrixbnontiled.png "campmatrixbnontiled")  
  
 A 2 tarafından 3 matris ve B 2 ile 3 matris. Aşağıdaki 3 x 3 matris B tarafından çarpılması bir üründür. Ürün bir satır B öğe sütunlara göre çarpılmasıyla hesaplanır.  
  
 ![3&#45;tarafından&#45;3 matris](../../parallel/amp/media/campmatrixproductnontiled.png "campmatrixproductnontiled")  
  
### <a name="to-multiply-without-using-c-amp"></a>C++ AMP kullanmadan çarpılacağı  
  
1.  MatrixMultiply.cpp açın ve var olan kodu değiştirmek için aşağıdaki kodu kullanın.  
  
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
  
    The algorithm is a straightforward implementation of the definition of matrix multiplication. It does not use any parallel or threaded algorithms to reduce the computation time.  
  
2.  Menü çubuğunda seçin **dosya**, **Tümünü Kaydet**.  
  
3.  Hata ayıklamayı başlatma ve çıkış doğru olduğunu doğrulamak için F5 klavye kısayolu seçin.  
  
4.  Uygulamadan çıkmak için Enter seçin.  
  
### <a name="to-multiply-by-using-c-amp"></a>C++ AMP kullanarak çarpılacağı  
  
1.  MatrixMultiply.cpp önce aşağıdaki kodu ekleyin `main` yöntemi.  
  
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
  
    The AMP code resembles the non-AMP code. The call to `parallel_for_each` starts one thread for each element in `product.extent`, and replaces the `for` loops for row and column. The value of the cell at the row and column is available in `idx`. You can access the elements of an `array_view` object by using either the `[]` operator and an index variable, or the `()` operator and the row and column variables. The example demonstrates both methods. The `array_view::synchronize` method copies the values of the `product` variable back to the `productMatrix` variable.  
  
2.  Aşağıdakileri ekleyin `include` ve `using` deyimleri MatrixMultiply.cpp üstünde.  
  
```cpp  
#include <amp.h>  
using namespace concurrency;  
```  
  
3.  Değiştirme `main` çağrılacak yöntem `MultiplyWithAMP` yöntemi.  
  
```cpp  
void main() {  
    MultiplyWithOutAMP();  
    MultiplyWithAMP();  
    getchar();  
}  
```  
  
4.  Ctrl + F5 klavye kısayolu hata ayıklamayı Başlat'ı seçin ve çıktı doğru olduğundan emin olun.  
  
5.  Uygulamadan çıkmak için boşluk çubuğu'nu seçin.  
  
## <a name="multiplication-with-tiling"></a>Çarpma ile döşeme  
 Döşeme, kutucukları olarak bilinen eşittir ölçekli alt içine veri bölüm bir tekniktir. Döşeme kullandığınızda üç şey değiştirin.  
  
-   Oluşturabileceğiniz `tile_static` değişkenleri. Veri erişimi `tile_static` alanı birçok kez genel alan veri erişimi daha hızlı olabilir. Örneği bir `tile_static` değişken her bölme için oluşturulur ve tüm iş parçacıklarının döşemesinin değişkeni erişimi. Döşeme birincil avantajı nedeniyle performans kazancı var mı `tile_static` erişim.  
  
-   Çağırabilirsiniz [tile_barrier::wait](reference/tile-barrier-class.md#wait) tüm iş parçacıklarının kodu belirtilen satırında bir döşemesinin durdurmak için yöntem. İş parçacığı, yalnızca çalışacak sırasını garanti edemez tüm iş parçacıklarının bir döşemesinin çağrısı sırasında durdurur `tile_barrier::wait` bunlar yürütme devam etmeden önce.  

  
-   Tüm göreli iş parçacığı dizini erişimi `array_view` nesneyi ve dizin döşemeye göre. Yerel dizini kullanarak, kodunuzu okuyun ve hata ayıklama kolaylaştırabilir.  
  
 Matris çarpım döşeme yararlanmak için algoritma gerekir matris döşemesine bölüm ve kutucuğu verilerini kopyalamak `tile_static` daha hızlı erişim için değişkenleri. Bu örnekte, matris eşit boyutu submatrices bölümlenmiş. Ürün submatrices çarparak bulunur. İki matrisi ve bu örnekte, ürünlerinin şunlardır:  
  
 ![4&#45;tarafından&#45;4 matris](../../parallel/amp/media/campmatrixatiled.png "campmatrixatiled")  
  
 ![4&#45;tarafından&#45;4 matris](../../parallel/amp/media/campmatrixbtiled.png "campmatrixbtiled")  
  
 ![4&#45;tarafından&#45;4 matris](../../parallel/amp/media/campmatrixproducttiled.png "campmatrixproducttiled")  
  
 Matrisleri şu şekilde tanımlanır dört 2 x 2 matrisleri bölümlenir:  
  
 ![4&#45;tarafından&#45;2 bölümlenmiş 4 matris&#45;tarafından&#45;2 alt&#45;matrisleri](../../parallel/amp/media/campmatrixapartitioned.png "campmatrixapartitioned")  
  
 ![4&#45;tarafından&#45;2 bölümlenmiş 4 matris&#45;tarafından&#45;2 alt&#45;matrisleri](../../parallel/amp/media/campmatrixbpartitioned.png "campmatrixbpartitioned")  
  
 Ürün a ve B artık yazılmış ve aşağıdaki gibi hesaplanır:  
  
 ![4&#45;tarafından&#45;2 bölümlenmiş 4 matris&#45;tarafından&#45;2 alt&#45;matrisleri](../../parallel/amp/media/campmatrixproductpartitioned.png "campmatrixproductpartitioned")  
  
 Çünkü matrisleri `a` aracılığıyla `h` 2 x 2 matrislerini, tüm ürünleri ve bunların toplamı ayrıca 2 x 2 matrisleri. Bu da A * B 4 x 4 bir matris olduğunu beklendiği gibi izler. Hızlı bir şekilde algoritma denetlemek için ilk satırın öğesinde, üründeki ilk sütun değerini hesaplayın. Örnekte, olacaktır öğenin değerini ilk satır ve ilk sütunu `ae + bg`. Yalnızca ilk sütun, ilk satırında hesaplanacak olan `ae` ve `bg` her terim için. Bu değer için `ae` olan `1*1 + 2*5 = 11`. Değeri `bg` olan `3*1 + 4*5 = 23`. Son değer `11 + 23 = 34`, doğru olduğu.  
  
 Bu algoritma kodu uygulamak için:  
  
-   Kullanan bir `tiled_extent` yerine Nesne bir `extent` nesnesinde `parallel_for_each` çağırın.  
  
-   Kullanan bir `tiled_index` yerine Nesne bir `index` nesnesinde `parallel_for_each` çağırın.  
  
-   Oluşturur `tile_static` submatrices tutması için değişkenleri.  
  
-   Kullanan `tile_barrier::wait` submatrices ürünleri hesaplamayı için iş parçacıklarını durdurma yöntemi.  
  
### <a name="to-multiply-by-using-amp-and-tiling"></a>AMP kullanma ve döşeme tarafından çarpılacağı  
  
1.  MatrixMultiply.cpp önce aşağıdaki kodu ekleyin `main` yöntemi.  
  
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
  
    1.  [0,0] parçasına öğeleri kopyalama `a` içine `locA`. [0,0] parçasına öğeleri kopyalama `b` içine `locB`. Dikkat `product` döşenir değil, `a` ve `b`. Bu nedenle, genel dizinlerini erişmek için kullandığınız `a, b`, ve `product`. Çağrı `tile_barrier::wait` gereklidir. Erene kadar tüm iş parçacıklarının döşemesinin durdurduğu `locA` ve `locB` doldurulur.  
  
    2.  Çarp `locA` ve `locB` ve sonuçları koyun `product`.  
  
    3.  [0,1] parçasına öğeleri kopyalama `a` içine `locA`. [1,0] parçasına öğeleri kopyalama `b` içine `locB`.  
  
    4.  Çarp `locA` ve `locB` ve bunları zaten adınız sonuçları Ekle `product`.  
  
    5.  Döşeme [0,0] çarpma tamamlanır.  
  
    6.  Diğer dört kutucuk için yineleyin. Yoktur özellikle döşeme için dizin oluşturma ve iş parçacıklarını herhangi bir sırayla çalıştırabilirsiniz. Her iş parçacığı çalıştırır gibi `tile_static` değişkenleri oluşturulan her bölme için uygun şekilde ve çağrısı `tile_barrier::wait` program akışını denetler.  
  
    7.  Algoritma yakından inceleyin gibi her submatrix içine yüklenip yüklenmediğine dikkat edin bir `tile_static` bellek iki kez. Bu veri aktarımı zaman ayırın. Ancak, veri geldiğinde `tile_static` bellek, verilere erişimin çok daha hızlı. Ürünleri hesaplamayı submatrices değerler yinelenen erişim gerektirdiğinden, bir genel performans kazancı yoktur. Her algoritma için en uygun algoritmayı bulmak ve boyutu döşeme için deneme gereklidir.  
  
         AMP olmayan ve kutucuk olmayan örneklerde, her öğeye A ve B ürün hesaplamak için genel bellekten dört kez erişilebilir. Döşeme örnekte, her öğe genel bellekten iki kez ve dört kez erişilen `tile_static` bellek. Bu önemli bir performans kazancı değil. Ancak, A ve B 1024 x 1024 matrisleri ve döşeme boyutu 16 olan, önemli bir performans kazancı olacaktır. Bu durumda, her öğenin içine kopyalanır `tile_static` bellek yalnızca 16 zaman ve erişilen `tile_static` bellek 1024 kez.  
  
2.  Main yöntemini çağırmak için değiştirme `MultiplyWithTiling` gösterildiği gibi yöntemi.  
  
```cpp  
void main() {  
    MultiplyWithOutAMP();  
    MultiplyWithAMP();  
    MultiplyWithTiling();  
    getchar();  
}  
```  
  
3.  Ctrl + F5 klavye kısayolu hata ayıklamayı Başlat'ı seçin ve çıktı doğru olduğundan emin olun.  
  
4.  Uygulamadan çıkmak için Ara çubuğuna seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ AMP (C++ hızlandırılmış yoğun paralellik)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [İzlenecek yol: C++ AMP Uygulamasında Hata Ayıklama](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)

