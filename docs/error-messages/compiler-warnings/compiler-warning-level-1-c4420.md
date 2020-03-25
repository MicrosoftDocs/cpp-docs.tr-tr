---
title: Derleyici Uyarısı (düzey 1) C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: 72ab87b34e07717112f5af1727a216b4f786ae0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186796"
---
# <a name="compiler-warning-level-1-c4420"></a>Derleyici Uyarısı (düzey 1) C4420

' operator ': işleç kullanılamıyor, yerine ' operator ' kullanılıyor; çalışma zamanı denetimi tehlikede olabilir

Bu uyarı, [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (vektör yeni/silme denetimi) kullandığınızda ve hiçbir vektör formu bulunamadığında oluşturulur. Bu durumda, vektör olmayan form kullanılır.

/RTCv 'nin düzgün çalışması için, vektör sözdizimi kullanılmışsa derleyicinin her zaman [yeni](../../cpp/new-operator-cpp.md)/[Sil](../../cpp/delete-operator-cpp.md) vektör formunu çağırması gerekir.
