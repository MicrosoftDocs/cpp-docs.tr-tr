---
title: Derleyici Hatası C2466 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2466
dev_langs:
- C++
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e55e5c130b0a0454577a7155b704a18933b86198
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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