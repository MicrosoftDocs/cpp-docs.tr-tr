---
title: "Derleyici Hatası C3168 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3168
dev_langs: C++
helpviewer_keywords: C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c96c94c15e586b98f236fb7731529cbca7087396
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3168"></a>Derleyici Hatası C3168
'type': temel alınan tür enum için geçersiz  
  
Arka plandaki için belirtilen tür `enum` türü geçerli değil. Temel alınan türü, tamsayı C++ türü veya karşılık gelen bir CLR türü olması gerekir.  
  
Aşağıdaki örnek C3168 oluşturur:  
  
```  
// C3168.cpp  
// compile with: /clr /c  
ref class G{};  
  
enum class E : G { e };   // C3168  
enum class F { f };   // OK  
```  
