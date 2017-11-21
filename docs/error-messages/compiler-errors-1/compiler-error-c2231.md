---
title: "Derleyici Hatası C2231 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2231
dev_langs: C++
helpviewer_keywords: C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 48aac0a2101b6c9cf02c29fe30ea12717b996087
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2231"></a>Derleyici Hatası C2231
'.': 'sınıfı-key' işleneni noktaları sola Kullan '->'  
  
 Üye seçim işlemi (.) sol işleneni, bir sınıf, yapı veya birleşim yerine bir işaretçidir.  
  
 Aşağıdaki örnek C2231 oluşturur:  
  
```  
// C2231.c  
struct S {  
   int member;  
} s, *ps = &s;  
int main() {  
   ps.member = 0;   // C2231  
  
   // OK  
   ps->member = 0;   // crash  
   s.member = 0;  
}  
```