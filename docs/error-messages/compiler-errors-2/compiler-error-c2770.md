---
title: "Derleyici Hatası C2770 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2770
dev_langs: C++
helpviewer_keywords: C2770
ms.assetid: 100001b5-80b0-4971-8ff6-9023f443c926
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 81179a10cc58c1b22f974b4367d471dde87bdc65
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2770"></a>Derleyici Hatası C2770
'şablon' için geçersiz açık template_or_generic bağımsız değişkenli  
  
 İzin verilmeyen işlevi türlerinde işlevi şablon adayları açık şablonu veya genel bağımsız değişkenleri ile sonuçlandı.  
  
 Aşağıdaki örnek C2770 oluşturur:  
  
```  
// C2770.cpp  
#include <stdio.h>  
template <class T>  
int f(typename T::B*);   // expects type with member B  
  
struct Err {};  
  
int main() {  
   f<int>(0);   // C2770 int has no B  
   // try the following line instead  
   f<OK>(0);  
}  
```