---
title: "Derleyici Hatası C2324 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2324
dev_langs: C++
helpviewer_keywords: C2324
ms.assetid: 215f0544-85b0-452d-825f-17a388b6a61c
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 34ce2658607f673806d93579bc6d47a59d5206cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2324"></a>Derleyici Hatası C2324
'tanımlayıcısı': 'name' nın sağındaki beklenmeyen  
  
 Bir yıkıcı bir hatalı tanımlayıcı kullanılarak çağrılır.  
  
 Aşağıdaki örnek C2324 oluşturur:  
  
```  
// C2324.cpp  
class A {};  
typedef A* pA_t;  
int i;  
  
int main() {  
   pA_t * ppa = new pA_t;  
   ppa->~i;   // C2324  
   ppa->~pA_t();   // OK  
}  
```