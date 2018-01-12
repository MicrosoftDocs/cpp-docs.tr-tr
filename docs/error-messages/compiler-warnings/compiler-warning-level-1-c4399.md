---
title: "Derleyici Uyarısı (düzey 1) C4399 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4399
dev_langs: C++
helpviewer_keywords: C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eff01c29d423b0823b41bf63702cf42ee839a523
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4399"></a>Derleyici Uyarısı (düzey 1) C4399
'simgesi': işlem içi simgesi işaretlenmemiş/CLR ile derlendiğinde __declspec(dllimport) ile: Saf  
  
 **/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışıdır.  
  
 Yerel görüntü veya yerel ve CLR yapılarına görüntüyle verileri saf görüntüsüne alınamıyor. İle bu uyarıyı çözmek için derleme **/CLR** (değil **/CLR: pure**) veya silme `__declspec(dllimport)`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4399 oluşturur.  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```