---
title: Derleyici Hatası C2161 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2161
dev_langs:
- C++
helpviewer_keywords:
- C2161
ms.assetid: d6798821-13bb-4e60-924f-85f7bf955387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62ea3ec8d0d4ac4cb47f61d23473b1faabc3a894
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33168210"
---
# <a name="compiler-error-c2161"></a>Derleyici Hatası C2161
' ##' bir makro tanımı sonunda olamaz  
  
 Makro tanımı sona bir belirteç yapıştıran işleç (#).  
  
 Aşağıdaki örnek C2161 oluşturur:  
  
```  
// C2161.cpp  
// compile with: /c  
#define mac(a,b) a   // OK  
#define mac(a,b) a##   // C2161  
```