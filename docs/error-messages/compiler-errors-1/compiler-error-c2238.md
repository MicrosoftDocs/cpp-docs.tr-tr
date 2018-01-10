---
title: "Derleyici Hatası C2238 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2238
dev_langs: C++
helpviewer_keywords: C2238
ms.assetid: 3d53060c-d6b7-4603-b9cf-d7c65eb64cd2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa7baf24ba564c8939fac0bfdf0e2c4f39f6d1e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2238"></a>Derleyici Hatası C2238
'belirteci' önceki beklenmeyen belirteçleri  
  
 Yanlış bir belirteç bulundu.  
  
 Aşağıdaki örnek C2238 oluşturur:  
  
```  
// C2238.cpp  
// compile with: /c  
class v {  
virtual: int vvv;   // C2238  
};  
```