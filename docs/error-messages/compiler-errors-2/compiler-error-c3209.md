---
title: Derleyici Hatası C3209
ms.date: 11/04/2016
f1_keywords:
- C3209
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
ms.openlocfilehash: f907d0605cccf0a36abd1361d8c87a783bb81506
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243251"
---
# <a name="compiler-error-c3209"></a>Derleyici Hatası C3209

'class': Genel sınıf bir yönetilen veya WinRTclass olmalıdır

Genel bir sınıf, yönetilen bir sınıf veya bir Windows çalışma zamanı sınıf olmalıdır.

Aşağıdaki örnek, C3209 oluşturur ve bu sorunun nasıl gösterir:

```
// C3209.cpp
// compile with: /clr
generic <class T>
class C {};   // C3209

// OK - ref class can be generic
generic <class T>
ref class D {};
```