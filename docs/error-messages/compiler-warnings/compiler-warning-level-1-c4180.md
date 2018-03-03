---
title: "Derleyici Uyarısı (düzey 1) C4180 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4180
dev_langs:
- C++
helpviewer_keywords:
- C4180
ms.assetid: 40c91bd4-37f1-4d59-a4f3-d5ddab68239b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e94979e9546ebf035c95ddc75db4edcd0f80afa1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4180"></a>Derleyici Uyarısı (düzey 1) C4180
Niteleyici işlev türü için uygulanan bir anlamı yoktur; göz ardı  
  
 Bir niteleyici gibi **const**, tarafından tanımlanan bir işlev türü için uygulanan `typedef`.  
  
## <a name="example"></a>Örnek  
  
```  
// C4180.cpp  
// compile with: /W1 /c  
typedef int FuncType(void);  
  
// the const qualifier cannot be applied to the  
// function type FuncType  
const FuncType f;   // C4180  
```