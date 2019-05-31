---
title: Hizalama (C++ Bildirimleri)
description: Veri hizalama modern nasıl belirtildiğine C++.
ms.date: 05/30/2019
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
ms.openlocfilehash: b6e03ac2b89624a0eb6602183d4ff4bf8b518f8d
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450776"
---
# <a name="alignment-c-declarations"></a>Hizalama (C++ Bildirimleri)

Alt düzey C++ özelliklerinin belirli donanım mimarisiyle en büyük avantajlarından yararlanmak için bellekte nesnelerin kesin hizalamayı belirtme olanağı biridir. Varsayılan olarak, derleyici sınıf ile yapı üyeleri kendi boyutu değeri hizalar: `bool` ve `char` 1 baytlık sınırlarda `short` 2 baytlık sınırlarda `int`, `long`, ve `float` 4 baytlık sınırlarda ve `long long`, `double`, ve `long double` 8 baytlık sınırlarda. Çoğu senaryoda, hiçbir zaman varsayılan hizalama zaten en iyi olduğundan ile aynı doğrultuda konusunda endişe duymaları gerekmez. Bazı durumlarda, ancak, önemli performans geliştirmeleri veya bellek tasarrufu, veri yapıları için özel bir hizalama belirterek elde edebilirsiniz. Visual Studio 2015 önce Microsoft'a özgü anahtar sözcükler kullanabilirsiniz `__alignof` ve `declspec(alignas)` varsayılandan daha büyük bir hizalama belirtmek için. C ++ 11 standart anahtar sözcükleri Visual Studio 2015'te, başlangıç kullanması gereken [alignof ve alignas](../cpp/alignof-and-alignas-cpp.md) maksimum kod taşınabilir. Yeni anahtar sözcüklerle Microsoft'a özgü genişletmelerdir başlık altında aynı şekilde davranır. Bu uzantıları belgelerine, yeni anahtar sözcükler için de geçerlidir. Daha fazla bilgi için [__alignof işleci](../cpp/alignof-operator.md) ve [hizalama](../cpp/align-cpp.md). C++ Standart değil belirtin paketleme davranışı hizalaması için hedef platformu için derleyici varsayılandan daha küçük sınırlarındaki hala #pragma Microsoft kullanmanız gereken şekilde [paketi](../preprocessor/pack.md) böyle bir durumda.

Kullanım [aligned_storage sınıfı](../standard-library/aligned-storage-class.md) Özel hizalamaları ile veri yapılarının bellek ayırma için. [Aligned_union sınıfı](../standard-library/aligned-union-class.md) birleşimler için hizalama Önemsiz olmayan oluşturuculara veya yıkıcıları ile belirtmenizi sağlar.

## <a name="about-alignment"></a>Hizalama hakkında

Hizalama, 2'in kuvveti modül sayısal adresi olarak ifade edilen bir bellek adresi özelliğidir. Örneğin, ' % s'adresi 0x0001103F 4 modül 3'tür. Bu adres hizalanması için 4n + 3, 4 2 seçilen gücünü burada gösterir kabul edilir. Bir adresi hizalamasını 2 seçilen gücüyle bağlıdır. Modül 8 aynı adres 7'dir. Bir adresi hizalamanın Xn + 0 ise X için uyumlu kabul edilir.

CPU, bellek içinde depolanan veriler çalıştırma yönergeleri yürütün. Veriler, bellek adreslerinde tarafından tanımlanır. Tek bir veri de bir boyuta sahiptir. Bir veri diyoruz *doğal olarak hizalı* adresini boyutuna hizalanır durumunda. Çağrıldığı *yanlış hizalanmış* Aksi takdirde. Örneğin, 8-bayt kayan veri, doğal olarak tanımlamak için kullanılan adres 8 baytlık hizalama varsa uyumludur.

## <a name="compiler-handling-of-data-alignment"></a>Veri hizalama derleyici işleme

Veri ayırma veri hizalanmama engelleyen bir hale getirmek derleyiciler çalışır.

Basit veri türleri için derleyici veri türünde bayt boyutu katları olan adresleri de atar. Örneğin, derleyici adresleri türü değişkenlere atar `long` 4 alt adresinin 2 biti sıfır olarak ayarlandığında, katları olan.

Derleyici ayrıca her öğe yapısının doğal olarak uygun bir şekilde yapıları sıfır ekleyerek doldurur. Yapısı göz önünde bulundurun `struct x_` aşağıdaki kod örneğinde:

```cpp
struct x_
{
   char a;     // 1 byte
   int b;      // 4 bytes
   short c;    // 2 bytes
   char d;     // 1 byte
} MyStruct;
```

Derleyici bu yapı hizalama doğal olarak zorlamak için sıfır ekleyerek doldurur.

Aşağıdaki kod örneği, nasıl derleyici doldurulan yapısını bellekte yerleştirir gösterir:

```cpp
// Shows the actual memory layout
struct x_
{
   char a;            // 1 byte
   char _pad0[3];     // padding to put 'b' on 4-byte boundary
   int b;            // 4 bytes
   short c;          // 2 bytes
   char d;           // 1 byte
   char _pad1[1];    // padding to make sizeof(x_) multiple of 4
}
```

1. Her iki bildirimi dönüş `sizeof(struct x_)` 12 bayt olarak.

1. İkinci bildirim iki doldurma öğeleri içerir:

1. `char _pad0[3]` hizalamak için `int b` 4-bayt sınırındaki üyesi

1. `char _pad1[1]` Dizi öğeleri yapı hizalama `struct _x bar[3];`

1. Doldurma öğelerini hizalar `bar[3]` doğal erişime izin veren bir yolla.

Aşağıdaki örnekte gösterildiği kod `bar[3]` dizi düzeni:

```Output
adr offset   element
------   -------
0x0000   char a;         // bar[0]
0x0001   char pad0[3];
0x0004   int b;
0x0008   short c;
0x000a   char d;
0x000b   char _pad1[1];

0x000c   char a;         // bar[1]
0x000d   char _pad0[3];
0x0010   int b;
0x0014   short c;
0x0016   char d;
0x0017   char _pad1[1];

0x0018   char a;         // bar[2]
0x0019   char _pad0[3];
0x001c   int b;
0x0020   short c;
0x0022   char d;
0x0023   char _pad1[1];
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri yapısı hizalama](https://en.wikipedia.org/wiki/Data_structure_alignment)
