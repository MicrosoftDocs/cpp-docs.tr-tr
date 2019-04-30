---
title: Derleyici Uyarısı (düzey 1) C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: a4a7e91e7845cc0fc25d5a6fad16ae7b7e327952
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408179"
---
# <a name="compiler-warning-level-1-c4420"></a>Derleyici Uyarısı (düzey 1) C4420

'operator': işleç kullanılamıyor, bunun yerine; 'operator' kullanma çalışma zamanı denetimi zarar görmüş

Kullandığınızda, bu uyarı oluşturulur [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (yeni/delete denetimi vektör) ve vektör form bulunduğunda. Bu durumda, vektör olmayan biçimi kullanılır.

Exchange'in /RTCv düzgün çalışması, derleyici her zaman vektör biçiminde çağırmalıdır [yeni](../../cpp/new-operator-cpp.md)/[Sil](../../cpp/delete-operator-cpp.md) vektör söz dizimi kullanılıyorsa.