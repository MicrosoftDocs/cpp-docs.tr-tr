---
title: tile_static Anahtar Sözcüğü
ms.date: 11/04/2016
f1_keywords:
- tile_static_CPP
helpviewer_keywords:
- tile_static keyword
ms.assetid: d78384d4-65d9-45cf-b3df-7e904f489d06
ms.openlocfilehash: 1e0e967edd1808b27d3d4e92f29f7472608f8e65
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330472"
---
# <a name="tilestatic-keyword"></a>tile_static Anahtar Sözcüğü

**Tile_static** anahtar sözcüğü iş parçacıklarının döşemedeki tüm iş parçacıklarının tarafından erişilebilecek bir değişken bildirmek için kullanılır. Değişkenin ömrü yürütme bildirim noktasından ulaşır ve çekirdek işlevi döndüğünde sona erer başlatılır. Döşemeleri kullanma ile ilgili daha fazla bilgi için bkz: [kullanarak kutucuk](../parallel/amp/using-tiles.md).

**Tile_static** anahtar sözcüğü aşağıdaki sınırlamalara sahiptir:

- Olan bir işlev olan değişkenleri kullanılabilir `restrict(amp)` değiştiricisi.

- İşaretçi veya başvuru türleri olan değişkenlerde kullanılamaz.

- A **tile_static** değişkeni bir başlatıcıya sahip olamaz. Varsayılan oluşturucular ve Yıkıcılar otomatik olarak çağrılmaz.

- Başlatılmamış bir değeri **tile_static** değişkeni tanımlanmamış.

- Varsa bir **tile_static** çağrısıyla döşenmemiş kökü belirtilmiş bir çağrı grafı içinde bildirilen değişken `parallel_for_each`, bir uyarı oluşturulur ve bu değişkenin davranış tanımlanmamıştır.

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği nasıl bir **tile_static** değişkeni, bir döşeme içindeki çeşitli iş parçacıkları arasında veri birleştirdiğinizde için kullanılabilir.

```cpp
// Sample data:
int sampledata[] = {
    2, 2, 9, 7, 1, 4,
    4, 4, 8, 8, 3, 4,
    1, 5, 1, 2, 5, 2,
    6, 8, 3, 2, 7, 2};

// The tiles:
// 2 2    9 7    1 4
// 4 4    8 8    3 4
//
// 1 5    1 2    5 2
// 6 8    3 2    7 2

// Averages:
int averagedata[] = {
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
};

array_view<int, 2> sample(4, 6, sampledata);
array_view<int, 2> average(4, 6, averagedata);

parallel_for_each(
    // Create threads for sample.extent and divide the extent into 2 x 2 tiles.
    sample.extent.tile<2,2>(),
    [=](tiled_index<2,2> idx) restrict(amp)
    {
        // Create a 2 x 2 array to hold the values in this tile.
        tile_static int nums[2][2];
        // Copy the values for the tile into the 2 x 2 array.
        nums[idx.local[1]][idx.local[0]] = sample[idx.global];
        // When all the threads have executed and the 2 x 2 array is complete, find the average.
        idx.barrier.wait();
        int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1];
        // Copy the average into the array_view.
        average[idx.global] = sum / 4;
      }
);

for (int i = 0; i < 4; i++) {
    for (int j = 0; j < 6; j++) {
        std::cout << average(i,j) << " ";
    }
    std::cout << "\n";
}

// Output:
// 3 3 8 8 3 3
// 3 3 8 8 3 3
// 5 5 2 2 4 4
// 5 5 2 2 4 4
// Sample data.
int sampledata[] = {
    2, 2, 9, 7, 1, 4,
    4, 4, 8, 8, 3, 4,
    1, 5, 1, 2, 5, 2,
    6, 8, 3, 2, 7, 2};

// The tiles are:
// 2 2    9 7    1 4
// 4 4    8 8    3 4
//
// 1 5    1 2    5 2
// 6 8    3 2    7 2

// Averages.
int averagedata[] = {
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
};

array_view<int, 2> sample(4, 6, sampledata);
array_view<int, 2> average(4, 6, averagedata);

parallel_for_each(
    // Create threads for sample.grid and divide the grid into 2 x 2 tiles.
    sample.extent.tile<2,2>(),
    [=](tiled_index<2,2> idx) restrict(amp)
    {
        // Create a 2 x 2 array to hold the values in this tile.
        tile_static int nums[2][2];
        // Copy the values for the tile into the 2 x 2 array.
        nums[idx.local[1]][idx.local[0]] = sample[idx.global];
        // When all the threads have executed and the 2 x 2 array is complete, find the average.
        idx.barrier.wait();
        int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1];
        // Copy the average into the array_view.
        average[idx.global] = sum / 4;
      }
);

for (int i = 0; i < 4; i++) {
    for (int j = 0; j < 6; j++) {
        std::cout << average(i,j) << " ";
    }
    std::cout << "\n";
}

// Output.
// 3 3 8 8 3 3
// 3 3 8 8 3 3
// 5 5 2 2 4 4
// 5 5 2 2 4 4
```

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft'a Özel Değiştiriciler](../cpp/microsoft-specific-modifiers.md)<br/>
[C++ AMP'ye Genel Bakış](../parallel/amp/cpp-amp-overview.md)<br/>
[parallel_for_each işlevi (C++ AMP)](../parallel/amp/reference/concurrency-namespace-functions-amp.md#parallel_for_each)<br/>
[İzlenecek yol: Matris Çarpımı](../parallel/amp/walkthrough-matrix-multiplication.md)