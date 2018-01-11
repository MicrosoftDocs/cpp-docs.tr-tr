---
title: "Derleyici Hatası C2061 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2061
dev_langs: C++
helpviewer_keywords: C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e18810742efa94cdd130c1e11a2cdda0656c9921
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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