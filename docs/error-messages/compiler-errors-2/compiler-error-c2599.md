---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2599'
title: Derleyici hatası C2599
ms.date: 11/04/2016
f1_keywords:
- C2599
helpviewer_keywords:
- C2599
ms.assetid: 88515f36-7589-47e2-862e-0de8b18d6668
ms.openlocfilehash: e1365ee2570d4af524f7e4dbd36a411916efb9c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312052"
---
# <a name="compiler-error-c2599"></a>Derleyici hatası C2599

' Enum ': sabit listesi türünün ileri bildirimine izin verilmiyor

Derleyici artık yönetilen bir numaralandırmanın ileri bildirimini desteklemiyor.

Bir sabit listesi türünün ileri bildirimine [/za](../../build/reference/za-ze-disable-language-extensions.md)altında izin verilmez.

Aşağıdaki örnek C2599 oluşturur:

```cpp
// C2599.cpp
// compile with: /clr /c
enum class Status;   // C2599

enum class Status2 { stop2, hold2, go2};

ref struct MyStruct {
   // Delete the following line to resolve.
   Status m_status;

   Status2 m_status2;   // OK
};

enum class Status { stop, hold, go };
```
