---
title: Derleyici Uyarısı (düzey 1) C4230 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4230
dev_langs:
- C++
helpviewer_keywords:
- C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf1cf97d05a794da76bc5ebd21d2b0a54f1e9eac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278688"
---
# <a name="compiler-warning-level-1-c4230"></a>Derleyici Uyarısı (düzey 1) C4230
kullanılan anachronism: değiştiricileri/niteleyicileri interspersed; dikkate niteleyicisi  
  
 Bir Microsoft değiştirici önce bir niteleyici gibi kullanarak `__cdecl` eski bir uygulamadır.  
  
## <a name="example"></a>Örnek  
  
```  
// C4230.cpp  
// compile with: /W1 /LD  
int __cdecl const function1();   // C4230 const ignored  
```