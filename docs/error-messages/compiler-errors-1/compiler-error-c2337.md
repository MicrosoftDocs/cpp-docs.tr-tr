---
title: "Derleyici Hatası C2337 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2337
dev_langs: C++
helpviewer_keywords: C2337
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4ca2d5a7108d181ee6e93e94119b945ed7b9da9f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2337"></a>Derleyici Hatası C2337
'öznitelik adı': öznitelik bulunamadı  
  
 Visual C++'ın bu sürümünde desteklenmeyen bir öznitelik kullandınız.  
  
 Aşağıdaki örnek C2337 oluşturur:  
  
```  
// C2337.cpp  
// compile with: /c  
[emitidl];  
[module(name="x")];  
[grasshopper]   // C2337, not a supported attribute  
class a{};  
```