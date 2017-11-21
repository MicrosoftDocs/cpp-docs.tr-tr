---
title: "Derleyici Hatası C2055 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2055
dev_langs: C++
helpviewer_keywords: C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c447d79179f3575230353b3db70717702b542b68
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2055"></a>Derleyici Hatası C2055
Beklenen biçimsel parametresi listesi, tür listesi  
  
 Bir işlev tanımı biçimsel parametresi listesini yerine parametre türü listesi içerir. ANSI C void veya üç nokta olmadıkça adlı biçimsel parametresi gerektirir (`...`).  
  
 Aşağıdaki örnek C2055 oluşturur:  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```