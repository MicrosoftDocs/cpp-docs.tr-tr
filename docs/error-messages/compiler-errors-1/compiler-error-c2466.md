---
title: "Derleyici Hatası C2466 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2466
dev_langs: C++
helpviewer_keywords: C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c3ad19ce37aa51bd6b670da6e857d7eccce04ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2466"></a>Derleyici Hatası C2466
bir dizi sabit boyutu 0 ayrılamıyor  
  
 Bir dizi ayrılan veya boyutu sıfır. Sabit ifade dizi boyutu sıfırdan büyük bir tamsayı olmalıdır. Bir dizi bildirimi bir sıfır alt simge ile bir sınıf, yapı veya bileşim üyesi için yalnızca ve yalnızca Microsoft uzantılı yasal ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 Aşağıdaki örnek C2466 oluşturur:  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```