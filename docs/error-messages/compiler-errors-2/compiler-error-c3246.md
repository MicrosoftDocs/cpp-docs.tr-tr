---
title: Derleyici hatası C3246
ms.date: 11/04/2016
f1_keywords:
- C3246
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
ms.openlocfilehash: e9396b3bc5eea5d15366fc94ffa308d78754c31e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754400"
---
# <a name="compiler-error-c3246"></a>Derleyici hatası C3246

' class ': ' Sealed ' olarak bildirildiği için ' Type ' öğesinden devralma yapılamaz

[Sealed](../../extensions/sealed-cpp-component-extensions.md) olarak işaretlenen bir sınıf, diğer sınıfların temel sınıfı olamaz.

Aşağıdaki örnek C3246 oluşturur:

```cpp
// C3246_2.cpp
// compile with: /clr /LD
ref class X sealed {};

ref class Y : public X {}; // C3246
```
