---
title: "Mantıksal Değilleme İşleci: ! | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs:
- C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f63d36fc5974241fb624dd3a2afc863142516e9b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Birli Aritmetik İşleçler](../c-language/unary-arithmetic-operators.md)