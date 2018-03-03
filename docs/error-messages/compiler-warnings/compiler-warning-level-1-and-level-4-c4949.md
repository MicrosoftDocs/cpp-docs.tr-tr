---
title: "Derleyici Uyarısı (düzey 1 ve düzey 4) C4949 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4949
dev_langs:
- C++
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d23a6d6e030007289cc50ce0372acc8f99e7ed3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>Derleyici Uyarısı (düzey 1 ve düzey 4) C4949
'yönetilen' ve 'yönetilmeyen' pragmaları yalnızca ile derlendiğinde anlamlı ' / clr [: seçeneği]'  
  
 Derleyici yoksayar [yönetilen](../../preprocessor/managed-unmanaged.md) ve kaynak kodu ile derlenmiş değil ise pragmaları yönetilmeyen [/CLR](../../build/reference/clr-common-language-runtime-compilation.md). Bu uyarı, bilgi amaçlıdır.  
  
 Aşağıdaki örnek C4949 oluşturur:  
  
```  
// C4949.cpp  
// compile with: /LD /W1  
#pragma managed   // C4949  
```  
  
 Zaman **yönetilmeyen #pragma** olmadan kullanılan **/CLR**, C4949 olan düzey 4 uyarı.  
  
 Aşağıdaki örnek C4949 oluşturur:  
  
```  
// C4949b.cpp  
// compile with: /LD /W4  
#pragma unmanaged   // C4949  
```