---
title: "Derleyici Hatası C3253 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3253
dev_langs: C++
helpviewer_keywords: C3253
ms.assetid: da40be26-0f78-4730-8727-ad11cddf8869
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5eae8e6bae423cb24e2a364ef59309d4110ccc49
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3253"></a>Derleyici Hatası C3253
'function': açık geçersiz kılma hatasıyla  
  
 Açık geçersiz kılma hatalı şekilde belirtildi. Örneğin, bir uygulama da saf olarak belirttiğiniz bir geçersiz kılma için belirtilemez. Daha fazla bilgi için bkz: [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C3253 oluşturur:  
  
```  
// C3253.cpp  
// compile with: /clr  
public interface struct I {  
   void a();  
   void b();  
   void c();  
};  
  
public ref struct R : I {  
   virtual void a() = 0, I::a {}   // C3253  
   virtual void b() = I::a {}   // OK  
   virtual void c() = 0;   // OK  
};  
```