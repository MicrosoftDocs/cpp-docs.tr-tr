---
title: Tamsayı türleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integer data type, integer types in C++
- integer constants
- integer types
- integers, types
ms.assetid: c8926a5e-0e98-4e37-9b05-ce97961379bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acc3dc7631602e8accd9574bf707798dae5ba0d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="integer-types"></a>Tam Sayı Türleri
Her tam sayı sabit değeri ve ifade edilir şekilde dayalı bir tür verilir. Türü için hiçbir tamsayı sabiti zorlayabilirsiniz **uzun** harf ekleyerek **l** veya **L** türü olmasını zorla; sabiti sonuna `unsigned` ekleyerek **u** veya **U** değerine. Küçük harf **l** 1 basamaklı kafası olabilir ve kaçınılmalıdır. Bazı formları **uzun** tamsayı sabitleri izleyin:  
  
```  
/* Long decimal constants */  
10L  
79L  
  
/* Long octal constants */  
012L  
0115L  
  
/* Long hexadecimal constants */  
0xaL or 0xAL  
0X4fL or 0x4FL  
  
/* Unsigned long decimal constant */  
776745UL  
778866LU  
```  
  
 Bir sabite atama türü sabiti temsil eden değerine bağlıdır. Sabit ait değer türü için gösterilebilir değer aralığında olması gerekir. Hangi dönüşümleri veya sabit bir ifadede kullanılan zaman gerçekleştirilen sabit 's türü belirler eksi işareti (**-**) uygulanır. Bu liste tamsayı sabitleri dönüştürme kurallarını özetler.  
  
-   İçin bir son eki olmadan bir ondalık sabit ya da türüdür `int`, **uzun tamsayı**, veya **imzasız long int**. İlk sabit ait değer gösterilebilir bu üç tür sabite atanan türüdür.  
  
-   Sekizlik ve onaltılık sabitleri sonekleri olmadan atanan türü `int`, `unsigned int`, **uzun tamsayı**, veya **imzasız long int** sabiti boyutuna bağlı olarak.  
  
-   Sabitler ile atanan türü bir **u** veya **U** sonekidir **imzasız int** veya **imzasız long int** boyutlarına bağlı olarak.  
  
-   Sabitler ile atanan türü bir **l** veya **L** sonekidir **uzun tamsayı** veya **imzasız long int** boyutlarına bağlı olarak.  
  
-   Sabitler ile atanan türü bir **u** veya **U** ve bir **l** veya **L** sonekidir **imzasız long int**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Tamsayı Sabitleri](../c-language/c-integer-constants.md)