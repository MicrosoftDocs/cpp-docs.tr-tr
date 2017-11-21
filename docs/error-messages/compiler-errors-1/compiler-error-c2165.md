---
title: "Derleyici Hatası C2165 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2165
dev_langs: C++
helpviewer_keywords: C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8d319826edac5ccdb83ab69b89abc11d5e54b68
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2165"></a>Derleyici Hatası C2165
'anahtar sözcüğü': verilere işaretçileri değiştirilemiyor  
  
 `__stdcall`, `__cdecl`, Veya `__fastcall` anahtar sözcüğü veri için bir işaretçi değiştirme dener.  
  
 Aşağıdaki örnek C2165 oluşturur:  
  
```  
// C2165.cpp  
// compile with: /c  
char __cdecl *p;   // C2165  
char *p;   // OK  
```