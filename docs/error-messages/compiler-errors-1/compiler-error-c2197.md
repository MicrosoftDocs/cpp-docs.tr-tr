---
title: "Derleyici Hatası C2197 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2197
dev_langs: C++
helpviewer_keywords: C2197
ms.assetid: 6dd5a6ec-bc80-41b9-a4ac-46f80eaca42d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3b2f3482a8f66098d42389234924fee9238b7ed0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2197"></a>Derleyici Hatası C2197
'function': çağrısı için çok fazla bağımsız değişken  
  
 Derleyici arama işlevi ya da yanlış işlev bildirimi için çok fazla parametre algılandı.  
  
 Aşağıdaki örnek C2197 oluşturur:  
  
```  
// C2197.c  
// compile with: /Za /c  
void func( int );  
int main() {  
   func( 1, 2 );   // C2197 two actual parameters  
   func( 2 );   // OK  
}  
```