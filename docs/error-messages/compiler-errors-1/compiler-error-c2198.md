---
title: "Derleyici Hatası C2198 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2198
dev_langs: C++
helpviewer_keywords: C2198
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 344ddd28dace0c50cb4071e56447cbb08d5fad27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2198"></a>Derleyici Hatası C2198
'function': çağrısı için çok az sayıda bağımsız değişken  
  
 Derleyici arama işlevi ya da yanlış işlev bildirimi için çok az sayıda parametre bulundu.  
  
 Aşağıdaki örnek C2198 oluşturur:  
  
```  
// C2198.c  
// compile with: /c  
void func( int, int );  
int main() {  
   func( 1 );   // C2198 only one actual parameter  
   func( 1, 1 );   // OK  
}  
```