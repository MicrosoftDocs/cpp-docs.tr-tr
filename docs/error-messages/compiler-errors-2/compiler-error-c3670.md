---
title: "Derleyici Hatası C3670 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3670
dev_langs: C++
helpviewer_keywords: C3670
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 773ee85df3e19245b665521be8d65055ffe3bf17
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3670"></a>Derleyici Hatası C3670
'override': 'yöntemi' erişilemez temel sınıf yöntemi geçersiz kılamaz  
  
 Bir geçersiz kılma yalnızca, erişim düzeyi türetilmiş bir tür olarak kullanılabilir yapar işlevi üzerinde gerçekleşebilir. Daha fazla bilgi için bkz: [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C3670 oluşturur:  
  
```  
// C3670.cpp  
// compile with: /clr /c  
public ref class C {  
// Uncomment the following line to resolve.  
// public:  
   virtual void g() { }  
};  
  
public ref class D : public C {  
public:  
   virtual void f() new sealed = C::g {};   // C3670  
};  
```