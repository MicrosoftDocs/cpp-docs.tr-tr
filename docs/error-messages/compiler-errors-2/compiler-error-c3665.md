---
title: Derleyici Hatası C3665 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3665
dev_langs:
- C++
helpviewer_keywords:
- C3665
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a7a8b5a93c4ed3a003eb23824e9b7207c7e26f8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3665"></a>Derleyici Hatası C3665
'yıkıcı': override tanımlayıcısı 'anahtar sözcüğü yıkıcı/sonlandırıcıyı üzerinde izin verilmiyor'  
  
 Bir anahtar sözcük, bir yıkıcı veya sonlandırıcıyı izin verilmeyen kullanıldı.  
  
 Örneğin, yeni bir yuva bir yıkıcı veya sonlandırıcıyı istenemez.  Daha fazla bilgi için bkz: [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md) ve [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Aşağıdaki örnek C3665 oluşturur:  
  
```  
// C3665.cpp  
// compile with: /clr  
public ref struct R {  
   virtual ~R() { }  
   virtual void a() { }  
};  
  
public ref struct S : R {  
   virtual ~S() new {}   // C3665  
   virtual void a() new {}   // OK  
};  
```