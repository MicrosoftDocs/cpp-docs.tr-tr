---
title: Derleyici Hatası C2286 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2286
dev_langs:
- C++
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ddfb523252572fb985b660f1d4dbf5b1d790df1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2286"></a>Derleyici Hatası C2286
üye 'tanımlayıcısı' gösteriminin işaretçileri 'devralma için' - göz ardı bildirimi zaten ayarlanmış  
  
 İki farklı işaretçi üyeleri sunumu sınıfı için mevcut.  
  
 Daha fazla bilgi için bkz: [devralınan anahtar sözcükler](../../cpp/inheritance-keywords.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2286 oluşturur:  
  
```  
// C2286.cpp  
// compile with: /c  
class __single_inheritance X;  
class __multiple_inheritance X;   // C2286  
class  __multiple_inheritance Y;   // OK  
```