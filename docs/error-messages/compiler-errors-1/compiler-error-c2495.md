---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2495'
title: Derleyici hatası C2495
ms.date: 11/04/2016
f1_keywords:
- C2495
helpviewer_keywords:
- C2495
ms.assetid: bb7066fe-3549-4901-97e4-157f3c04dd57
ms.openlocfilehash: 03f7102cff8b41415c1d845595bb443717cffd43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283646"
---
# <a name="compiler-error-c2495"></a>Derleyici hatası C2495

' tanımlayıcı ': ' nothrow ' yalnızca işlev bildirimlerine veya tanımlarına uygulanabilir

[Nothrow](../../cpp/nothrow-cpp.md) genişletilmiş özniteliği yalnızca işlev bildirimlerine veya tanımlarına uygulanabilir.

Aşağıdaki örnek C2495 oluşturur:

```cpp
// C2495.cpp
// compile with: /c
__declspec(nothrow) class X {   // C2495
   int m_data;
} x;

__declspec(nothrow) void test();   // OK
```
