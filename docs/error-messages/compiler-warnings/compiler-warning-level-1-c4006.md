---
title: "Derleyici Uyarısı (düzey 1) C4006 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4006
dev_langs: C++
helpviewer_keywords: C4006
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab19bbf1f886321700f350029c3cf41fe0d6b00b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4006"></a>Derleyici Uyarısı (düzey 1) C4006
\#undef bir tanımlayıcı bekleniyor  
  
 `#undef` Yönergesi tanımlayıcıyı tanımsız belirtmedi. Yönergesi göz ardı edilir. Uyarıyı çözmek için bir tanımlayıcı belirttiğinizden emin olun. Aşağıdaki örnek C4006 oluşturur:  
  
```  
// C4006.cpp  
// compile with: /W1  
#undef   // C4006  
  
// try..  
// #undef TEST  
  
int main() {  
}  
```