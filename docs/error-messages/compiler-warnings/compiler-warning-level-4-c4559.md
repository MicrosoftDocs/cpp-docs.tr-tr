---
title: "Derleyici Uyarısı (düzey 4) C4559 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4559
dev_langs:
- C++
helpviewer_keywords:
- C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa3dcd3bc2af9e7a9376ff6a2e5db31dbbe9c898
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4559"></a>Derleyici Uyarısı (düzey 4) C4559
'function': şemadaki; işlev kazançlar __declspec(modifier)  
  
 Bir işlev yeniden tanımlandı veya yeniden bildirilen ve ikinci tanımı veya bildirimi eklenen bir __**declspec** değiştiricisi (***değiştiricisi***). Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözmenin tanımları birini silin.  
  
 Aşağıdaki örnek C4559 oluşturur:  
  
```  
// C4559.cpp  
// compile with: /W4 /LD  
void f();  
__declspec(noalias) void f();   // C4559  
```