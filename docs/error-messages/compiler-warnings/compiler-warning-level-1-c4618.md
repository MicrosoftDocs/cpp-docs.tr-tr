---
title: Derleyici Uyarısı (düzey 1) C4618 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4618
dev_langs:
- C++
helpviewer_keywords:
- C4618
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e53f8542983a6e15f353ff181efa280815fea9d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4618"></a>Derleyici Uyarısı (düzey 1) C4618
pragma parametreler boş bir dize dahil; göz ardı pragması  
  
 Boş bir dize bağımsız değişken olarak verilen bir **#pragma**.  
  
 Pragma bağımsız değişken olmadan işlendi.  
  
 Aşağıdaki örnek C4618 oluşturur:  
  
```  
// C4618.cpp  
// compile with: /W1 /LD  
#pragma code_seg("")   // C4618  
```