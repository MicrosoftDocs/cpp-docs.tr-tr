---
title: "Derleyici Hatası C2904 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2904
dev_langs: C++
helpviewer_keywords: C2904
ms.assetid: d5802f2e-d3fc-473d-aa04-36957b4eaca5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b177a7725b1ed6c411e4ffaebfce34860377e34e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2904"></a>Derleyici Hatası C2904
'tanımlayıcısı': adı geçerli kapsamdaki bir şablon için zaten kullanılıyor  
  
 Yinelenen adlar kodunu denetleyin.  
  
 Aşağıdaki örnek C2904 oluşturur:  
  
```  
// C2904.cpp  
// compile with: /c  
void X();  // X is declared as a function  
template<class T> class X{};  // C2904  
```