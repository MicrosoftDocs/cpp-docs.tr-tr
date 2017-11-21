---
title: "Derleyici Uyarısı (düzey 1) C4420 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4420
dev_langs: C++
helpviewer_keywords: C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 646e87243e6901827fb2d36076a95e6bcb63c3ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4420"></a>Derleyici Uyarısı (düzey 1) C4420
'işleci': 'işleci' bunun yerine; kullanarak işleci mevcut değil çalışma zamanı denetimi güvenliği aşılmış olabilir  
  
 Kullandığınızda bu uyarı oluşturulur [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (yeni/silme denetimi vektör) ve vektör form bulunduğunda. Bu durumda, vektör olmayan form kullanılır.  
  
 Doğru çalışması /RTCv için sırayla derleyici her zaman vektör biçiminde çağırmalıdır [yeni](../../cpp/new-operator-cpp.md)/[silmek](../../cpp/delete-operator-cpp.md) vektör sözdizimi kullanıldığında.