---
title: "Derleyici Hatası C2462 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2462
dev_langs: C++
helpviewer_keywords: C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7ddb841157bbd29e66812a30ea433868597f4ecc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2462"></a>Derleyici Hatası C2462
'tanımlayıcısı': türü bir 'yeni ifadede' tanımlanamıyor  
  
 İşlenen alanında bir türü tanımlayamazsınız `new` işleci. Tür tanımı ayrı bir deyimde yerleştirin.  
  
 Aşağıdaki örnek C2462 oluşturur:  
  
```  
// C2462.cpp  
int main() {  
   new struct S { int i; };   // C2462  
}  
```