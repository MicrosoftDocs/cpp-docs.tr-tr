---
title: Döşemeleri Kullanma
ms.date: 11/19/2018
ms.assetid: acb86a86-2b7f-43f1-8fcf-bcc79b21d9a8
ms.openlocfilehash: e5cedde255846f61ed0aaadacbd9966c00a03c9d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126272"
---
# <a name="using-tiles"></a>Döşemeleri Kullanma

Döşeme kullanarak uygulamanızın hızlandırmasını en üst düzeye çıkarabilirsiniz. İş parçacıklarını, eşit dikdörtgen alt kümelerine veya *döşemelere*böler. Uygun bir kutucuk boyutu ve döşeli algoritma kullanırsanız, C++ amp kodunuzda daha da fazla hızlandırma sağlayabilirsiniz. Döşeme temel bileşenleri şunlardır:

- `tile_static` değişkenleri. Döşeme 'nin birincil avantajı `tile_static` erişimine ait performans kazanımı olur. `tile_static` bellekteki verilere erişim, genel alanda (`array` veya `array_view` nesneleri) verilere erişimden önemli ölçüde daha hızlı olabilir. Her kutucuk için bir `tile_static` değişkeni örneği oluşturulur ve kutucuktaki tüm iş parçacıkları değişkene erişebilir. Tipik bir döşeli algoritmada, veriler genel bellekten bir kez `tile_static` belleğe kopyalanır ve sonra `tile_static` bellekten birçok kez erişilir.

- [tile_barrier:: wait yöntemi](reference/tile-barrier-class.md#wait). `tile_barrier::wait` çağrısı, aynı kutucuktaki tüm iş parçacıkları `tile_barrier::wait`çağrısına ulaşana kadar geçerli iş parçacığının yürütülmesini askıya alır. İş parçacıklarının içinde çalışacağı sırayı garanti edemezsiniz; yalnızca kutucukta iş parçacıklarının, tüm iş parçacıkları çağrıya ulaşana kadar `tile_barrier::wait` çağrısı süresi üzerinden yürütülecektir. Bu, `tile_barrier::wait` yöntemi kullanılarak, iş parçacığı temelinde bir kutucuk temelinde görevler gerçekleştirebileceğiniz anlamına gelir. Tipik bir döşeme algoritması, tüm kutucuk için `tile_static` belleği başlatmak ve ardından `tile_barrier::wait`çağrısı olan kodu içerir. `tile_barrier::wait` aşağıdaki kod, tüm `tile_static` değerlerine erişim gerektiren hesaplamalar içerir.

- Yerel ve Genel dizin oluşturma. Tüm `array_view` veya `array` nesnesi ile ilişkili iş parçacığının dizinine ve kutucuğa göre dizine erişiminiz vardır. Yerel dizini kullanmak, kodunuzun okunmasını ve hata ayıklamasına daha kolay bir hale getirir. Genellikle, `tile_static` değişkenlerine erişmek için yerel dizin oluşturma ve `array` ve `array_view` değişkenlerine erişmek için genel dizin oluşturma kullanırsınız.

- [Tiled_extent sınıfı](../../parallel/amp/reference/tiled-extent-class.md) ve [tiled_index sınıfı](../../parallel/amp/reference/tiled-index-class.md). `parallel_for_each` çağrısındaki bir `extent` nesnesi yerine `tiled_extent` nesnesi kullanırsınız. `parallel_for_each` çağrısındaki bir `index` nesnesi yerine `tiled_index` nesnesi kullanırsınız.

Kutucuktan yararlanmak için, algoritmanız, işlem etki alanını kutucuklara göre bölümleyip kutucuk verilerini daha hızlı erişim için `tile_static` değişkenlere kopyalayamalıdır.

## <a name="example-of-global-tile-and-local-indices"></a>Küresel, kutucuk ve yerel dizinler örneği

Aşağıdaki diyagram, 2x3 kutucuklarında düzenlenmiş bir 8x9 veri matrisini temsil eder.

![8&#45;x&#45;9 matris 2&#45;ile&#45;3 kutucuk bölünmüştür](../../parallel/amp/media/usingtilesmatrix.png "8&#45;x&#45;9 matris 2&#45;ile&#45;3 kutucuk bölünmüştür")

Aşağıdaki örnek, bu döşeli matrisin genel, kutucuk ve yerel dizinlerini görüntüler. `array_view` nesnesi, `Description`türündeki öğeler kullanılarak oluşturulur. `Description` matristeki öğenin genel, döşeme ve yerel dizinlerini barındırır. `parallel_for_each` çağrısındaki kod, her bir öğenin genel, döşeme ve yerel dizinlerinin değerlerini ayarlar. Çıktı, `Description` yapılarında değerleri görüntüler.

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

int main() {
    TilingDescription();
    char wait;
    std::cin >> wait;
}
```

Örneğin ana çalışması `array_view` nesnesinin tanımında ve `parallel_for_each`çağrısının tanımıdır.

1. `Description` yapılarının vektörü 8x9 `array_view` nesnesine kopyalanır.

2. `parallel_for_each` yöntemi, işlem etki alanı olarak bir `tiled_extent` nesnesi ile çağırılır. `tiled_extent` nesnesi, `descriptions` değişkeninin `extent::tile()` yöntemi çağırarak oluşturulur. `extent::tile()`çağrının tür parametreleri `<2,3>`, 2x3 kutucuklarının oluşturulduğunu belirtir. Bu nedenle, 8x9 matrisi 12 kutucuğa, dört satıra ve üç sütuna döşenir.

3. `parallel_for_each` yöntemi, dizin olarak bir `tiled_index<2,3>` nesnesi (`t_idx`) kullanılarak çağrılır. Dizinin tür parametreleri (`t_idx`), işlem etki alanının (`descriptions.extent.tile< 2, 3>()`) tür parametreleriyle eşleşmelidir.

4. Her iş parçacığı yürütüldüğünde Dizin `t_idx`, iş parçacığının hangi kutucuğun (`tiled_index::tile` özelliği) ve kutucuk içindeki iş parçacığının konumunu (`tiled_index::local` özelliği) döndürür.

## <a name="tile-synchronizationtile_static-and-tile_barrierwait"></a>Kutucuk eşitleme — tile_static ve tile_barrier:: wait

Önceki örnekte kutucuk düzeni ve dizinler gösterilmektedir, ancak kendi kendine çok yararlı değildir.  Döşeme, kutucuklar algoritmaya integral olduğunda ve `tile_static` değişkenleriyle yararlandığınızda yararlı olur. Bir kutucuktaki tüm iş parçacıklarının `tile_static` değişkenlere erişimi olduğundan, `tile_barrier::wait` çağrıları `tile_static` değişkenlerine erişimi eşzamanlı hale getirmek için kullanılır. Bir kutucuktaki tüm iş parçacıklarının `tile_static` değişkenlere erişimi olsa da, kutucukta iş parçacıklarının hiçbir garanti edilemez. Aşağıdaki örnek, her kutucuğun ortalama değerini hesaplamak için `tile_static` değişkenlerinin ve `tile_barrier::wait` yönteminin nasıl kullanılacağını gösterir. Örneği anlamak için anahtarlar aşağıda verilmiştir:

1. RawData, 8x8 matrisinde depolanır.

2. Döşeme boyutu 2x2 ' dir. Bu, 4x4 bir kutucuk ızgarası oluşturur ve ortalamalar bir `array` nesnesi kullanılarak bir 4x4 matrisine depolanabilir. Bir AMP kısıtlı işlevinde başvuruya göre yakalayabileceğiniz sınırlı sayıda tür vardır. `array` sınıfı bunlardan biridir.

3. `array`, `array_view`, `extent`ve `tiled_index` için tür parametreleri sabit değerler olması gerektiğinden, matris boyutu ve örnek boyutu `#define` deyimleri kullanılarak tanımlanır. `const int static` bildirimleri de kullanabilirsiniz. Ek bir avantaj olarak, örnek boyutunu değiştirmek önemsiz bir örnektir.

4. Her döşeme için `tile_static` 2x2 bir float değeri dizisi olarak bildirilmiştir. Bildirim her iş parçacığının kod yolunda olsa da, matristeki her kutucuk için yalnızca bir dizi oluşturulur.

5. Her kutucukta değerleri `tile_static` dizisine kopyalamak için bir kod satırı vardır. Her iş parçacığı için, değer diziye kopyalandıktan sonra, `tile_barrier::wait`çağrısı nedeniyle iş parçacığında yürütme durduruluyor.

6. Bir kutucuktaki tüm iş parçacıkları engelle ulaştığında, ortalama hesaplanabilir. Kod her iş parçacığı için yürütüldüğü için, yalnızca bir iş parçacığında ortalamayı hesaplamak için `if` bir ifade vardır. Ortalama, ortalamalar değişkeninde depolanır. Engel, temel olarak, `for` döngüsünü kullanabileceğiniz şekilde, kutucuğa göre hesaplamaları denetleyen yapısıdır.

7. `averages` değişkenindeki veriler, bir `array` nesnesi olduğundan, konağa geri kopyalanmalıdır. Bu örnek, vektör dönüştürme işlecini kullanır.

8. Örnek olarak, Sample boyutunu 4 ' e değiştirebilirsiniz ve kod başka herhangi bir değişiklik yapmadan doğru şekilde yürütülür.

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
    // Output for SAMPLESIZE = 2 is:
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

Bu, `total` adında bir `tile_static` değişkeni oluşturmak ve bu değişkeni, her iş parçacığı için şu şekilde artırmanız olabilir:

```cpp
// Do not do this.
tile_static float total;
total += matrix[t_idx];
t_idx.barrier.wait();

averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);
```

Bu yaklaşımda ilk sorun `tile_static` değişkenlerinin başlatıcılara sahip olamaz. İkinci sorun, `total`atamasında bir yarış durumu olduğu için, kutucuktaki tüm iş parçacıkları belirli bir sıra değişkenine erişim sahibi olduğundan, Bir algoritmayı, ileri ' de gösterildiği gibi, her bir engelte yalnızca bir iş parçacığının toplamına erişmesine izin verecek şekilde programlayabilirsiniz. Ancak bu çözüm genişletilebilir değildir.

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

## <a name="memory-fences"></a>Bellek Balıkonları

Eşitlenmesi gereken, genel bellek erişimi ve `tile_static` bellek erişimi olmak üzere iki tür bellek erişimi vardır. `concurrency::array` nesne yalnızca genel belleği ayırır. Bir `concurrency::array_view`, nasıl oluşturulduğuna bağlı olarak genel belleğe, `tile_static` belleğe veya her ikisine başvurabilir.  Eşitlenmesi gereken iki tür bellek vardır:

- Genel bellek

- `tile_static`

*Bellek sınırı* , bellek erişimlerinin iş parçacığı kutucuğunda diğer iş parçacıkları tarafından kullanılabilmesini sağlar ve bellek erişimleri program sırasına göre yürütülür. Bunu sağlamak için, derleyiciler ve işlemcilerin, parmaklarınızın okuma ve yazma işlemlerini yeniden sıralamayın. AMP C++ 'da, şu yöntemlerden birine yapılan bir çağrı tarafından bir bellek dilimi oluşturulur:

- [tile_barrier:: wait yöntemi](reference/tile-barrier-class.md#wait): hem genel hem de `tile_static` belleği etrafında bir çit oluşturur.

- [tile_barrier:: Wait_with_all_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_all_memory_fence): hem genel hem de `tile_static` belleği etrafında bir çit oluşturur.

- [tile_barrier:: Wait_with_global_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_global_memory_fence): yalnızca genel belleğin etrafında bir çit oluşturur.

- [tile_barrier:: Wait_with_tile_static_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_tile_static_memory_fence): yalnızca `tile_static` belleği etrafında bir çit oluşturur.

İhtiyaç duyduğunuz belirli bir dilimi çağırmak uygulamanızın performansını iyileştirebilirler. Engel türü derleyicinin ve donanım yeniden sıralama deyimlerinin nasıl yapıldığını etkiler. Örneğin, genel bellek sınırı kullanırsanız, bu, yalnızca genel bellek erişimleri için geçerlidir ve bu nedenle, derleyici ve donanım, her iki tarafında `tile_static` değişkenlere okuma ve yazma işlemleri için yeniden sıralama yapılabilir.

Sonraki örnekte, engeli `tileValues`, bir `tile_static` değişkeni olan yazmaları eşitler. Bu örnekte, `tile_barrier::wait`yerine `tile_barrier::wait_with_tile_static_memory_fence` çağırılır.

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
