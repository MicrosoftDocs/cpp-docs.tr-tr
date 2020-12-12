---
description: 'Daha fazla bilgi edinin: C tamsayı sabitleri'
title: C Tamsayı Sabitleri
ms.date: 02/27/2018
helpviewer_keywords:
- integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
ms.openlocfilehash: 1dbc22a2d4351dbd6d09f555a95380a1fd94619b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182196"
---
# <a name="c-integer-constants"></a>C Tamsayı Sabitleri

*Tamsayı sabiti* , bir integral değeri temsil eden ondalık (10 tabanında), sekizlik (taban 8) veya onaltılı (taban 16) sayıdır. Değiştirilemeyen tamsayı değerlerini göstermek için tamsayı sabitleri kullanın.

## <a name="syntax"></a>Syntax

*tamsayı sabiti*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Decimal-sabit* *tamsayı-son ek*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sekizlik sabit* *tamsayı-son ek*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*onaltılı sabit* *tamsayı-son ek*<sub>opt</sub>

*Decimal sabit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sıfır olmayan basamak*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Decimal-sabit* *basamak*

*sekizlik sabit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sekizlik sabit* *sekizlik basamak*

*onaltılı sabit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*on altılı ön ek* *onaltılı basamak*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*onaltılı sabit* *onaltılı basamak*

*on altılı önek*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0x**  **0x**

*sıfır olmayan rakam*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**1 2 3 4 5 6 7 8 9**

*sekizlik basamak*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7**

*on altılık*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**a b c d e f**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**A B C D E F**

*tamsayı-sonek*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*imzasız son sonek* *uzun son ek*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*imzasız son sonek* *uzun uzun-sonek*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*imzasız son ek* *64-bit tamsayı-sonek*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*uzun son sonek* *imzasız-son ek*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*uzun uzun son ek* *işaretsiz-sonek*<sub>kabul etme</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*64-bit-tamsayı-sonek*

*imzasız-sonek*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**u U**

*uzun sonek*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**l L**

*uzun uzun son ek*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**ll LL**

*64-bit-tamsayı-sonek*: aşağıdakilerden biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**i64 I64**

**İ64** ve **I64** sonekleri, Microsoft 'a özgüdür.

Tamsayı sabitleri önünde eksi işareti () belirtilmedikçe pozitif bir tamsayıdır **-** . Eksi işareti birli aritmetik olumsuzlama işleci olarak yorumlanır. (Bu işleç hakkında bilgi için bkz. [birli aritmetik işleçler](../c-language/unary-arithmetic-operators.md) .)

Tamsayı sabiti **0x** veya **0x** ile başlıyorsa, onaltılı olur. **0** basamağına başlıyorsa, sekizlik olur. Aksi takdirde, ondalık olarak kabul edilir.

Aşağıdaki tamsayı sabitleri eşdeğerdir:

```C
28
0x1C   /* = Hexadecimal representation for decimal 28 */
034    /* = Octal representation for decimal 28 */
```

Boşluk karakteri, bir tamsayı sabitinin rakamlarını ayırabilirler. Bu örneklerde bazı geçerli ondalık, sekizli ve onaltılık sabitler gösterilmektedir.

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

[C sabitleri](../c-language/c-constants.md)<br/>
