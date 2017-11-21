---
title: "Derleyici Uyarısı (düzey 1) C4606 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4606
dev_langs: C++
helpviewer_keywords: C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8cabc2eb00cb1944a19ac31b5f0f30deb3857c04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4606"></a>Derleyici Uyarısı (düzey 1) C4606
\#pragma uyarısı: 'warning_number göz ardı;' Kod çözümleme uyarıları uyarı düzeyleri ile ilişkili değil  
  
 Kod çözümleme uyarıları, yalnızca için `error`, `once`, ve `default` ile desteklenen [uyarı](../../preprocessor/warning.md) pragması.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4606 oluşturur.  
  
```  
// C4606.cpp  
// compile with: /c /W1  
#pragma warning(1: 6001)   // C4606  
#pragma warning(once: 6001)   // OK  
```