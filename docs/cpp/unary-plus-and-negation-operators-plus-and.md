---
title: 'Birli artı ve değilleme işleçleri: + ve - | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8211cf9ebef808ad428e4c94ba97c6bcd22897ea
ms.sourcegitcommit: cdd4808dcb274bbb29618286df4d1d4acd35b9bc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/30/2018
---
# <a name="unary-plus-and-negation-operators--and--"></a>Birli Artı ve Değilleme işleçleri: + ve -
## <a name="syntax"></a>Sözdizimi  
  
```  
  
+ cast-expression  
```  
  
```  
  
- cast-expression  
```  
  
## <a name="-operator"></a>+ işleci  
 Birli artı işleci sonucu (**+**), işlenen değeri. Tek işlenenli artı işleminin işleneni, aritmetik bir türden olmalıdır.  
  
 İntegral işlenenlerde integral yükseltme gerçekleştirilir. Sonuç türü, işlenin yükseltildiği türdür. Bu nedenle, `+ch`'nin `ch` türünde olduğu `char` ifadesi, `int` türüyle sonuçlanır; değer değiştirilmez. Bkz: [standart dönüşümler](standard-conversions.md) nasıl yükseltme yapılacağı hakkında daha fazla bilgi.  
  
## <a name="--operator"></a>- işleci  
 Tekli değilleme işleci (**-**), işlenen negatif üretir. Tekli değilleme işleci için işlenen aritmetik bir türü olmalıdır.  
  
 İntegral yükseltme, iç işlenenlerde gerçekleştirilir ve ortaya çıkan tür işlenenin yükseltildiği türdür. Bkz: [standart dönüşümler](standard-conversions.md) yükseltme nasıl gerçekleştirildiğini hakkında daha fazla bilgi.  
  
## <a name="microsoft-specific"></a>Belirli Microsoft  
 Tekli değilleme imzasız miktarlarının işleneni 2 değerini çıkarılmasıyla gerçekleştirilir ^ burada n verilen imzasız türünde bir nesne bit sayısını alır.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
