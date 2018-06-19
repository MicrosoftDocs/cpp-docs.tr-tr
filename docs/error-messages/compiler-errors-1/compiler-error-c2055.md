---
title: Derleyici Hatası C2055 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2055
dev_langs:
- C++
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f16d9c3948c0211da69142f1b9c7c1a6a32d8c37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169338"
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