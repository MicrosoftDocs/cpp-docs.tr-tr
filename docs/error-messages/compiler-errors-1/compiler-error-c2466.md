---
title: "Derleyici Hatası C2466 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2466
dev_langs:
- C++
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a41ea550abff9e48973452996cf5621e6bc4c42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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