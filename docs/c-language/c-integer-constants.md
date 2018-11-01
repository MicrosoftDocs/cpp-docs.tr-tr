---
title: C Tamsayı Sabitleri
ms.date: 02/27/2018
helpviewer_keywords:
- integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
ms.openlocfilehash: 4a3d6b945f3611b8e51029c0a5ec5dc77b2cbaa0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620226"
---
# <a name="c-integer-constants"></a>C Tamsayı Sabitleri

Bir *tamsayı sabiti* (10 tabanında) ondalık, sekizlik (Temel 8) ya da temsil eder bir tamsayı değeri onaltılık (16 tabanında) sayıdır. Tamsayı sabitleri değiştirilemez tamsayı değerlerini temsil edecek şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

*tamsayı sabiti*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ondalık sabit* *tamsayı soneki*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sekizlik sabit* *tamsayı soneki*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*onaltılık sabit* *tamsayı soneki*<sub>iyileştirilmiş</sub><br/>

*ondalık sabit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıfır olmayan basamak*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ondalık sabit* *basamak*<br/>

*sekizlik sabit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sekizlik sabit* *sekizlik basamak*<br/>

*onaltılık sabit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*onaltılık önek* *onaltılık basamak*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*onaltılık sabit* *onaltılık basamak*<br/>

*onaltılık önek*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0x**  **0X**<br/>

*sıfır olmayan basamak*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**1 2 3 4 5 6 7 8 9**<br/>

*sekizlik basamak*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7**<br/>

*onaltılık basamak*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1, 2, 3, 4, 5, 6, 7, 8, 9**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**b c d e f**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**B C D E F**<br/>

*integer-suffix*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretsiz sonek* *uzun soneki*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretsiz sonek* *uzun uzun soneki*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*işaretsiz sonek* *64 bit tamsayı soneki*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*uzun soneki* *işaretsiz sonek*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*uzun uzun soneki* *işaretsiz sonek*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*64 bit tamsayı soneki*<br/>

*işaretsiz sonek*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**u U**<br/>

*uzun soneki*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**l L**<br/>

*uzun uzun soneki*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**ll LL**<br/>

*64 bit tamsayı soneki*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**i64 I64**<br/>

**I64** ve **I64** birimlerdir Microsoft'a özgü.

Bunlar bir eksi işareti tarafından öncelenen sürece tamsayı sabitleri pozitif (**-**). Eksi işareti birli aritmetik olumsuzlama işleci yorumlanır. (Bkz [birli aritmetik işleçler](../c-language/unary-arithmetic-operators.md) bu işleci hakkında bilgi için.)

Bir tam sayı sabiti ile başlıyorsa **0 x** veya **0 X**, onaltılık. Basamağı ile başlıyorsa **0**, sekizlik. Aksi takdirde, ondalık olduğu varsayılır.

Aşağıdaki tamsayı sabitleri eşdeğerdir:

```C
28
0x1C   /* = Hexadecimal representation for decimal 28 */
034    /* = Octal representation for decimal 28 */
```

Hiçbir boşluk karakterlerinin bir tamsayı sabiti rakamı ayırabilirsiniz. Bu örnekler, bazı geçerli bir ondalık, sekizlik ve onaltılık sabitler gösterir.

```C
    /* Decimal Constants */
    int                 dec_int    = 28;
    unsigned            dec_uint   = 4000000024u;
    long                dec_long   = 2000000022l;
    unsigned long       dec_ulong  = 4000000000ul;
    long long           dec_llong  = 9000000000LL;
    unsigned long long  dec_ullong = 900000000001ull;
    __int64             dec_i64    = 9000000000002I64;
    unsigned __int64    dec_ui64   = 90000000000004ui64;

    /* Octal Constants */
    int                 oct_int    = 024;
    unsigned            oct_uint   = 04000000024u;
    long                oct_long   = 02000000022l;
    unsigned long       oct_ulong  = 04000000000UL;
    long long           oct_llong  = 044000000000000ll;
    unsigned long long  oct_ullong = 044400000000000001Ull;
    __int64             oct_i64    = 04444000000000000002i64;
    unsigned __int64    oct_ui64   = 04444000000000000004uI64;

    /* Hexadecimal Constants */
    int                 hex_int    = 0x2a;
    unsigned            hex_uint   = 0XA0000024u;
    long                hex_long   = 0x20000022l;
    unsigned long       hex_ulong  = 0XA0000021uL;
    long long           hex_llong  = 0x8a000000000000ll;
    unsigned long long  hex_ullong = 0x8A40000000000010uLL;
    __int64             hex_i64    = 0x4a44000000000020I64;
    unsigned __int64    hex_ui64   = 0x8a44000000000040Ui64;
```

## <a name="see-also"></a>Ayrıca bkz.

[C Sabitleri](../c-language/c-constants.md)<br/>
