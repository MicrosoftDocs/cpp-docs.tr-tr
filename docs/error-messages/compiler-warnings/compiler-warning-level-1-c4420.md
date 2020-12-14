---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4420'
title: Derleyici Uyarısı (düzey 1) C4420
ms.date: 11/04/2016
f1_keywords:
- C4420
helpviewer_keywords:
- C4420
ms.assetid: 44a37754-7ddd-4764-a5f7-d33e05c20091
ms.openlocfilehash: 2a92d7296bf5c38655182e5c0dd2c200d0ccf42d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311077"
---
# <a name="compiler-warning-level-1-c4420"></a>Derleyici Uyarısı (düzey 1) C4420

' operator ': işleç kullanılamıyor, yerine ' operator ' kullanılıyor; çalışma zamanı denetimi tehlikede olabilir

Bu uyarı, [/RTCv](../../build/reference/rtc-run-time-error-checks.md) (vektör yeni/silme denetimi) kullandığınızda ve hiçbir vektör formu bulunamadığında oluşturulur. Bu durumda, vektör olmayan form kullanılır.

/RTCv 'nin düzgün çalışması için, vektör sözdizimi kullanılmışsa derleyicinin her zaman [Yeni](../../cpp/new-operator-cpp.md)silme vektör formunu çağırması gerekir / [](../../cpp/delete-operator-cpp.md) .
