---
title: Derleyici Hatası C2464 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2464
dev_langs:
- C++
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98949ba463f432666753cb39de37bb4bf8f7276f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226032"
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