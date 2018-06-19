---
title: Derleyici Hatası C2198 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2198
dev_langs:
- C++
helpviewer_keywords:
- C2198
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6f69874b5c324250338baf480b6bd1cf1c36a1f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170056"
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