---
title: 'Yöneltme işleci: * | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- '* operator'
- indirection operator
- operators [C++], indirection
- indirection operator [C++], syntax
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a23951697a5f736305734c6d49044a2e33ac4783
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200499"
---
# <a name="indirection-operator-"></a>Yönlendirme İşleci: *
## <a name="syntax"></a>Sözdizimi  
  
```  
* cast-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Birli yöneltme işleci (<strong>\*</strong>) bir; işaretçiye başka bir deyişle, bir işaretçi değeri bir l-değerine dönüştürür. Yöneltme işlecinin işleneni, bir tür için bir işaretçi olması gerekir. Yöneltme ifadenin sonucu işaretçi türünün türetildiği türüdür. Kullanımını <strong>\*</strong> işleci bu bağlamda anlamını çarpma bir ikili işleç olarak farklıdır.  
  
 İşlenen bir işleve işaret ediyorsa, sonuç bir işlev göstergesidir. Bir depolama konumuna işaret ediyorsa, sonuç depolama konumunu gösteren l değeridir.  
  
 Yöneltme işleci üst üste işaretçilerin işaretçileri başvuru için kullanılabilir. Örneğin:  
  
```cpp 
// expre_Indirection_Operator.cpp  
// compile with: /EHsc  
// Demonstrate indirection operator  
#include <iostream>  
using namespace std;  
int main() {  
   int n = 5;  
   int *pn = &n;  
   int **ppn = &pn;  
  
   cout  << "Value of n:\n"  
         << "direct value: " << n << endl  
         << "indirect value: " << *pn << endl  
         << "doubly indirect value: " << **ppn << endl  
         << "address of n: " << pn << endl  
         << "address of n via indirection: " << *ppn << endl;  
}  
```  
  
 İşaretçi değeri geçersizse sonuç tanımsızdır. Aşağıdaki liste, işaretçi değerini geçersiz kılan en yaygın koşulların bazılarını içermektedir.  
  
-   İşaretçi, bir null işaretçidir.  
  
-   İşaretçi, başvuru sırasında görünür olmayan yerel bir öğrenin adresini belirtir.  
  
-   İşaretçi, işaret edilen nesnenin türü için uygun olmayan bir şekilde hizalanmış bir adresi belirtir.  
  
-   İşaretçi, yürütülen program tarafından kullanılmayan bir adresi belirtir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Address-of işleci: &](../cpp/address-of-operator-amp.md)   
 [İşleçlerin Yöneltmesi ve Adresi](../c-language/indirection-and-address-of-operators.md)