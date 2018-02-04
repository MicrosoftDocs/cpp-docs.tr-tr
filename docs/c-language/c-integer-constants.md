---
title: "C tamsayı sabitleri | Microsoft Docs"
ms.custom: 
ms.date: 02/01/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c23e90d235e1ad2a8cca577c5cfbf2be55b52b6
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="c-integer-constants"></a>C Tamsayı Sabitleri

"Tamsayı sabiti" ondalık (10 tabanı), sekizli (8 tabanı) veya bir tam sayı değeri temsil eden onaltılı (16 tabanı) sayı olabilir. Tamsayı sabitleri değiştirilemez tamsayı değerlerini temsil edecek şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

*integer-constant*:  
&nbsp;&nbsp;*ondalık sabiti* *tamsayı sonek*<sub>iptal et</sub>  
&nbsp;&nbsp;*octal-constant* *integer-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*onaltılık sabiti* *tamsayı sonek*<sub>iptal et</sub>  

*ondalık sabiti*:  
&nbsp;&nbsp;*nonzero-digit*  
&nbsp;&nbsp;*ondalık sabiti* *basamak*  

*sabiti sekizli*:  
&nbsp;&nbsp;**0**  
&nbsp;&nbsp;*octal-constant* *octal-digit*  

*hexadecimal-constant*:  
&nbsp;&nbsp;**0x**  *hexadecimal-digit*  
&nbsp;&nbsp;**0X**  *hexadecimal-digit*  
&nbsp;&nbsp;*onaltılık sabiti* *onaltılık basamak*  

*sıfır olmayan basamaklı*: biri  
&nbsp;&nbsp;**1 2 3 4 5 6 7 8 9**  

*sekizli basamak*: biri  
&nbsp;&nbsp;**0 1 2 3 4 5 6 7**  

*onaltılık basamaklı*: biri  
&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**  
&nbsp;&nbsp;**b c d e f**  
&nbsp;&nbsp;**A B C D E F**  
  
*integer-suffix*:  
&nbsp;&nbsp;*İmzasız soneki* *uzun soneki*<sub>iptal et</sub>  
&nbsp;&nbsp;*uzun soneki* *imzasız soneki*<sub>iptal et</sub>  
&nbsp;&nbsp;*İmzasız soneki* *64 bit tamsayı soneki*<sub>iptal et</sub>

*İmzasız soneki*: biri  
&nbsp;&nbsp;**u U**  

*uzun soneki*: biri  
&nbsp;&nbsp;**l L**  
  
*64 bit tamsayı soneki*: biri &nbsp; &nbsp; **I64 I64**  

Bir eksi işareti koyarak sürece tamsayı sabitleri pozitif (**-**). Eksi işareti birli aritmetik değilleme işleci yorumlanır. (Bkz [birli aritmetik işleçler](../c-language/unary-arithmetic-operators.md) bu işleci hakkında bilgi için.)

Tamsayı sabiti ile başlıyorsa **0 x** veya **0 X**, onaltılık. Basamaklı başlıyorsa **0**, sekizli. Aksi takdirde, ondalık olduğu varsayılır.

Aşağıdaki satırları eşdeğerdir:

```C
0x1C   /* = Hexadecimal representation for decimal 28 */
034    /* = Octal representation for decimal 28 */
```

Hiçbir boşluk karakterleri tamsayı sabiti basamak ayırabilirsiniz. Bu örnekler, geçerli ondalık, sekizlik ve onaltılık sabitleri gösterir.

```C
/* Decimal Constants */
10
132
32179

/* Octal Constants */
012
0204
076663

/* Hexadecimal Constants */
0xa or 0xA
0x84
0x7dB3 or 0X7DB3
```

## <a name="see-also"></a>Ayrıca bkz.

[C Sabitleri](../c-language/c-constants.md)  
