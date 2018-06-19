---
title: Derleyici Hatası C3765 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3765
dev_langs:
- C++
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb8370a5c9c25fee211636214a82f22c05ccb311
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274774"
---
# <a name="compiler-error-c3765"></a>Derleyici Hatası C3765
'event': olay 'type', bir event_receiver işaretlenmiş bir sınıf/yapı tanımlayamazsınız  
  
 Bir sınıf ile işaretlenmişse [event_receiver](../../windows/event-receiver.md) özniteliği, sınıf içeremez bir [__event](../../cpp/event.md) bildirimi.  
  
 Aşağıdaki örnek C3765 oluşturur:  
  
```  
// C3765.cpp  
[event_receiver(native)]  
struct ER2 {  
   __event void f();   // C3765  
   __event void b(int);   // C3765  
};  
```