---
description: 'Daha fazla bilgi edinin: kutucukları kullanma'
title: Döşemeleri Kullanma
ms.date: 11/19/2018
ms.assetid: acb86a86-2b7f-43f1-8fcf-bcc79b21d9a8
ms.openlocfilehash: 6277faf867cd64e5ea0e4503bb36f8e1d4a8bc74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150169"
---
# <a name="using-tiles"></a>Döşemeleri Kullanma

Döşeme kullanarak uygulamanızın hızlandırmasını en üst düzeye çıkarabilirsiniz. İş parçacıklarını, eşit dikdörtgen alt kümelerine veya *döşemelere* böler. Uygun bir kutucuk boyutu ve döşeli algoritma kullanıyorsanız, C++ AMP kodunuzda daha da fazla hızlandırma sağlayabilirsiniz. Döşeme temel bileşenleri şunlardır:

- `tile_static` değişkenlerinin. Döşeme 'nin birincil avantajı, Access 'ten alınan performans kazanımı olur `tile_static` . Bellekteki verilere erişim `tile_static` , genel alanda ( `array` veya nesnelerinde) verilere erişimden önemli ölçüde daha hızlı olabilir `array_view` . `tile_static`Her kutucuk için bir değişken örneği oluşturulur ve kutucuktaki tüm iş parçacıkları değişkene erişebilir. Tipik bir döşeli algoritmada veriler, `tile_static` genel bellekten bir kez belleğe kopyalanır ve sonra bellekten çok sayıda kez erişilir `tile_static` .

- [tile_barrier:: wait yöntemi](reference/tile-barrier-class.md#wait). ' A Çağrı, `tile_barrier::wait` aynı kutucuktaki tüm iş parçacıkları çağrısına ulaşana kadar geçerli iş parçacığının yürütülmesini askıya alır `tile_barrier::wait` . İş parçacıklarının içinde çalışacağı sırayı garanti edemezsiniz; yalnızca kutucukta iş parçacıklarının, `tile_barrier::wait` tüm iş parçacıkları çağrıya ulaşıncaya kadar çağrının yürütülmeyeceği. Bu, yöntemi kullanılarak, iş parçacığı temelinde, bir kutucuk temelinde `tile_barrier::wait` görevleri yerine getirebilirsiniz. Tipik bir döşeme algoritması, `tile_static` Tüm kutucuk için belleği başlatmak üzere bir kod içerir ve sonra öğesine bir çağrı gelir `tile_barrier::wait` . Aşağıdaki kod `tile_barrier::wait` , tüm değerlere erişim gerektiren hesaplamalar içerir `tile_static` .

- Yerel ve Genel dizin oluşturma. Tüm veya nesnesine göre iş parçacığının dizinine `array_view` `array` ve kutucuğa göre dizine erişiminiz vardır. Yerel dizini kullanmak, kodunuzun okunmasını ve hata ayıklamasına daha kolay bir hale getirir. Genellikle, değişkenlere erişmek için yerel dizin oluşturma `tile_static` ve erişim ve değişkenlere Genel dizin oluşturma `array` kullanırsınız `array_view` .

- [Tiled_extent sınıfı](../../parallel/amp/reference/tiled-extent-class.md) ve [tiled_index sınıfı](../../parallel/amp/reference/tiled-index-class.md). `tiled_extent`Çağrıda bir nesne yerine bir nesne kullanırsınız `extent` `parallel_for_each` . `tiled_index`Çağrıda bir nesne yerine bir nesne kullanırsınız `index` `parallel_for_each` .

Kutucuktan yararlanmak için, algoritmanız, işlem etki alanını kutucuklar halinde bölümleyip kutucuk verilerini `tile_static` daha hızlı erişim için değişkenlere kopyalayamalıdır.

## <a name="example-of-global-tile-and-local-indices"></a>Küresel, kutucuk ve yerel dizinler örneği

Aşağıdaki diyagram, 2x3 kutucuklarında düzenlenmiş bir 8x9 veri matrisini temsil eder.

![&#45;9 matrisine göre 8&#45;&#45;3 kutucuk tarafından 2&#45;bölünmüştür](../../parallel/amp/media/usingtilesmatrix.png "&#45;9 matrisine göre 8&#45;&#45;3 kutucuk tarafından 2&#45;bölünmüştür")

Aşağıdaki örnek, bu döşeli matrisin genel, kutucuk ve yerel dizinlerini görüntüler. Bir `array_view` nesne, türündeki öğeler kullanılarak oluşturulur `Description` . , `Description` Matristeki öğenin genel, döşeme ve yerel dizinlerini tutar. Çağrısındaki kod, `parallel_for_each` her bir öğenin genel, döşeme ve yerel dizinlerinin değerlerini ayarlar. Çıktı, yapıların değerlerini görüntüler `Description` .

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

Örneğin ana çalışması `array_view` nesnenin tanımında ve çağrısının tanımıdır `parallel_for_each` .

1. `Description`Yapıların vektörü 8x9 `array_view` nesnesine kopyalanır.

2. `parallel_for_each`Yöntemi, `tiled_extent` işlem etki alanı olarak bir nesneyle çağrılır. `tiled_extent`Nesnesi, `extent::tile()` değişkeninin metodu çağırarak oluşturulur `descriptions` . Çağrısının tür parametreleri, `extent::tile()` `<2,3>` 2x3 kutucuklarının oluşturulduğunu belirtir. Bu nedenle, 8x9 matrisi 12 kutucuğa, dört satıra ve üç sütuna döşenir.

3. `parallel_for_each`Yöntemi, `tiled_index<2,3>` Dizin olarak bir nesne () kullanılarak çağrılır `t_idx` . Dizinin () tür parametreleri, `t_idx` işlem etki alanının () tür parametreleriyle aynı olmalıdır `descriptions.extent.tile< 2, 3>()` .

4. Her bir iş parçacığı yürütüldüğünde, dizin, `t_idx` iş parçacığının hangi kutucuk ( `tiled_index::tile` özellik) ve kutucuk içindeki iş parçacığının konumu (özellik) hakkındaki bilgileri döndürür `tiled_index::local` .

## <a name="tile-synchronizationtile_static-and-tile_barrierwait"></a>Kutucuk eşitleme — tile_static ve tile_barrier:: wait

Önceki örnekte kutucuk düzeni ve dizinler gösterilmektedir, ancak kendi kendine çok yararlı değildir.  Döşeme, kutucuklar algoritmaya ve yararlanma değişkenlerine tam sayı olduğunda yararlı olur `tile_static` . Bir kutucuktaki tüm iş parçacıkları değişkenlere erişimi olduğundan `tile_static` , ' a yapılan çağrılar `tile_barrier::wait` değişkenlere erişimi eşzamanlı hale getirmek için kullanılır `tile_static` . Bir kutucuktaki tüm iş parçacıklarının değişkenlere erişimi olsa da `tile_static` , kutucukta iş parçacıklarının hiçbir garanti edilemez. Aşağıdaki örnek, `tile_static` `tile_barrier::wait` her kutucuğun ortalama değerini hesaplamak için değişkenlerin ve yönteminin nasıl kullanılacağını gösterir. Örneği anlamak için anahtarlar aşağıda verilmiştir:

1. RawData, 8x8 matrisinde depolanır.

2. Döşeme boyutu 2x2 ' dir. Bu, bir 4x4 grubu oluşturur ve ortalama ortalamalar bir nesne kullanılarak 4x4 matrisi içinde depolanabilir `array` . Bir AMP kısıtlı işlevinde başvuruya göre yakalayabileceğiniz sınırlı sayıda tür vardır. `array`Sınıf bunlardan biridir.

3. `#define`,, Ve için tür parametreleri `array` `array_view` `extent` `tiled_index` sabit değerler olması gerektiğinden, matris boyutu ve örnek boyutu deyimleri kullanılarak tanımlanır. Bildirimleri de kullanabilirsiniz `const int static` . Ek bir avantaj olarak, örnek boyutunu değiştirmek önemsiz bir örnektir.

4. `tile_static`Her kutucuk için bir 2x2 bir float değeri dizisi bildirilmiştir. Bildirim her iş parçacığının kod yolunda olsa da, matristeki her kutucuk için yalnızca bir dizi oluşturulur.

5. Her kutucukta bulunan değerleri diziye kopyalamak için bir kod satırı vardır `tile_static` . Her iş parçacığı için, değer diziye kopyalandıktan sonra iş parçacığında yürütme, çağrısı nedeniyle yanıt vermez `tile_barrier::wait` .

6. Bir kutucuktaki tüm iş parçacıkları engelle ulaştığında, ortalama hesaplanabilir. Kod her iş parçacığı için yürütüldüğü için, `if` yalnızca bir iş parçacığında ortalamayı hesaplamak için bir ifade vardır. Ortalama, ortalamalar değişkeninde depolanır. Engel temel olarak, bir döngüyü kullanabileceğiniz şekilde, kutucuğa göre hesaplamaları denetleyen yapısıdır **`for`** .

7. Bir nesne olduğundan, `averages` değişkende bulunan veriler `array` konağa geri kopyalanmalıdır. Bu örnek, vektör dönüştürme işlecini kullanır.

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

`tile_static`Adlandırılmış bir değişken oluşturmak `total` ve bu değişkeni, her iş parçacığı için aşağıdaki gibi artırmanız gerekebilir:

```cpp
// Do not do this.
tile_static float total;
total += matrix[t_idx];
t_idx.barrier.wait();

averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE* SAMPLESIZE);
```

Bu yaklaşımdaki ilk sorun, `tile_static` değişkenlerin başlatıcıları olamaz. İkinci sorun, ' de atamadaki bir yarış durumu olduğu için `total` , kutucuktaki tüm iş parçacıklarının değişkene belirli bir sıra erişemez. Bir algoritmayı, ileri ' de gösterildiği gibi, her bir engelte yalnızca bir iş parçacığının toplamına erişmesine izin verecek şekilde programlayabilirsiniz. Ancak bu çözüm genişletilebilir değildir.

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

Eşitlenmesi gereken, genel bellek erişimi ve bellek erişimi olmak üzere iki tür bellek erişimi vardır `tile_static` . Bir `concurrency::array` nesne yalnızca genel belleği ayırır. `concurrency::array_view` `tile_static` , Nasıl oluşturulduğuna bağlı olarak genel belleğe, belleğe veya her ikisine de başvurabilir.  Eşitlenmesi gereken iki tür bellek vardır:

- Genel bellek

- `tile_static`

*Bellek sınırı* , bellek erişimlerinin iş parçacığı kutucuğunda diğer iş parçacıkları tarafından kullanılabilmesini sağlar ve bellek erişimleri program sırasına göre yürütülür. Bunu sağlamak için, derleyiciler ve işlemcilerin, parmaklarınızın okuma ve yazma işlemlerini yeniden sıralamayın. C++ AMP, aşağıdaki yöntemlerden birine yapılan bir çağrı tarafından bir bellek dilimi oluşturulur:

- [tile_barrier:: wait yöntemi](reference/tile-barrier-class.md#wait): hem genel hem de bellek etrafında bir sınır oluşturur `tile_static` .

- [tile_barrier:: Wait_with_all_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_all_memory_fence): hem genel hem de bellek etrafında bir sınır oluşturur `tile_static` .

- [tile_barrier:: Wait_with_global_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_global_memory_fence): yalnızca genel belleğin etrafında bir çit oluşturur.

- [tile_barrier:: Wait_with_tile_static_memory_fence yöntemi](reference/tile-barrier-class.md#wait_with_tile_static_memory_fence): yalnızca bellek etrafında bir sınır oluşturur `tile_static` .

İhtiyaç duyduğunuz belirli bir dilimi çağırmak uygulamanızın performansını iyileştirebilirler. Engel türü derleyicinin ve donanım yeniden sıralama deyimlerinin nasıl yapıldığını etkiler. Örneğin, genel bellek sınırı kullanırsanız, bu, yalnızca genel bellek erişimleri için geçerlidir ve bu nedenle, derleyici ve donanım, her iki tarafındaki değişkenlere yapılan okuma ve yazma işlemlerini yeniden sıralayabilir `tile_static` .

Sonraki örnekte, engeli, bir değişken olarak yazmaları eşitler `tileValues` `tile_static` . Bu örnekte `tile_barrier::wait_with_tile_static_memory_fence` yerine çağrılır `tile_barrier::wait` .

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
[tile_static anahtar sözcüğü](../../cpp/tile-static-keyword.md)
