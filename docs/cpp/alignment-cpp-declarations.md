---
title: Hizalama
description: Modern C++içinde veri hizalaması nasıl belirtilir.
ms.date: 12/11/2019
ms.assetid: a986d510-ccb8-41f8-b905-433df9183485
ms.openlocfilehash: 13f09366501de2482b8ae9ea430898d6c32134c2
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443659"
---
# <a name="alignment"></a>Hizalama

Öğesinin C++ alt düzey özelliklerinden biri, belirli bir donanım mimarisinin en yüksek avantajlarından yararlanmak için bellekteki nesnelerin kesin hizalamasını belirtme yeteneğidir. Varsayılan olarak, derleyici sınıf ve yapı üyelerini boyut değerlerine göre hizalar: `bool` ve `char` 1 baytlık sınırlarda, 2 baytlık sınırlarda `short`, `int`, `long`ve `float`, 8 baytlık sınırlarda `long long`, `double`ve `long double`. 

Çoğu senaryoda, varsayılan hizalama zaten en iyi durumda olduğu için hizalamayla ilgilenmelisiniz. Ancak bazı durumlarda, veri yapılarınız için özel bir hizalama belirterek önemli performans geliştirmeleri veya bellek tasarrufu elde edebilirsiniz. Visual Studio 2015 ' den önce, Microsoft 'a özgü anahtar kelimeleri `__alignof` ve varsayılandan daha büyük bir hizalama belirtmek için `declspec(alignas)` kullanabilirsiniz. Visual Studio 2015 ' den başlayarak, en fazla kod taşınabilirlik için C++ 11 standart anahtar sözcükleri **hizalamasını** ve **alignas** 'yi kullanmanız gerekir. Yeni anahtar sözcükler, Microsoft 'a özgü uzantılar ile aynı şekilde davranır. Bu uzantılara ait belgeler yeni anahtar sözcükler için de geçerlidir. Daha fazla bilgi için bkz. [__Alignof işleci](../cpp/alignof-operator.md) ve [Hizalama](../cpp/align-cpp.md). Standart C++ , hedef platformun varsayılan derleyicisinden daha küçük olan sınırlara göre hizalama için paketleme davranışını belirtmez, bu nedenle yine de bu durumda Microsoft #pragma [paketini](../preprocessor/pack.md) kullanmanız gerekir.

Özel hizalamalar ile veri yapılarının bellek ayırması için [aligned_storage sınıfını](../standard-library/aligned-storage-class.md) kullanın. [Aligned_union sınıfı](../standard-library/aligned-union-class.md) , önemsiz olmayan oluşturucular veya Yıkıcılar içeren birleşimler için hizalama belirtmek içindir.

## <a name="alignment-and-memory-addresses"></a>Hizalama ve bellek adresleri

Hizalama, bir bellek adresinin 2. kuvvetinin sayısal adres olarak ifade edildiği bir özelliğidir. Örneğin, 0x0001103F modül 4 adresi 3 ' dir. Bu adres 4N + 3 ' e hizalandığını belirtir; burada 4, 2 ' nin seçili kuvvetinin olduğunu gösterir. Bir adresin hizalaması, 2 ' nin seçili gücüne bağlıdır. Aynı adres modül 8 ' i 7 ' dir. Hizalama xn + 0 ise, bir adresin X 'e hizalandığını söylenir.

CPU 'Lar bellekte depolanan veriler üzerinde çalışan yönergeleri yürütür. Veriler, bellekteki adresleriyle tanımlanır. Tek bir veri de boyut içerir. Adresi boyutuna hizalanmışsa *doğal olarak hizalanmış* bir veri çağırıyoruz. Aksi halde *yanlış hizalanmış* olarak çağırılır. Örneğin, bir 8 baytlık kayan nokta veri, bunu tanımlamak için kullanılan adreste 8 baytlık bir hizalama varsa doğal olarak hizalanır.

## <a name="compiler-handling-of-data-alignment"></a>Veri hizalamasını derleyici işleme

Derleyiciler, verileri hatalı hizalanmış şekilde engelleyecek şekilde veri ayırmaları yapmayı dener.

Basit veri türleri için derleyici, veri türü baytlarına göre boyutun katları olan adresleri atar. Örneğin, derleyici 4 ' ün katları olan `long` değişkenlere adresler atar, bu da adresin alt 2 bitini sıfıra ayarlar.

Derleyici Ayrıca yapıları yapının her bir öğesini doğal olarak bir şekilde hizalar. Aşağıdaki kod örneğinde yapıyı `struct x_` göz önünde bulundurun:

```cpp
struct x_
{
   char a;     // 1 byte
   int b;      // 4 bytes
   short c;    // 2 bytes
   char d;     // 1 byte
} bar[3];
```

Derleyici bu yapıyı, doğal olarak hizalamayı zorlamak için Pad 'ler.

Aşağıdaki kod örneğinde, derleyicinin doldurulmuş yapıyı belleğe nasıl yerleştirdiği gösterilmektedir:

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
} bar[3];
```

Her iki bildirim de 12 bayt olarak `sizeof(struct x_)` döndürür.

İkinci bildirim iki doldurma öğesi içerir:

1. `char _pad0[3]`, `int b` üyesini 4 baytlık bir sınıra hizalamak için.

1. Yapı `struct _x bar[3];` dizi öğelerini dört baytlık bir sınırında hizalamak `char _pad1[1]`.

Doldurma `bar[3]` öğelerini doğal erişime izin verecek şekilde hizalar.

Aşağıdaki kod örneği `bar[3]` dizi mizanpajını gösterir:

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

## <a name="alignof-and-alignas"></a>alignof ve alignas

**Alignas** tür Belirleyicisi, değişkenlerin ve Kullanıcı tanımlı C++ türlerin özel hizalamasını belirtmenin taşınabilir ve standart bir yoludur. Aynı **şekilde, belirtilen** bir tür veya değişkenin hizalamasını elde etmek için standart, taşınabilir bir yoldur.

## <a name="example"></a>Örnek

Bir sınıf, yapı veya Union üzerinde veya ayrı üyelerde **alignas** kullanabilirsiniz. Birden çok **alignas** belirticisi ile karşılaşıldığında, derleyici en katı birini (en büyük değere sahip olan) seçer.

```cpp
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar
{
    int i;       // 4 bytes
    int n;      // 4 bytes
    alignas(4) char arr[3];
    short s;          // 2 bytes
};

int main()
{
    std::cout << alignof(Bar) << std::endl; // output: 16
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri yapısı hizalaması](https://en.wikipedia.org/wiki/Data_structure_alignment)
