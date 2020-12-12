---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3209'
title: Derleyici hatası C3209
ms.date: 11/04/2016
f1_keywords:
- C3209
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
ms.openlocfilehash: 81b2453a8e6318c082d6cd8838cc4a384ba80517
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173928"
---
# <a name="compiler-error-c3209"></a>Derleyici hatası C3209

' class ': genel sınıf bir yönetilen veya WinRTclass olmalıdır

Genel bir sınıf, yönetilen bir sınıf veya Windows Çalışma Zamanı sınıfı olmalıdır.

Aşağıdaki örnek C3209 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3209.cpp
// compile with: /clr
generic <class T>
class C {};   // C3209

// OK - ref class can be generic
generic <class T>
ref class D {};
```
