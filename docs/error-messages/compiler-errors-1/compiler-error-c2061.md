---
title: Derleyici Hatası C2061 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2061
dev_langs:
- C++
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4d4b018dbab16e8e376a3331a85d0f1b1004f5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2061"></a>Derleyici Hatası C2061
sözdizimi hatası: 'tanımlayıcısı' tanımlayıcısı  
  
 Derleyici beklenirken değildi tanıtıcısı bulunamadı. Olduğundan emin olun `identifier` kullanmadan önce bildirilir.  
  
 Bir başlatıcı parantez. Bu sorunu önlemek için bildirimcisi parantez içine alın veya onu bir `typedef`.  
  
 Sınıf şablonu bağımsız değişkeni olarak bir ifade derleyici algıladığında, bu hata ayrıca nedeni olabilir; kullanmak [typename](../../cpp/typename.md) derleyici bir türü olduğunu bildirmek için.  
  
 Aşağıdaki örnek C2061 oluşturur:  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 Bir örnek adı geçirirseniz C2061 oluşabilir [TypeID](../../windows/typeid-cpp-component-extensions.md):  
  
```  
// C2061b.cpp  
// compile with: /clr  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   System::Type ^ pType = typeid<pG>;   // C2061  
   System::Type ^ pType2 = typeid<G>;   // OK  
}  
```