---
title: 'Birli artı ve değilleme işleçleri: + ve - | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs:
- C++
helpviewer_keywords:
- unary operators [C++], plus
- '- operator'
- negation operator
- + operator [C++], unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06e7f6bd089866619d82798bb220580e8a11b04b
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460899"
---
# <a name="unary-plus-and-negation-operators--and--"></a>Birli Artı ve Değilleme işleçleri: + ve -
## <a name="syntax"></a>Sözdizimi  
  
```  
+ cast-expression  
- cast-expression  
```  
  
## <a name="-operator"></a>+ işleci  
 Tek işlenenli artı sonucunu (**+**), işleneninin değeridir. Tek işlenenli artı işleminin işleneni, aritmetik bir türden olmalıdır.  
  
 İntegral işlenenlerde integral yükseltme gerçekleştirilir. Sonuç türü, işlenin yükseltildiği türdür. Bu nedenle, ifade `+ch`burada `ch` türünde **char**, türüyle sonuçlanır **int**; değer değiştirilmez. Bkz: [standart dönüştürmeler](standard-conversions.md) yükseltmenin nasıl yapılacağı hakkında daha fazla bilgi.  
  
## <a name="--operator"></a>- işleci  
 Tekli değilleme işleci (**-**), işleneninin negatifini üretir. Tekli değilleme işleci için işlenen, aritmetik bir türü olmalıdır.  
  
 İntegral yükseltme, iç işlenenlerde gerçekleştirilir ve ortaya çıkan tür işlenenin yükseltildiği türdür. Bkz: [standart dönüştürmeler](standard-conversions.md) yükseltmenin nasıl gerçekleştirildiğini hakkında daha fazla bilgi.  
  
## <a name="microsoft-specific"></a>Microsoft'a özgü  
 Tekli olumsuzlama işaretsiz miktarlar, işlenenin 2'den çıkarılmasıyla gerçekleştirilir ^ n, n, bit işaretsiz belirtilen türde bir nesne sayısı.
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)