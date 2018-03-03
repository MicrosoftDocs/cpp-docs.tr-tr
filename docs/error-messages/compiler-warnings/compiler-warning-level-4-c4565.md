---
title: "Derleyici Uyarısı (düzey 4) C4565 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4565
dev_langs:
- C++
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b89da26312c68bc76d23fc829a14f17db3d601b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4565"></a>Derleyici Uyarısı (düzey 4) C4565
'function': şemadaki; simgenin __declspec(modifier) ile önceden bildirildi  
  
 Bir simge yeniden tanımlandı ya da yeniden bildirilen ve ikinci tanımı ya da ilk tanımı veya bildirimi aksine bildiriminde değil sahip bir `__declspec` değiştiricisi (***değiştiricisi***). Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözmenin tanımları birini silin.  
  
 Aşağıdaki örnek C4565 oluşturur:  
  
```  
// C4565.cpp  
// compile with: /W4 /LD  
__declspec(noalias) void f();  
void f();   // C4565  
```