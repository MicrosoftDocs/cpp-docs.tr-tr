---
title: "Nasıl yapılır: değer türleri oluşturmak ve örtük kutulamayı için gcnew kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: db569feb489fc73c7460e2444e3d2340c1a5be13
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing"></a>Nasıl yapılır: Değer Türleri Oluşturmak için gcnew Kullanma ve Örtük Kutulamayı Kullanma
Kullanarak [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) bir değerini daha sonra managed, atık toplanan yığında yerleştirilebilir paketlenmiş değer türü, türü oluşturur.  
  
## <a name="example"></a>Örnek  
  
```  
// vcmcppv2_explicit_boxing4.cpp  
// compile with: /clr  
public value class V {  
public:  
   int m_i;  
   V(int i) : m_i(i) {}  
};  
  
public ref struct TC {  
   void do_test(V^ v) {  
      if (v != nullptr)  
         ;  
      else  
         ;  
   }  
};  
  
int main() {  
   V^ v = gcnew V(42);  
   TC^ tc = gcnew TC;  
   tc->do_test(v);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kutulama](../windows/boxing-cpp-component-extensions.md)