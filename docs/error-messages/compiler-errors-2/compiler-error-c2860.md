---
title: "Derleyici Hatası C2860 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2860
dev_langs: C++
helpviewer_keywords: C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 53a5d08e6a6b9fbbd0aba9156bc85c4f2ef8dae0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2860"></a>Derleyici Hatası C2860
'void' dışında (boş) bir bağımsız değişken türü olamaz  
  
 Tür `void` bir bağımsız değişken türü ile başka bir bağımsız değişken olarak kullanılamaz.  
  
 Aşağıdaki örnek C2860 oluşturur:  
  
```  
// C2860.cpp  
// compile with: /c  
void profunc1(void, int i);   // C2860  
void func10(void);   // OK  
```