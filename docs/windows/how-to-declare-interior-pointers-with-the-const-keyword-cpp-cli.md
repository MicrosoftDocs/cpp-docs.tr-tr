---
title: 'Nasıl yapılır: const anahtar sözcüğü ile iç işaretçileri bildirme (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pointers, interior
ms.assetid: 64e08b0e-9396-4046-ab51-8f6588f32330
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fdab21e0e8b9ad0b6fb1d58ba7d1bcd7020ffd10
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39568621"
---
# <a name="how-to-declare-interior-pointers-with-the-const-keyword-ccli"></a>Nasıl yapılır: const Anahtar Sözcüğü ile İç İşaretçileri Bildirme (C++/CLI)
Aşağıdaki örnek nasıl kullanılacağını gösterir **const** iç işaretçiye bildiriminde.  
  
> [!IMPORTANT]
>  Bu dil özelliği tarafından desteklenen `/clr` derleyici seçeneği, ancak tarafından `/ZW` derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// interior_ptr_const.cpp  
// compile with: /clr  
using namespace System;  
value struct V {   
   int i;  
};  
  
ref struct G {  
   V v;  
   String ^ msg;  
};  
  
interior_ptr<int> f( interior_ptr<V> pv ) {   
   return &(pv->i);   
}  
  
int main() {  
   int n = -1;  
   int o = -1;  
   interior_ptr<int> pn1 = &n;  
   *pn1 = 50;  
  
   V v;  
   v.i = 101;  
   V * npV = &v;   // ok: &v yields a pointer to the native heap  
  
   interior_ptr<int> pn2 = &n;  
   interior_ptr<V> pV = &(v);  
   pn2 = f(pV);  
   *pn2 = 50;  
  
   G ^pG = gcnew G;  
   pV = &(pG->v);   // ok: pV is an interior pointer  
  
   interior_ptr<int const> pn3 = &n;  
   // *pn3 = 5;   error because pn3 cannot be dereferenced and changed  
   pn3 = &o;   // OK, can change the memory location  
  
   interior_ptr<int> const pn4 = &n;     
   *pn4 = 5;   // OK because you can dereference and change pn4  
   // pn4 = &o;   error cannot change the memory location  
  
   const interior_ptr<const int> pn5 = &n;  
   // *pn5 = 5;   error cannot dereference and change pn5  
   // pn5 = &o;   error cannot change the memory location  
  
   const G ^ h_G = gcnew G;   // object is const, cannot modify any members of h_G or call any non-const methods  
   // h_G->msg = "test";   error h_G is const  
   interior_ptr<String^ const> int_ptr_G = &(h_G->msg);  
  
   G ^ const h_G2 = gcnew G;   // interior pointers to this obejct cannot be dereferenced and changed  
   h_G2->msg = "test";  
   interior_ptr<String^ const> int_ptr_G2 = &(h_G->msg);  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)