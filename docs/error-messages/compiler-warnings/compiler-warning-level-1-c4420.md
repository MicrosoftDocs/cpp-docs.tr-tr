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
ms.openlocfilehash: e1ba4ef4c4fc006e1a5950d0d16dc530ccc06a1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049754"
---
# <a name="compiler-warning-level-1-c4420"></a>Derleyici Uyarısı (düzey 1) C4420

'operator': işleç kullanılamıyor, bunun yerine; 'operator' kullanma çalışma zamanı denetimi zarar görmüş

Kullandığınızda, bu uyarı oluşturulur [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (yeni/delete denetimi vektör) ve vektör form bulunduğunda. Bu durumda, vektör olmayan biçimi kullanılır.

Exchange'in /RTCv düzgün çalışması, derleyici her zaman vektör biçiminde çağırmalıdır [yeni](../../cpp/new-operator-cpp.md)/[Sil](../../cpp/delete-operator-cpp.md) vektör söz dizimi kullanılıyorsa.