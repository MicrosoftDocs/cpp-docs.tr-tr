---
title: Derleyici hatası C3209
ms.date: 11/04/2016
f1_keywords:
- C3209
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
ms.openlocfilehash: 79a5bc77f0e18a8e55954e25e67a836af8157596
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755141"
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
