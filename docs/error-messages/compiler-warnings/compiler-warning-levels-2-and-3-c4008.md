---
title: "Derleyici Uyarısı (Düzey 2 ve 3) C4008 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4008
dev_langs:
- C++
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: afd45078ac75ec9da8343baa2c203e75b324fb6e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Derleyici Uyarısı (Düzey 2 ve 3) C4008
'tanımlayıcısı': 'öznitelik' özniteliği yoksayıldı  
  
 Göz ardı derleyici `__fastcall`, **statik**, veya **satır içi** özniteliği işlevi (Düzey 3 uyarı) veya veriler (Düzey 2 uyarı).  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  `__fastcall`veri özniteliği.  
  
2.  **statik** veya **satır içi** ile öznitelik **ana** işlevi.