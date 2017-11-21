---
title: "C tamsayı sabitleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 20025ae47491084436864481357125e741ccc486
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="c-integer-constants"></a>C Tamsayı Sabitleri
"Tamsayı sabiti" ondalık (10 tabanı), sekizli (8 tabanı) veya bir tam sayı değeri temsil eden onaltılı (16 tabanı) sayı olabilir. Tamsayı sabitleri değiştirilemez tamsayı değerlerini temsil edecek şekilde kullanın.  
  
## <a name="syntax"></a>Sözdizimi  
 *tamsayı sabiti*:  
 *ondalık sabiti tamsayı sonek* iptal et  
  
 *sabiti sekizlik tamsayı sonek* iptal et  
  
 *onaltılık sabiti tamsayı sonek* iptal et  
  
 *ondalık sabiti*:  
 *sıfır olmayan basamaklı*  
  
 *Sabit ondalık basamak*  
  
 *sabiti sekizli*:  
 **0**  
  
 *sekizlik sabiti sekizli basamak*  
  
 *onaltılık sabiti*:  
 **0 x***onaltılık basamak*   
  
 **0 X***onaltılık basamak*   
  
 *onaltılık basamaklı onaltılık sabiti*  
  
 *sıfır olmayan basamaklı*: biri  
 **1 2 3 4 5 6 7 8 9**  
  
 *sekizli basamak*: biri  
 **0 1 2 3 4 5 6 7**  
  
 *onaltılık basamaklı*: biri  
 **0 1 2 3 4 5 6 7 8 9**  
  
 **b c d e f**  
  
 **A B C D E F**  
  
 *tamsayı sonek*:  
 *İmzasız soneki uzun-soneki* iptal et  
  
 *İmzasız Long soneki-soneki* iptal et  
  
 *İmzasız soneki*: biri  
 **u U**  
  
 *uzun soneki*: biri  
 **l m**  
  
 *64 bit tamsayı sonek*:  
 **I64**  
  
 Bir eksi işareti koyarak sürece tamsayı sabitleri pozitif (**-**). Eksi işareti birli aritmetik değilleme işleci yorumlanır. (Bkz [birli aritmetik işleçler](../c-language/unary-arithmetic-operators.md) bu işleci hakkında bilgi için.)  
  
 Tamsayı sabiti ile başlıyorsa **0 x** veya **0 X**, onaltılık. Basamaklı başlıyorsa **0**, sekizli. Aksi takdirde, ondalık olduğu varsayılır.  
  
 Aşağıdaki satırları eşdeğerdir:  
  
```  
0x1C   /* = Hexadecimal representation for decimal 28 */  
034    /* = Octal representation for decimal 28 */  
```  
  
 Hiçbir boşluk karakterleri tamsayı sabiti basamak ayırabilirsiniz. Bu örnekler, geçerli ondalık, sekizlik ve onaltılık sabitleri gösterir.  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C sabitleri](../c-language/c-constants.md)