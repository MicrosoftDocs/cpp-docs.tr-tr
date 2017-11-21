---
title: "Derleyici Hatası C3911 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3911
dev_langs: C++
helpviewer_keywords: C3911
ms.assetid: b786da59-0e99-479d-bc0d-551126e940f2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4869cf6d5a1619aa692f3076de3e3c7d00bc7c16
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3911"></a>Derleyici Hatası C3911
'event_accessor_method': işlevi türü 'imzası' olmalıdır  
  
 Olay erişimci yöntemi düzgün bildirilmedi.  
  
 Daha fazla bilgi için bkz: [olay](../../windows/event-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C3911 oluşturur:  
  
```  
// C3911.cpp  
// compile with: /clr  
using namespace System;  
delegate void H(String^, int);  
  
ref class X {  
   event H^ E1 {  
      void add() {}   // C3911  
      // try the following line instead  
      // void add(H ^ h) {}  
  
      void remove(){}  
      // try the following line instead  
      // void remove(H ^ h) {}  
  
      void raise(){}  
      // try the following line instead  
      // void raise(String ^ s, int i) {}  
   };  
};  
```