---
title: Hizalama (C++ Bildirimleri)
ms.date: 11/04/2016
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
ms.openlocfilehash: 0709ad414af3f167a64d9c89c342690015190287
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155400"
---
# <a name="alignment-c-declarations"></a>Hizalama (C++ Bildirimleri)

Alt düzey C++ özelliklerinin belirli donanım mimarisiyle en büyük avantajlarından yararlanmak için bellekte nesnelerin kesin hizalamayı belirtme olanağı biridir. Varsayılan olarak, derleyici sınıf ile yapı üyeleri kendi boyutu değeri hizalar: bool ve char hizalanır tek baytlık sınırlarda, iki bayt üzerinde kısa Int uzun uzun, çift ve üzerinde sekiz bayt uzun çift dört bayt. Çoğu senaryoda hiçbir zaman varsayılan hizalama zaten en iyi olduğundan ile aynı doğrultuda önceliğiniz olması gerekir. Bazı durumlarda ancak, önemli performans geliştirmeleri veya bellek tasarrufu, veri yapıları için özel bir hizalama belirterek elde edebilirsiniz. Visual Studio 2015 tarihinden önce varsayılandan daha büyük bir hizalama belirtmek için Microsoft'a özgü anahtar sözcükler __alignof ve declspec(alignas) kullanabilirsiniz. C ++ 11 standart anahtar sözcükleri Visual Studio 2015'te, başlangıç kullanması gereken [alignof ve alignas](../cpp/alignof-and-alignas-cpp.md) maksimum kod taşınabilir. Yeni anahtar sözcüklerle Microsoft'a özgü genişletmelerdir başlık altında aynı şekilde davranır ve bu uzantıları belgelerine de için yeni anahtar sözcüklerin uygular. Bkz: [__alignof işleci](../cpp/alignof-operator.md) ve [hizalama](../cpp/align-cpp.md) daha fazla bilgi için. C++ standart Microsoft #pragma kullanmak yine hedef platformu için derleyici varsayılandan daha küçük sınırlarındaki hizalama için paketleme davranışı belirtmiyor [paketi](../preprocessor/pack.md) durumda.

C++ Standart kitaplığı sağlar [aligned_storage sınıfı](../standard-library/aligned-storage-class.md) Özel hizalamaları ile veri yapıları için bellek ayırma için ve [aligned_union sınıfı](../standard-library/aligned-union-class.md) hizalamayı belirtme birleşimler Önemsiz olmayan oluşturuculara veya yıkıcıları ile.

## <a name="about-alignment"></a>Hizalama hakkında

Hizalama, 2'in kuvveti modül sayısal adresi olarak ifade edilen bir bellek adresi özelliğidir. Örneğin, ' % s'adresi 0x0001103F 4 modül 3'tür; Bu adres hizalanması için 4n + 3, 4 2 seçilen gücünü burada gösterir kabul edilir. Adres hizalama ikinin seçilen gücüyle bağlıdır. Modül 8 aynı adres 7'dir. Bir adresi hizalamanın Xn + 0 ise X için uyumlu kabul edilir.

CPU yürütme yönergeleri bellekte depolanan veriler, çalıştırmak ve verileri, bellek adreslerinde tarafından tanımlanır. Adresini ek olarak, tek bir veri de bir boyutu vardır. Bir veri adresini Aksi takdirde, boyutuna ve yanlış hizalanmış hizalanır, doğal olarak hizalanmış olarak adlandırılır. Örneğin, 8-bayt kayan veri, doğal olarak tanımlamak için kullanılan adres 8'e hizalanır varsa hizalanır.

Verileri veri hizalanmama engelleyen bir şekilde ayırmak için veri alignmentDevice derleyiciler girişimi derleyici işleme.

Basit veri türleri için derleyici veri türünde bayt boyutu katları olan adresleri de atar. Bu nedenle, derleyici, dört, ayarlamanın adresinin alt iki biti sıfır olarak katları olan değişkenlere tür uzun adresleri atar.

Ayrıca, derleyici her öğe yapısının doğal olarak uygun bir şekilde yapıları sıfır ekleyerek doldurur. Aşağıdaki kod örneğinde yapısı yapı x_ göz önünde bulundurun:

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

Aşağıdaki kod örneğinde nasıl derleyici bellek: kopyalama doldurulan yapısı yerleştirir gösterir.

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

1. Her iki bildirimi sizeof(struct x_) 12 bayt olarak döndürür.

1. İkinci bildirim iki doldurma öğeleri içerir:

1. _pad0 char dört bayt sınırındaki int b üyesi hizalamak için [3]

1. _pad1 char [1] [3]; çubuğu yapısı yapı _x'i dizi öğelerinin hizalamak için

1. Doldurma öğeleri [3] çubuğu doğal erişime izin veren bir yolla hizalar.

Aşağıdaki kod örneği çubuğu gösterir. [3] dizi düzeni:

```
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

[Veri yapısı hizalama](http://en.wikipedia.org/wiki/Data_structure_alignment)