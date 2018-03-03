---
title: "Yönlendirme işleci: * | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- '* operator'
- indirection operator
- operators [C++], indirection
- indirection operator [C++], syntax
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c87c279ae1f45899dfa4525c3bdc65bfa5acc2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="indirection-operator-"></a>Yönlendirme İşleci: *
## <a name="syntax"></a>Sözdizimi  
  
```  
  
* cast-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Birli indirection işleci (**\***) bir; işaretçiye diğer bir deyişle, bir l-değeri bir işaretçi değerine dönüştürür. Yöneltme işlecinin işleneni bir işaretçi bir türü olmalıdır. İşaretçi türünün türetildiği türü yöneltme ifade sonucudur. Kullanımını  **\***  bu bağlamda işlecidir kendi çarpım bir ikili işleç anlamı farklıdır.  
  
 İşlenen bir işleve işaret ediyorsa, sonuç bir işlev göstergesidir. Bir depolama konumuna işaret ediyorsa, sonuç depolama konumunu gösteren l değeridir.  
  
 İndirection işleci işaretçileri işaretçiler başvurulacak kümülatif olarak kullanılabilir. Örneğin:  
  
```  
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
  
 İşaretçi değeri geçersiz, tanımlanmamış bir sonucudur. Aşağıdaki liste, işaretçi değerini geçersiz kılan en yaygın koşulların bazılarını içermektedir.  
  
-   İşaretçi, bir null işaretçidir.  
  
-   İşaretçi, başvuru sırasında görünür olmayan yerel bir öğrenin adresini belirtir.  
  
-   İşaretçi, işaret edilen nesnenin türü için uygun olmayan bir şekilde hizalanmış bir adresi belirtir.  
  
-   İşaretçi, yürütülen program tarafından kullanılmayan bir adresi belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Address-of işleci: &](../cpp/address-of-operator-amp.md)   
 [İşleçlerin Yöneltmesi ve Adresi](../c-language/indirection-and-address-of-operators.md)