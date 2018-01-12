---
title: "Derleyici Hatası C3650 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3650
dev_langs: C++
helpviewer_keywords: C3650
ms.assetid: ca4d8de4-b027-4d13-9b9f-03ca62905c33
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d823892e2f8e117a7be766765ccbb57a04804da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3650"></a>Derleyici Hatası C3650
'interface_method': açık geçersiz kılma olarak kullanılamaz, bir taban sınıfın sanal üye işlevi olmalıdır.  
  
 Açık geçersiz kılma sanal değildi üyede gerçekleştirmek için girişimde bulunuldu.  
  
 Daha fazla bilgi için bkz: [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C3650 oluşturur:  
  
```  
// C3650.cpp  
// compile with: /clr  
public interface struct I {  
   void a();  
};  
  
public ref class S {  
public:  
   static int f() { return 0; }  
   static int g() { return 0; }  
};  
  
public ref struct T1 : public S, I {  
   virtual int f() new sealed = S::f;   // C3650  
   virtual int g() { return 0; }   // OK does not override S::g  
   virtual void a() new sealed = I::a {}   // OK  
};  
```