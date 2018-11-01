---
title: C Bit Alanları
ms.date: 11/04/2016
helpviewer_keywords:
- bitfields
- bit fields
ms.assetid: 9faf74c4-7fd5-4b44-ad18-04485193d06e
ms.openlocfilehash: ffcc622135a9a4d9b46cf6ab62604f9965ac6d47
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666238"
---
# <a name="c-bit-fields"></a>C Bit Alanları

Bir yapı veya birleşim üyeleri için Bildirimciler ek olarak, bir yapı bildirimci de BITS "bit alanı." adlı, belirtilen sayıda olabilir Uzunluğu alan adı bildirimcisi gelen iki nokta ile alınır. Bir bit alanı integral türü yorumlanır.

## <a name="syntax"></a>Sözdizimi

*Yapı-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirticisi* *bildirimci*<sub>iyileştirilmiş</sub> **:** *sabit-ifade*

*Sabit-ifade* bit alanının genişliğini belirtir. *Tür tanımlayıcısı* için `declarator` olmalıdır `unsigned int`, **signed int**, veya `int`ve *sabit-ifade* bir negatif olmamalıdır tamsayı değeri. Değer sıfır ise bildirimi olmayan `declarator`. Diziler bit alanları bit alanlarının ve bit alanları döndüren işlev işaretçileri izin verilmez. İsteğe bağlı `declarator` bit alanı adları. Bit alanları yalnızca bir yapının bir parçası olarak bildirilebilir. Address-of işlecini (**&**) bit alanı bileşenleri için uygulanamaz.

Adsız bit alanları başvurulamaz ve çalışma zamanında içeriklerini tahmin edilemez. Bunlar "kukla" alanları olarak hizalama amaçları için kullanılabilir. 0 içinde aşağıdaki üyesi için depolama garanti gibi genişliğini belirtilen adlandırılmamış bir bit alanı *yapı bildirim listesi* başlangıcı bir `int` sınır.

Bit alanları da içeren bit deseni için yeterince uzun olması gerekir. Örneğin, bu iki ifade geçerli değil:

```
short a:17;        /* Illegal! */
int long y:33;     /* Illegal! */
```

Bu örnek iki boyutlu bir dizi adlandırılmış yapıları tanımlar `screen`.

```
struct
{
    unsigned short icon : 8;
    unsigned short color : 4;
    unsigned short underline : 1;
    unsigned short blink : 1;
} screen[25][80];
```

Dizi 2.000 öğeleri içerir. Dört bit alanı üyelerini içeren tek bir yapı her öğesidir: `icon`, `color`, `underline`, ve `blink`. Her yapı boyutu iki bayttır.

Bit alanları, tamsayı türü ile aynı semantiğe sahip. Başka bir deyişle, bit alanı kaç BITS ne olursa olsun aynı temel türünde bir değişken kullanılacak bir bit alanı ifadeleri tam olarak aynı şekilde kullanılır.

**Microsoft'a özgü**

Bit alanları olarak tanımlanan `int` işaretli olarak kabul edilir. ANSI C standardı için bir Microsoft uzantısı sağlar `char` ve **uzun** türleri (her ikisi de **imzalı** ve `unsigned`) bit alanları için. Bit alanları temel türüyle adlandırılmamış **uzun**, **kısa**, veya `char` (**imzalı** veya `unsigned`) bir sınır hizalamayı temel türü için uygun zorlayın.

Bit alanları, bir tamsayı içinde en az önemli olan bitten en önemli bite doğru ayrılır. Aşağıdaki kodda

```
struct mybitfields
{
    unsigned short a : 4;
    unsigned short b : 5;
    unsigned short c : 7;
} test;

int main( void );
{
    test.a = 2;
    test.b = 31;
    test.c = 0;
}
```

bitler aşağıdaki gibi düzenlenir:

```
00000001 11110010
cccccccb bbbbaaaa
```

İşlemci 8086 ailesi düşük baytını yüksek bayttan, tamsayı önce tamsayı değerleri depoladığından `0x01F2` yukarıdaki fiziksel bellekte depolanır `0xF2` ardından `0x01`.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Yapı Bildirimleri](../c-language/structure-declarations.md)