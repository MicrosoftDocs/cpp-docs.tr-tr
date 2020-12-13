---
description: 'Hakkında daha fazla bilgi edinin: tile_static anahtar sözcüğü'
title: tile_static Anahtar Sözcüğü
ms.date: 11/04/2016
f1_keywords:
- tile_static_CPP
helpviewer_keywords:
- tile_static keyword
ms.assetid: d78384d4-65d9-45cf-b3df-7e904f489d06
ms.openlocfilehash: c719ab61fd6247800b7e1b6b8ac1a58dd51c6ac5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151417"
---
# <a name="tile_static-keyword"></a>tile_static Anahtar Sözcüğü

**Tile_static** anahtar sözcüğü, bir iş parçacığı kutucuğunda tüm iş parçacıkları tarafından erişilebilen bir değişkeni bildirmek için kullanılır. Değişkenin ömrü, yürütme bildirim noktasına ulaştığında başlar ve çekirdek işlevi döndüğünde sonlanır. Kutucukları kullanma hakkında daha fazla bilgi için bkz. [kutucukları kullanma](../parallel/amp/using-tiles.md).

**Tile_static** anahtar sözcüğü aşağıdaki sınırlamalara sahiptir:

- Yalnızca değiştiriciye sahip bir işlevde bulunan değişkenlerde kullanılabilir `restrict(amp)` .

- İşaretçi veya başvuru türleri olan değişkenlerde kullanılamaz.

- **Tile_static** değişkeni bir başlatıcıya sahip olamaz. Varsayılan oluşturucular ve Yıkıcılar otomatik olarak çağrılmaz.

- Başlatılmamış **tile_static** değişkenin değeri tanımsız.

- Bir **tile_static** değişkeni, üzerinde döşeli olmayan bir çağrının belirtildiği bir çağrı grafiğinde bildirilirse `parallel_for_each` , bir uyarı oluşturulur ve değişkenin davranışı tanımsız olur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir kutucuk içindeki çeşitli iş parçacıkları arasında veri biriktirmek için bir **tile_static** değişkeninin nasıl kullanılabileceğini gösterir.

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

[Microsoft 'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md)<br/>
[C++ AMP genel bakış](../parallel/amp/cpp-amp-overview.md)<br/>
[parallel_for_each Işlevi (C++ AMP)](../parallel/amp/reference/concurrency-namespace-functions-amp.md#parallel_for_each)<br/>
[İzlenecek yol: Matris çarpma](../parallel/amp/walkthrough-matrix-multiplication.md)
