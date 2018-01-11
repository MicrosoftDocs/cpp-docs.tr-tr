---
title: "Derleyici Uyarısı (düzey 1) C4080 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4080
dev_langs: C++
helpviewer_keywords: C4080
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7218b2ffff179cdf17231d010f600c5ed8eafde9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4080"></a>Derleyici Uyarısı (düzey 1) C4080
segment adı için beklenen tanımlayıcı; 'simgesi' bulundu  
  
 Kesimdeki adını [#pragma alloc_text](../../preprocessor/alloc-text.md) bir dize veya bir tanımlayıcı olması gerekir. Geçerli bir tanımlayıcı bulunmazsa derleyici pragma yok sayar.  
  
 Aşağıdaki örnek C4080 oluşturur:  
  
```  
// C4080.cpp  
// compile with: /W1  
extern "C" void func(void);  
  
#pragma alloc_text()   // C4080  
  
// try this line to resolve the warning  
// #pragma alloc_text("mysection", func)  
  
int main() {  
}  
  
void func(void) {  
}  
```