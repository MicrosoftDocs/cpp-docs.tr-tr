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
ms.openlocfilehash: 980341a7871d314e3173449234fbb597a5b55d63
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
