---
title: "Mantıksal Değilleme İşleci: ! | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs: C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd8169d2281f1cbd77063eddc312fa93655b99dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="logical-negation-operator-"></a>Mantıksal Değilleme İşleci: !
## <a name="syntax"></a>Sözdizimi  
  
```  
  
! cast-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Mantıksal değilleme işleci (**!**), işlenen anlamını tersine çevirir. İşlenen, aritmetik veya işaretçi türünde (veya aritmetik ya da işaretçi türü olarak değerlendirilen bir ifade) olmalıdır. İşlenen, örtülü olarak `bool` türüne dönüştürülür. Sonuç **true** dönüştürülmüş işleneni ise **false**; sonuç **false** dönüştürülmüş işleneni ise **doğru**. Sonuç, `bool` türündedir.  
  
 Bir ifadenin *e*, tek terimli ifadesi **!** *e* ifade eşdeğerdir **(***e* `==` 0), aşırı yüklenmiş işleçler söz konusu olduğu dışında.  
  
## <a name="operator-keyword-for-"></a>! için İşleç Anahtar Sözcüğü  
 **Değil** işlecidir metin denk **!**. Erişmek için iki yolla **değil** programlarınızı işleci: üst bilgi dosyasını dahil `iso646.h`, veya ile derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
```  
// expre_Logical_NOT_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 0;  
   if (!i)  
      cout << "i is zero" << endl;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Birli aritmetik işleçler](../c-language/unary-arithmetic-operators.md)