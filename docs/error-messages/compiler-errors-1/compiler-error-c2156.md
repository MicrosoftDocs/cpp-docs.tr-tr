---
title: "Derleyici Hatası C2156 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2156
dev_langs: C++
helpviewer_keywords: C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c74ca376b44f192e784db5eef398f503a501510
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2156"></a>Derleyici Hatası C2156
pragma dış işlev olmalıdır  
  
 (Dışında bir işlev gövdesi) genel düzeyde belirtilmelidir pragma içinde bir işlevdir.  
  
 Aşağıdaki örnek C2156 oluşturur:  
  
```  
// C2156.cpp  
#pragma optimize( "l", on )   // OK  
int main() {  
   #pragma optimize( "l", on )   // C2156  
}  
```