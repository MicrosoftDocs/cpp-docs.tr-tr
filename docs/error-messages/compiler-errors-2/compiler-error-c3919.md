---
title: "Derleyici Hatası C3919 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3919
dev_langs: C++
helpviewer_keywords: C3919
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 856954bdadfd4bd418ef412762f8cc3d79e47240
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3919"></a>Derleyici Hatası C3919
'event_method': işlevi türü 'type' olması gerekir  
  
 Bir olay erişimci yöntemi doğru bildirilmedi.  
  
 Olaylar hakkında daha fazla bilgi için bkz: [olay](../../windows/event-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C3919 oluşturur:  
  
```  
// C3919.cpp  
// compile with: /clr /c  
using namespace System;  
delegate void D(String^);  
ref class R {  
   event D^ e {  
      int add(int);   // C3919  
      int remove(int);   // C3919  
  
      void add(D^);   // OK  
      void remove(D^);   // OK  
   }  
};  
```