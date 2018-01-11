---
title: "Derleyici Hatası C3216 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3216
dev_langs: C++
helpviewer_keywords: C3216
ms.assetid: bbab1efe-8779-4489-8bb0-b11e45f5cbe5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb712077335703b68cdb7ace60f72ca845a724d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3216"></a>Derleyici Hatası C3216
kısıtlama değil 'type' genel bir parametresi olmalıdır  
  
 Bir kısıtlama ill oluşturulmuş.  
  
 Aşağıdaki örnek C3216 oluşturur:  
  
```  
// C3216.cpp  
// compile with: /clr  
interface struct A {};  
  
generic <class T>  
where F : A   // C3216  
// Try the following line instead:  
// where T : A    // C3216  
ref class C {};  
```  
  
 Aşağıdaki örnek, olası bir çözüm gösterilmektedir:  
  
```  
// C3216b.cpp  
// compile with: /clr /c  
interface struct A {};  
  
generic <class T>  
where T : A  
ref class C {};  
```