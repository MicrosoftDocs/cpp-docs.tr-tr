---
title: Derleyici Uyarısı (düzey 1) C4399 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b39f4919dd736e4bf2e6230fe68ea69c2b14766e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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