---
title: Döşemeleri kullanma | Microsoft Docs
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: acb86a86-2b7f-43f1-8fcf-bcc79b21d9a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c02b5d558ccf2c1353e96dd1990b6d4178457aa
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121955"
---
# <a name="using-tiles"></a>Döşemeleri Kullanma

Döşeme uygulamanızı ivmesini en üst düzeye çıkarmak için kullanabilirsiniz. Döşeme böler iş parçacığı eşit dikdörtgen alt kümeler veya *kutucukları*. Uygun döşeme boyutunu ve döşeli algoritması kullanırsanız, C++ AMP kodunuzdan daha da fazla hızlandırma alabilirsiniz. Döşeme temel bileşeni vardır:

- `tile_static` değişkenleri. Döşeme birincil avantajı gelen performans kazancı var mı `tile_static` erişim. Veri erişimi `tile_static` bellek genel alan veri erişimi önemli ölçüde daha hızlı olabilir (`array` veya `array_view` nesneleri). Örneği bir `tile_static` değişken her bölme için oluşturulur ve tüm iş parçacıklarının döşemesinin değişkeni erişimi. Veri kopyalanır tipik döşeli algoritmada `tile_static` genel bellek kez bellekten ve birçok kez sonra erişilen `tile_static` bellek.

- [tile_barrier::wait yöntemi](reference/tile-barrier-class.md#wait). Çağrı `tile_barrier::wait` tüm iş parçacıklarının aynı döşemesinin çağrısı ulaşana kadar geçerli iş parçacığının durduran `tile_barrier::wait`. İş parçacığı çalıştıracak, yalnızca o iş parçacığı döşemesinin çağrısı geçmiş yürütecek sırayı garanti edemez `tile_barrier::wait` kadar tüm iş parçacıklarının çağrı üst sınırına ulaştınız. Kullanarak buna `tile_barrier::wait` yöntemi, bir iş parçacığı tarafından iş parçacığı başına yerine döşemesi tarafından döşeme temel görevleri gerçekleştirebilir. Başlatmak için kod tipik döşeme algoritmasına sahip `tile_static` bir çağrı tarafından izlenen tüm döşeme için bellek `tile_barrer::wait`. Aşağıdaki kod `tile_barrier::wait` erişmesi gereken tüm hesaplamalar içeriyor `tile_static` değerleri.

- Yerel ve genel dizin oluşturma. Tüm göreli iş parçacığı dizini erişimi `array_view` veya `array` nesneyi ve dizin döşemeye göre. Yerel dizin kullanarak kodunuzu daha kolay okumak ve hata ayıklama yapabilirsiniz. Genellikle, yerel erişimi dizini oluşturmayı `tile_static` değişkenleri ve genel erişim için dizin oluşturma `array` ve `array_view` değişkenleri.

- [tiled_extent sınıfı](../../parallel/amp/reference/tiled-extent-class.md) ve [tiled_index sınıfı](../../parallel/amp/reference/tiled-index-class.md). Kullandığınız bir `tiled_extent` yerine Nesne bir `extent` nesnesinde `parallel_for_each` çağırın. Kullandığınız bir `tiled_index` yerine Nesne bir `index` nesnesinde `parallel_for_each` çağırın.

Döşeme yararlanmak için algoritma gerekir bilgi işlem etki döşemesine bölümlemek ve ardından kutucuğu verilerini kopyalamak `tile_static` daha hızlı erişim için değişkenleri.

## <a name="example-of-global-tile-and-local-indices"></a>Örnek genel olarak, bölme ve yerel dizinlerini

Aşağıdaki diyagramda bir 8 x 9 matris 2 x 3 döşemeleri düzenlenmiş verilerin temsil eder.

![8&#45;tarafından&#45;9 matris bölünmüş 2&#45;tarafından&#45;3 döşeme](../../parallel/amp/media/usingtilesmatrix.png "usingtilesmatrix")

Aşağıdaki örnek genel kutucuğu görüntüler ve bu yerel dizinlerini matris döşenir. Bir `array_view` nesne türündeki öğeler kullanarak oluşturulur `Description`. `Description` Tutan genel kutucuğu ve yerel dizinlerini Matristeki öğesinin. Kod çağrısında `parallel_for_each` Global değerleri, döşeme ve her öğenin yerel dizinlerini ayarlar. Çıktıyı değerleri görüntüler `Description` yapıları.

```cpp
#include <iostream>
#include <iomanip>
#include <Windows.h>
#include <amp.h>
using namespace concurrency;

const int ROWS = 8;
const int COLS = 9;

// tileRow and tileColumn specify the tile that each thread is in.
// globalRow and globalColumn specify the location of the thread in the array_view.
// localRow and localColumn specify the location of the thread relative to the tile.
struct Description {
    int value;
    int tileRow;
    int tileColumn;
    int globalRow;
    int globalColumn;
    int localRow;
    int localColumn;
};

// A helper function for formatting the output.
void SetConsoleColor(int color) {
    int colorValue = (color == 0)  4 : 2;
    SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE), colorValue);
}

// A helper function for formatting the output.
void SetConsoleSize(int height, int width) {
    COORD coord;
    
    coord.X = width;
    coord.Y = height;
    SetConsoleScreenBufferSize(GetStdHandle(STD_OUTPUT_HANDLE), coord);
    
    SMALL_RECT* rect = new SMALL_RECT();
    rect->Left = 0;
    rect->Top = 0;
    rect->Right = width;
    rect->Bottom = height;
    SetConsoleWindowInfo(GetStdHandle(STD_OUTPUT_HANDLE), true, rect);
}

// This method creates an 8x9 matrix of Description structures.
// In the call to parallel_for_each, the structure is updated
// with tile, global, and local indices.
void TilingDescription() {
    // Create 72 (8x9) Description structures.
    std::vector<Description> descs;
    for (int i = 0; i < ROWS * COLS; i++) {
        Description d = {i, 0, 0, 0, 0, 0, 0};
        descs.push_back(d);
    }

    // Create an array_view from the Description structures.
    extent<2> matrix(ROWS, COLS);
    array_view<Description, 2> descriptions(matrix, descs);

    // Update each Description with the tile, global, and local indices.
    parallel_for_each(descriptions.extent.tile< 2, 3>(),
        [=] (tiled_index< 2, 3> t_idx) restrict(amp)
    {
        descriptions[t_idx].globalRow = t_idx.global[0];
        descriptions[t_idx].globalColumn = t_idx.global[1];
        descriptions[t_idx].tileRow = t_idx.tile[0];
        descriptions[t_idx].tileColumn = t_idx.tile[1];
        descriptions[t_idx].localRow = t_idx.local[0];
        descriptions[t_idx].localColumn= t_idx.local[1];
    });

    // Print out the Description structure for each element in the matrix.
    // Tiles are displayed in red and green to distinguish them from each other.
    SetConsoleSize(100, 150);
    for (int row = 0; row < ROWS; row++) {
        for (int column = 0; column < COLS; column++) {
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);
            std::cout << "Value: " << std::setw(2) << descriptions(row, column).value << "      ";
        }
        std::cout << "\n";

        for (int column = 0; column < COLS; column++) {
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);
            std::cout << "Tile:   " << "(" << descriptions(row, column).tileRow << "," << descriptions(row, column).tileColumn << ")  ";
        }
        std::cout << "\n";

        for (int column = 0; column < COLS; column++) {
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);
            std::cout << "Global: " << "(" << descriptions(row, column).globalRow << "," << descriptions(row, column).globalColumn << ")  ";
        }
        std::cout << "\n";

        for (int column = 0; column < COLS; column++) {
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);
            std::cout << "Local:  " << "(" << descriptions(row, column).localRow << "," << descriptions(row, column).localColumn << ")  ";
        }
        std::cout << "\n";
        std::cout << "\n";
    }
}

void main() {
    TilingDescription();
    char wait;
    std::cin >> wait;
}
```

Örneğin ana iş tanımı içinde bulunan `array_view` nesne ve çağrısı `parallel_for_each`.

1. Vektörü `Description` yapıları bir 8 x 9'a kopyaladığınız `array_view` nesnesi.

2. `parallel_for_each` İle yöntemi çağrıldığında bir `tiled_extent` nesnesi işlem etki alanı olarak. `tiled_extent` Nesne çağırarak oluşturulur `extent::tile()` yöntemi `descriptions` değişkeni. Tür parametreleri çağırma `extent::tile()`, `<2,3>`, 2 x 3 döşeme oluşturduğunu belirtin. Bu nedenle, 8 x 9 matris 12 döşeme, dört satır ve üç sütun döşenir.

3. `parallel_for_each` Kullanarak yöntemi çağrıldığında bir `tiled_index<2,3>` nesne (`t_idx`) dizin olarak. Dizin tür parametreleri (`t_idx`) bilgi işlem etki tür parametrelerini eşleşmesi gerekir (`descriptions.extent.tile< 2, 3>()`).

4. Her iş parçacığı yürütüldüğünde, dizin `t_idx` hangi döşeme hakkında iş parçacığıdır içinde bilgi verir (`tiled_index::tile` özelliği) ve iş parçacığı döşeme içinde konumunu (`tiled_index::local` özelliği).

## <a name="tile-synchronizationtilestatic-and-tilebarrierwait"></a>Döşeme eşitleme — tile_static ve tile_barrier::wait

Önceki örnekte taş düzeni ve dizinlerini gösterir, ancak çok kullanışlı kendisini değil.  Döşeme algoritması ve yararlanma tam sayı olduğunda döşeme kullanışlı hale `tile_static` değişkenleri. Tüm iş parçacıklarının kutucuktaki erişiminiz olduğundan `tile_static` değişkenleri, çağrıları `tile_barrier::wait` erişimi eşitlemek için kullanılan `tile_static` değişkenleri. Tüm iş parçacıklarının kutucuktaki erişimi rağmen `tile_static` değişkenleri, hiçbir garanti edilen iş parçacığı döşemesinin yürütme sırasını yoktur. Aşağıdaki örnekte nasıl kullanılacağını gösterir `tile_static` değişkenleri ve `tile_barrier::wait` her bölme ortalama değerini hesaplamak için yöntem. Örnek anlama anahtarları şunlardır:

1. RawData 8 x 8 matrisinde depolanır.

2. Döşeme boyutunu 2 x 2'dir. Bu kutucuk 4 x 4 kılavuzunun oluşturur ve ortalamalar kullanarak 4 x 4 bir matris depolanabilir bir `array` nesnesi. Yalnızca sınırlı sayıda AMP kısıtlanmış bir işlevde başvuruya yakalayabilirsiniz türleri vardır. `array` Sınıftır biri.

3. Matris boyutu ve örnek boyutu kullanarak tanımlanan `#define` deyimleri, çünkü tür parametreleri `array`, `array_view`, `extent`, ve `tiled_index` sabit değerleri olmalıdır. Aynı zamanda `const int static` bildirimleri. Ek bir avantaj olarak ortalama üzerinde 4 x 4 döşeme hesaplamak için örnek boyutunu değiştirmek için kısmı oldukça kolaydır.

4. A `tile_static` 2 x 2 float değerleri dizisi her bölme için bildirildi. Her iş parçacığı için kod yolunda bildirimi olmasına rağmen yalnızca bir dizi Matristeki her bölme için oluşturulur.

5. Kod her bölme için değerleri kopyalamak için bir satır vardır `tile_static` dizi. Her iş parçacığı için iş parçacığı üzerinde yürütme değer dizisine kopyalandıktan sonra çağrısı nedeniyle durdurur. `tile_barrier::wait`.

6. Tüm iş parçacıklarının kutucuktaki engel ulaştığınızda, ortalama hesaplanabilir. Her iş parçacığı için kodu yürütür olduğundan, bir `if` yalnızca bir iş parçacığında ortalamayı hesaplamak için deyimi. Ortalama ortalamalar değişkende depolanır. Kullanabileceğinize kadar engel döşemesi tarafından hesaplamalar denetleyen temelde yapıdır bir `for` döngü.

7. Verileri `averages` değişken, çünkü bir `array` nesne, ana bilgisayara kopyalanmalıdır. Bu örnek vektör dönüşüm işleci kullanır.

8. Tam örnek kodu doğru hiçbir bir değişiklik yapmadan yürütür ve 4'e SAMPLESIZE değiştirebilirsiniz.

```cpp
#include <iostream>
#include <amp.h>
using namespace concurrency;

#define SAMPLESIZE 2
#define MATRIXSIZE 8
void SamplingExample() {

    // Create data and array_view for the matrix.
    std::vector<float> rawData;
    for (int i = 0; i < MATRIXSIZE * MATRIXSIZE; i++) {
        rawData.push_back((float)i);
    }
    extent<2> dataExtent(MATRIXSIZE, MATRIXSIZE);
    array_view<float, 2> matrix(dataExtent, rawData);

    // Create the array for the averages.
    // There is one element in the output for each tile in the data.
    std::vector<float> outputData;
    int outputSize = MATRIXSIZE / SAMPLESIZE;
    for (int j = 0; j < outputSize * outputSize; j++) {
        outputData.push_back((float)0);
    }
    extent<2> outputExtent(MATRIXSIZE / SAMPLESIZE, MATRIXSIZE / SAMPLESIZE);
    array<float, 2> averages(outputExtent, outputData.begin(), outputData.end());

    // Use tiles that are SAMPLESIZE x SAMPLESIZE.
    // Find the average of the values in each tile.
    // The only reference-type variable you can pass into the parallel_for_each call
    // is a concurrency::array.
    parallel_for_each(matrix.extent.tile<SAMPLESIZE, SAMPLESIZE>(),
        [=, &averages] (tiled_index<SAMPLESIZE, SAMPLESIZE> t_idx) restrict(amp)
    {
        // Copy the values of the tile into a tile-sized array.
        tile_static float tileValues[SAMPLESIZE][SAMPLESIZE];
        tileValues[t_idx.local[0]][t_idx.local[1]] = matrix[t_idx];

        // Wait for the tile-sized array to load before you calculate the average.
        t_idx.barrier.wait();

        // If you remove the if statement, then the calculation executes for every
        // thread in the tile, and makes the same assignment to averages each time.
        if (t_idx.local[0] == 0 && t_idx.local[1] == 0) {
            for (int trow = 0; trow < SAMPLESIZE; trow++) {
                for (int tcol = 0; tcol < SAMPLESIZE; tcol++) {
                    averages(t_idx.tile[0],t_idx.tile[1]) += tileValues[trow][tcol];
                }
            }
            averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE * SAMPLESIZE);
        }
    });

    // Print out the results.
    // You cannot access the values in averages directly. You must copy them
    // back to a CPU variable.
    outputData = averages;
    for (int row = 0; row < outputSize; row++) {
        for (int col = 0; col < outputSize; col++) {
            std::cout << outputData[row*outputSize + col] << " ";
        }
        std::cout << "\n";
    }
    // Output for SAMPLESSIZE = 2 is:
    //  4.5  6.5  8.5 10.5
    // 20.5 22.5 24.5 26.5
    // 36.5 38.5 40.5 42.5
    // 52.5 54.5 56.5 58.5

    // Output for SAMPLESIZE = 4 is:
    // 13.5 17.5
    // 45.5 49.5
}

int main() {
    SamplingExample();
}
```

## <a name="race-conditions"></a>Yarış durumları

Oluşturmak için tempting olabilir bir `tile_static` adlı değişken `total` ve bu gibi her iş parçacığı için bu değişkeni Artır:

```cpp
// Do not do this.
tile_static float total;
total += matrix[t_idx];
t_idx.barrier.wait();

averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);
```

Bu yaklaşım ilk sorun olan `tile_static` değişkenleri başlatıcıları sahip olamaz. İkinci sorun bir yarış durumu atamayı üzerinde olmasıdır `total`, tüm iş parçacıklarının döşemesinin değişkeni belirli bir sırada erişiminiz olduğundan. Her engel adresindeki toplam erişmek tek bir iş parçacığı sonraki gösterildiği gibi yalnızca izin vermek için bir algoritma program. Ancak, bu çözüm Genişletilebilir değil.

```cpp
// Do not do this.
tile_static float total;
if (t_idx.local[0] == 0&& t_idx.local[1] == 0) {
    total = matrix[t_idx];
}
t_idx.barrier.wait();

if (t_idx.local[0] == 0&& t_idx.local[1] == 1) {
    total += matrix[t_idx];
}
t_idx.barrier.wait();

// etc.
```

## <a name="memory-fences"></a>Bellek dilimleri

Eşitlenmesi gereken bellek erişimleri iki tür vardır: genel bellek erişimi ve `tile_static` bellek erişimi. A `concurrency::array` nesne yalnızca genel bellek ayırır. A `concurrency::array_view` genel bellek başvurabilir `tile_static` bellek ya da her ikisini nasıl oluşturulan bağlı olarak.  Eşitlenmesi gereken bellek iki tür vardır:

- Genel bellek

- `tile_static`

A *bellek sınırı* erişir, iş parçacığı döşemesinin başka bir iş parçacığı kullanılabilir belleğin ve erişimleri program sırasına göre çalıştırılır belleğin sağlar. Bu emin olmak için derleyicileri ve işlemci okuma ve yazma işlemleri arasında dilimi yeniden değil. C++ AMP içinde bellek sınırı bu yöntemlerden biri için bir çağrı tarafından oluşturulur:

- [tile_barrier::wait yöntemi](reference/tile-barrier-class.md#wait): her ikisi de geçici bir dilimi genel oluşturur ve `tile_static` bellek.

- [tile_barrier::wait_with_all_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_all_memory_fence): her ikisi de geçici bir dilimi genel oluşturur ve `tile_static` bellek.

- [tile_barrier::wait_with_global_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_global_memory_fence): yalnızca genel bellek geçici bir sınırı oluşturur.

- [tile_barrier::wait_with_tile_static_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_tile_static_memory_fence): yalnızca geçici bir sınırı oluşturur `tile_static` bellek.

Uygulamanızın performansını artırabilir gerektiren belirli dilimi çağrılıyor. Engeli türü, derleyici ve donanım deyimleri nasıl yeniden etkiler. Örneğin, bir genel bellek sınırı kullanırsanız, yalnızca genel bellek erişimleri uygulanır ve bu nedenle, derleyici ve donanım yeniden okuyan ve yazan `tile_static` dilimi iki tarafında değişkenleri.

Sonraki örnekte engel yazmaları eşitler `tileValues`, `tile_static` değişkeni. Bu örnekte, `tile_barrier::wait_with_tile_static_memory_fence` yerine adlı `tile_barrier::wait`.

```cpp
// Using a tile_static memory fence.
parallel_for_each(matrix.extent.tile<SAMPLESIZE, SAMPLESIZE>(),
    [=, &averages] (tiled_index<SAMPLESIZE, SAMPLESIZE> t_idx) restrict(amp)
{
    // Copy the values of the tile into a tile-sized array.
    tile_static float tileValues[SAMPLESIZE][SAMPLESIZE];
    tileValues[t_idx.local[0]][t_idx.local[1]] = matrix[t_idx];

    // Wait for the tile-sized array to load before calculating the average.
    t_idx.barrier.wait_with_tile_static_memory_fence();

    // If you remove the if statement, then the calculation executes
    // for every thread in the tile, and makes the same assignment to
    // averages each time.
    if (t_idx.local[0] == 0&& t_idx.local[1] == 0) {
        for (int trow = 0; trow <SAMPLESIZE; trow++) {
            for (int tcol = 0; tcol <SAMPLESIZE; tcol++) {
                averages(t_idx.tile[0],t_idx.tile[1]) += tileValues[trow][tcol];
            }
        }
    averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);
    }
});
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
[tile_static Anahtar Sözcüğü](../../cpp/tile-static-keyword.md)  
