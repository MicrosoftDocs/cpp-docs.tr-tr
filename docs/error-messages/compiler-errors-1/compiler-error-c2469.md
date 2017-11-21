---
title: "Derleyici Hatası C2469 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2469
dev_langs: C++
helpviewer_keywords: C2469
ms.assetid: 3814bdff-581a-4d3e-8b47-8de6887cea69
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0b92a60a8e43c876466e21313a41eba1481a33ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2469"></a>Derleyici Hatası C2469
'işleci': 'type' nesnesi ayrılamıyor  
  
 Bir işleç geçersiz bir tür geçirildi.  
  
 Aşağıdaki örnek C2469 oluşturur:  
  
```  
// C2469.cpp  
int main() {  
   int *i = new void;   // C2469  
   int *i = new int;   // OK  
}  
```