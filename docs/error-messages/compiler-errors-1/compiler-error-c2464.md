---
title: "Derleyici Hatası C2464 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2464
dev_langs: C++
helpviewer_keywords: C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7e2600608ae490363d9042ad72ad91bf7cfe32d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2464"></a>Derleyici Hatası C2464
'tanımlayıcısı': 'new' bir başvuru ayırmak için kullanılamaz  
  
 Başvuru kimliği ile ayrıldı `new` işleci. Başvuruları olmayan bellek nesneleri, bu nedenle `new` bir işaretçi bunları geri dönemezsiniz. Bir başvuru bildirmek için standart değişken bildirimi sözdizimini kullanın.  
  
 Aşağıdaki örnek C2464 oluşturur:  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```