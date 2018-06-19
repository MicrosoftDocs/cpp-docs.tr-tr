---
title: Derleyici Uyarısı (düzey 1) C4612 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0983f5d0bb89eaf1daee94468b318557bc83cd05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281888"
---
# <a name="compiler-warning-level-1-c4612"></a>Derleyici Uyarısı (düzey 1) C4612
hataya dahil etmek, dosya adı  
  
 Bu uyarı oluşur **#pragma include_alias** ne zaman bir dosya adı yanlış veya eksik.  
  
 Bağımsız değişkenleri **#pragma include_alias** deyimi tekliften kullanabilirsiniz (**"***filename***"**) veya açılı ayraç biçiminde ( **\< ***filename***>**), ancak her ikisi de aynı form kullanmanız gerekir.  
  
## <a name="example"></a>Örnek  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```