---
title: Derleyici Uyarısı (düzey 1) C4420 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4420
dev_langs:
- C++
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98336a30e7174b62df48e93a04ba9ee7ddcc919a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4420"></a>Derleyici Uyarısı (düzey 1) C4420
'işleci': 'işleci' bunun yerine; kullanarak işleci mevcut değil çalışma zamanı denetimi güvenliği aşılmış olabilir  
  
 Kullandığınızda bu uyarı oluşturulur [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (yeni/silme denetimi vektör) ve vektör form bulunduğunda. Bu durumda, vektör olmayan form kullanılır.  
  
 Doğru çalışması /RTCv için sırayla derleyici her zaman vektör biçiminde çağırmalıdır [yeni](../../cpp/new-operator-cpp.md)/[silmek](../../cpp/delete-operator-cpp.md) vektör sözdizimi kullanıldığında.