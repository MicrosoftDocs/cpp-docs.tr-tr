---
title: Derleyici Hatası C2734 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2734
dev_langs:
- C++
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6fdc5dda82fe7410afc6e8580f3bedd8ddc289ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237365"
---
# <a name="compiler-error-c2734"></a>Derleyici Hatası C2734
'tanımlayıcısı': const nesnesi değil extern varsa başlatılmalı  
  
 Tanımlayıcı bildirilmiş `const` ancak başlatılmamış veya `extern`.  
  
 Aşağıdaki örnek C2734 oluşturur:  
  
```  
// C2734.cpp  
const int j;   // C2734  
extern const int i;   // OK, declared as extern  
```