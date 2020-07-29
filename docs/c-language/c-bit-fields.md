---
title: C Bit Alanları
ms.date: 11/04/2016
helpviewer_keywords:
- bitfields
- bit fields
ms.assetid: 9faf74c4-7fd5-4b44-ad18-04485193d06e
ms.openlocfilehash: 4878a9c8c206851b13484446b436952e655e06db
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234295"
---
# <a name="c-bit-fields"></a>C Bit Alanları

Bir yapı veya birleşim üyeleri için bildirimcilerin yanı sıra, bir yapı bildirimci, "bit alanı" olarak adlandırılan belirtilen sayıda bit de olabilir. Uzunluğu, alan adı için bildirimciden bir iki nokta üst üste kadar ayarlanır. Bit alanı integral türü olarak yorumlanır.

## <a name="syntax"></a>Sözdizimi

*struct-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bildirimci*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tür belirleyicisi* *bildirimci*<sub>opt</sub> **:** *sabit ifadesi*

*Sabit ifade* , alanın genişliğini bit cinsinden belirtir. İçin *tür belirleyicisi* `declarator` **`unsigned int`** , **`signed int`** , veya olmalıdır **`int`** ve *sabit ifadesi* negatif olmayan bir tamsayı değeri olmalıdır. Değer sıfırsa, bildirimin No değeri vardır `declarator` . Bit alanı dizileri, bit alanları işaretçileri ve bit alanları döndüren işlevlere izin verilmez. İsteğe bağlı, `declarator` bit alanını adlandırır. Bit alanları, yalnızca bir yapının parçası olarak bildirilemez. Address-of işleci ( **&** ), bit alanı bileşenlerine uygulanamaz.

Adlandırılmamış bit alanlarına başvurulamaz ve çalışma zamanında içerikleri tahmin edilemez. Hizalama amacıyla "sözde" alanları olarak kullanılabilirler. Genişliği 0 olarak belirtilen adlandırılmamış bir bit alanı, *Yapı-bildirim-listesinde* kendisini izleyen üyenin depolamanın bir sınır üzerinde başlayacağını garanti eder **`int`** .

Bit alanları da bit deseninin içermesi için yeterince uzun olmalıdır. Örneğin, bu iki deyim geçerli değildir:

```
short a:17;        /* Illegal! */
int long y:33;     /* Illegal! */
```

Bu örnek adında iki boyutlu yapıların bir dizisini tanımlar `screen` .

```
struct
{
    unsigned short icon : 8;
    unsigned short color : 4;
    unsigned short underline : 1;
    unsigned short blink : 1;
} screen[25][80];
```

Dizi 2.000 öğe içeriyor. Her öğe, dört bitlik alan üyesini içeren tek bir yapıdır: `icon` , `color` , `underline` ve `blink` . Her yapının boyutu iki bayttır.

Bit alanları tamsayı türüyle aynı semantiğe sahip. Bu bir bit alanın, bit alanında kaç bitin olduğunu fark etmeksizin, aynı temel türdeki bir değişkenle tam olarak aynı şekilde kullanıldığı anlamına gelir.

**Microsoft'a Özgü**

Olarak tanımlanan bit alanları **`int`** olarak değerlendirilir **`signed`** . ANSI C standardına yönelik bir Microsoft uzantısı, **`char`** **`long`** **`signed`** bit alanları için ve türleri (hem hem de **`unsigned`** ) sağlar. Temel türü olan adlandırılmamış bit alanları **`long`** , **`short`** veya **`char`** ( **`signed`** veya **`unsigned`** ) temel türe uygun bir sınıra hizalamayı zorlar.

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

8086 işlemci ailesi, yüksek bayttan önce gelen tamsayı değerlerinin düşük baytını depoladığından, yukarıdaki tamsayı, `0x01F2` tarafından izlenen fiziksel bellekte depolanır `0xF2` `0x01` .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Yapı bildirimleri](../c-language/structure-declarations.md)
