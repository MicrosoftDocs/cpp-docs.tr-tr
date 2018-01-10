---
title: "Derleyici Hatası C2541 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2541
dev_langs: C++
helpviewer_keywords: C2541
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1694b8b71f7dbc2142e81e193190afa87b99bde4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2541"></a>Derleyici Hatası C2541
'delete': silin: işaretçiler olmayan nesneler silinemiyor  
  
 [Silmek](../../cpp/delete-operator-cpp.md) işleci bir işaretçi olmayan bir nesnede kullanıldı.  
  
 Aşağıdaki örnek C2541 oluşturur:  
  
```  
// C2541.cpp  
int main() {  
   int i;  
   delete i;   // C2541 i not a pointer  
  
   // OK  
   int *ip = new int;  
   delete ip;  
}  
```