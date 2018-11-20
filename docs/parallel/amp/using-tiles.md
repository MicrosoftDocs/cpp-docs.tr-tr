---
title: Döşemeleri Kullanma
ms.date: 11/19/2018
ms.assetid: acb86a86-2b7f-43f1-8fcf-bcc79b21d9a8
ms.openlocfilehash: ede62c80a83b5f5fc1d691bf52dde67140e68246
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176100"
---
# <a name="using-tiles"></a>Döşemeleri Kullanma

Döşeme hızlandırma uygulamanızın en üst düzeye çıkarmak için kullanabilirsiniz. Döşeme iş parçacıklarını eşit dikdörtgen altkümelere, böler veya *kutucukları*. Bir uygun döşeme boyutu ve döşemeli algoritma kullanırsanız, C++ AMP kodunuzdan daha fazla hızlandırma alabilirsiniz. Döşeme temel bileşenleri şunlardır:

- `tile_static` değişkenler. Birincil döşeme performans kazancı avantajdır `tile_static` erişim. Veri erişimi `tile_static` bellek erişim genel alandaki verilere kıyasla önemli ölçüde daha hızlı olabilir (`array` veya `array_view` nesneleri). Örneği bir `tile_static` değişken her döşeme için oluşturulur ve döşemedeki tüm iş parçacıkları değişkene erişimi vardır. Tipik bir döşemeli algoritmada veri yoluna kopyalanır `tile_static` genel bellek kez bellekten ve birden çok kez ardından erişilen `tile_static` bellek.

- [tile_barrier::wait yöntemi](reference/tile-barrier-class.md#wait). Bir çağrı `tile_barrier::wait` tüm aynı döşemedeki iş parçacıkları çağrısına erişene kadar geçerli iş parçacığının yürütülmesini askıya `tile_barrier::wait`. İş parçacıklarının çalışacağı, yalnızca o iş parçacığı döşemesindeki çağrısı geçmiş yürütecek sırayı belirleyemezsiniz `tile_barrier::wait` tüm iş parçacıklarının çağrısına erişene kadar. Kullanarak yani `tile_barrier::wait` yöntemi, bir iş parçacığı tarafından iş parçacığı başına yerine bir kutucuk olarak kutucuk temel görevleri gerçekleştirebilirsiniz. Tipik bir döşeme algoritması başlatacak koda sahip `tile_static` bir çağrı tarafından izlenen tüm döşeme için bellek `tile_barrer::wait`. Aşağıdaki kod `tile_barrier::wait` tüm erişim gerektiren hesaplamalar içerir `tile_static` değerleri.

- Yerel ve genel dizin oluşturma. Dizini iş parçacığının tüm göre erişimi `array_view` veya `array` nesne ve döşemeye göreceli dizinine. Yerel dizin kullanmak kodunuzu ve hata ayıklaması daha kolay hale getirebilir. Genellikle, yerel erişim için dizin oluşturma kullanın `tile_static` değişkenleri ve küresel erişim dizin `array` ve `array_view` değişkenleri.

- [tiled_extent sınıfı](../../parallel/amp/reference/tiled-extent-class.md) ve [tiled_index sınıfı](../../parallel/amp/reference/tiled-index-class.md). Kullandığınız bir `tiled_extent` yerine Nesne bir `extent` nesnesine `parallel_for_each` çağırın. Kullandığınız bir `tiled_index` yerine Nesne bir `index` nesnesine `parallel_for_each` çağırın.

Döşemeden yararlanmak için algoritmanız gerekir hesaplama alanı döşemesine bölümlemek ve ardından döşeme verilerini kopyalamak `tile_static` değişkenleri daha hızlı erişim için.

## <a name="example-of-global-tile-and-local-indices"></a>Örnek genel, döşeme ve yerel dizinlerini

Aşağıdaki diyagram 2 x 3 döşemeler şeklinde düzenlenmiş veri bir 8 x 9 matrisi temsil eder.

![8&#45;tarafından&#45;9 matrisi bölünmüş 2&#45;tarafından&#45;3 döşemeler](../../parallel/amp/media/usingtilesmatrix.png "8&#45;tarafından&#45;9 matrisi bölünmüş 2&#45;tarafından&#45;3 kutucukları")

Aşağıdaki örnek, genel, döşeme görüntüler ve döşemeli matrisin yerel dizinlerini gösterir. Bir `array_view` nesnesi türü öğeler kullanarak oluşturulur `Description`. `Description` Tutan genel, döşeme ve yerel dizinlerini Matristeki öğenin. Kod çağrısında `parallel_for_each` genel, döşeme ve yerel dizinlerini her öğenin ayarlar. Çıkış değerleri gösterir `Description` yapıları.

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

1. Vektör `Description` yapıları bir 8x9luk kopyalanır `array_view` nesne.

2. `parallel_for_each` Yöntemi çağrıldığında bir `tiled_extent` hesaplama alanı olarak nesnesi. `tiled_extent` Nesne çağırılarak oluşturulur `extent::tile()` yöntemi `descriptions` değişkeni. Çağrısının tür parametreleri `extent::tile()`, `<2,3>`, 2x3lük döşemelerin oluşturulduğunu belirtir. Bu nedenle, 8 x 9 matrisi 12 kutucuklar, dört satır ve üç sütun döşenir.

3. `parallel_for_each` Yöntemi kullanılarak çağrılır bir `tiled_index<2,3>` nesne (`t_idx`) dizin olarak. Dizin tür parametreleri (`t_idx`) tür parametreleri hesaplama alanı eşleşmelidir (`descriptions.extent.tile< 2, 3>()`).

4. Her iş parçacığı yürütüldüğünde, dizin `t_idx` iş parçacığının hangi döşeme hakkında konusu bilgilerini döndürür (`tiled_index::tile` özelliği) ve iş parçacığının döşeme içindeki konumu (`tiled_index::local` özelliği).

## <a name="tile-synchronizationtilestatic-and-tilebarrierwait"></a>Döşeme eşitleme — tile_static ve tile_barrier::wait

Önceki örnek döşeme yerleşimini ve dizinleri göstermektedir, ancak kendisi çok yararlı değildir.  Kutucukları yararlanma ve algoritma integral olduğunda döşeme yararlı olur `tile_static` değişkenleri. Döşemedeki tüm iş parçacıklarının erişiminiz olduğundan `tile_static` değişkenleri, çağrıları `tile_barrier::wait` erişimi eşitlemek için kullanılan `tile_static` değişkenleri. Tüm iş parçacıklarının bir döşeme içindeki erişimi olsa `tile_static` değişkenleri yürütülme sırası belirli döşeme içindeki iş parçacıklarının yürütülmesini yoktur. Aşağıdaki örnek nasıl kullanılacağını gösterir `tile_static` değişkenleri ve `tile_barrier::wait` her döşemenin ortalama değerini hesaplamak için yöntemi. Örneği anlamak için anahtarlar şunlardır:

1. RawData 8x8lik bir matriste depolanır.

2. Döşeme boyutu 2 x 2'dir. Bu 4 x 4 karelerde döşemeler oluşturur ve ortalamalar bir 4 x 4 matriste kullanılarak depolanabilir bir `array` nesne. AMP kısıtlamalı işlevde başvuruya göre yakalama türleri yalnızca sınırlı sayıda vardır. `array` Sınıfı bunlardan biridir.

3. Matris boyu ve örnek boyu kullanarak tanımlanan `#define` deyimleri, çünkü tür parametreleri `array`, `array_view`, `extent`, ve `tiled_index` sabit değerler olmalıdır. Ayrıca `const int static` bildirimleri. Ek bir avantaj olarak basit bir iş ortalama 4 x 4 kutucukları hesaplamak için örnek boyutunu değiştirin.

4. A `tile_static` 2 x 2 float değeri dizisi her bölme için bildirilir. Bildirim her iş parçacığının kod yolunda olsa da, Matristeki her döşeme için yalnızca bir dizi oluşturulur.

5. Her döşemedeki değerleri kopyalamak için kod satırı yoktur `tile_static` dizisi. Her iş parçacığı için iş parçacığı üzerindeki yürütme değer diziye kopyalandıktan sonra çağrısı nedeniyle durdurulur. `tile_barrier::wait`.

6. Tüm iş parçacıklarının bir döşeme içindeki engele eriştiğinde, ortalama hesaplanabilir. Kod her iş parçacığı için yürütüldüğünden, var olan bir `if` yalnızca bir iş parçacığında ortalamayı hesaplamak için ifade. Ortalama averages değişkeninde depolanır. Kullanabileceğinize kadar engel hesaplamaları kutucuğa göre denetleyen temelde yapıdır bir `for` döngü.

7. Verileri `averages` değişken, çünkü bu bir `array` nesne, ana bilgisayara kopyalanması gerekir. Bu örnek vektör dönüştürme işleci kullanır.

8. Tam bir örnek samplesıze'ı 4'e değiştirebilirsiniz ve kod başka bir değişiklik olmadan doğru bir şekilde yürütür.

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

Oluşturma daha cazip olabilir bir `tile_static` adlı değişken `total` ve böyle her iş parçacığında o değişkeni Artır:

```cpp
// Do not do this.
tile_static float total;
total += matrix[t_idx];
t_idx.barrier.wait();

averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);
```

Bu yaklaşımdaki ilk sorun `tile_static` değişkenlerinin başlatıcıları olamamasıdır. İkinci sorun olduğunu bir yarış durumu atamasında olan `total`, tüm iş parçacıklarının kutucuğunda belirli bir sırada değişkene erişimi vardır. Her engelde, erişmek tek bir iş parçacığı sonraki gösterildiği gibi yalnızca izin vermek için bir algoritma programlayabilirsiniz. Ancak, bu çözüm Genişletilebilir değildir.

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

## <a name="memory-fences"></a>Bellek sınırları

Eşitlenmesi gereken bellek erişimlerinin iki çeşit vardır — genel bellek erişimi ve `tile_static` bellek erişimi. A `concurrency::array` nesnesi yalnızca genel bellek ayırır. A `concurrency::array_view` genel bellek başvurabilirsiniz `tile_static` bellek veya her ikisini de oluşturuluşuna bağlı olarak.  Bellek eşitlenmesi gereken iki çeşit vardır:

- Genel bellek

- `tile_static`

A *bellek sınırı* bu bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları kullanımına sunulur ve bu bellek erişimlerinin program sırasına göre yürütülmesini sağlar. Bunu sağlamak için derleyiciler ve işlemciler okuma ve yazmaları yeniden sıralamaz değil. C++ AMP'ta bir bellek sınırı aşağıdaki yöntemlerden birini yapılan bir çağrıyla oluşturulur:

- [tile_barrier::wait yöntemi](reference/tile-barrier-class.md#wait): her ikisi de etrafında bir sınır genel oluşturur ve `tile_static` bellek.

- [tile_barrier::wait_with_all_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_all_memory_fence): her ikisi de etrafında bir sınır genel oluşturur ve `tile_static` bellek.

- [tile_barrier::wait_with_global_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_global_memory_fence): yalnızca genel bellek etrafında bir sınır oluşturur.

- [tile_barrier::wait_with_tile_static_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_tile_static_memory_fence): yalnızca etrafında bir sınır oluşturur `tile_static` bellek.

Uygulamanızın performansını artırmak ihtiyacınız olan belirli sınırı çağırmak. Engel türü derleyicinin ve donanımın deyimleri nasıl yeniden etkiler. Örneğin, bir genel bellek sınırı kullanırsanız, yalnızca genel bellek erişimine uygulanır ve bu nedenle, derleyici ve donanım yeniden sıralayabilir okuyan ve yazan `tile_static` sınır iki tarafındaki değişkenleri.

Sonraki örnekte, engel için yazmaları eşitler `tileValues`, `tile_static` değişkeni. Bu örnekte, `tile_barrier::wait_with_tile_static_memory_fence` yerine adlı `tile_barrier::wait`.

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

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[tile_static Anahtar Sözcüğü](../../cpp/tile-static-keyword.md)
