---
title: "Derleyici Uyarısı (düzey 1) C4612 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 922da98a54a572462d2b247f6211a39bcaed9ec6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4612"></a>Derleyici Uyarısı (düzey 1) C4612
hataya dahil etmek, dosya adı  
  
 Bu uyarı oluşur **#pragma include_alias** ne zaman bir dosya adı yanlış veya eksik.  
  
 Bağımsız değişkenleri **#pragma include_alias** deyimi tekliften kullanabilirsiniz (**"***filename***"**) veya açılı ayraç biçiminde ( **\<**  *filename***>**), ancak her ikisi de aynı form kullanmanız gerekir.  
  
## <a name="example"></a>Örnek  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```