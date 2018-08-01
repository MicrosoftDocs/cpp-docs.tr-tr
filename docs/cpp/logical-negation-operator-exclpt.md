---
title: 'Mantıksal Değilleme İşleci: ! | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f911c6f01dfc188c26355a3749d8a130f0d6951
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403595"
---
# <a name="logical-negation-operator-"></a>Mantıksal Değilleme İşleci: !
## <a name="syntax"></a>Sözdizimi  
  
```  
! cast-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Mantıksal değilleme işleci (**!**), işlenenin anlamını tersine çevirir. İşlenen, aritmetik veya işaretçi türünde (veya aritmetik ya da işaretçi türü olarak değerlendirilen bir ifade) olmalıdır. İşlenen örtülü olarak türüne dönüştürülür **bool**. Dönüştürülen işlenen FALSE ise, sonuç değeri True'dur; Dönüştürülen işlenen TRUE ise sonuç FALSE olur. Sonuç türünde **bool**.  
  
 Bir ifade için *e*, birli ifadesi **! *** e* ifadesine eşdeğerdir **(*** e* `==` 0), aşırı yüklenmiş işleçler dahil olduğu dışında.  
  
## <a name="operator-keyword-for-"></a>! için İşleç Anahtar Sözcüğü  
 **Değil** işlecidir öğesinin metin eşdeğeridir **!**. Erişmenin iki yöntemi vardır **değil** programlarınızda işleci: üstbilgi dosyasını dahil `iso646.h`, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırakma) derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Birli Aritmetik İşleçler](../c-language/unary-arithmetic-operators.md)