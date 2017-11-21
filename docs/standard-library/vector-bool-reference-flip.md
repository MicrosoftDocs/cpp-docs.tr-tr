---
title: "vektör&lt;bool&gt;:: reference::flip | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vector/std::vector<bool>::reference::flip
dev_langs: C++
helpviewer_keywords: reference::flip method
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 788df6791b63fa15d1d0f11aeb9095ee15da5e10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vectorltboolgtreferenceflip"></a>vektör&lt;bool&gt;:: reference::flip
Başvurulan bir Boolean değerini tersine çevirir [vektör\<bool >](../standard-library/vector-bool-class.md) öğesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void flip();
```  
  
## <a name="example"></a>Örnek  
  
```cpp  
// vector_bool_ref_flip.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    cout << boolalpha;  
  
    vector<bool> vb = { true, false, false, true, true };  
  
    cout << "The vector is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
  
    vector<bool>::reference vbref = vb.front();  
    vbref.flip();  
  
    cout << "The vector with first element flipped is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
}  
  
```  
  
## <a name="output"></a>Çıkış  
  
```  
The vector is:  
    true false false true true  
The vector with first element flipped is:  
    false false false true true  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<vektör >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vektör\<bool >:: sınıfı başvurusu](../standard-library/vector-bool-reference-class.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

