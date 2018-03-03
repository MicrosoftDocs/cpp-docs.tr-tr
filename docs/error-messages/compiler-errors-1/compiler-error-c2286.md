---
title: "Derleyici Hatası C2286 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2286
dev_langs:
- C++
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3773c8ed60f4787c96f1695dddf2dc23aacf10e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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