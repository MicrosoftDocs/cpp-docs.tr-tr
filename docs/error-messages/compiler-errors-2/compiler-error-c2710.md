---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2710'
title: Derleyici hatası C2710
ms.date: 11/04/2016
f1_keywords:
- C2710
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
ms.openlocfilehash: ea9e4eaefa023362647f418be16a72ee14fbd044
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320863"
---
# <a name="compiler-error-c2710"></a>Derleyici hatası C2710

' yapı ': ' __declspec (değiştirici) ' yalnızca bir işaretçi döndüren bir işleve uygulanabilir

Dönüş değeri işaretçi olan bir işlev, uygulanabilen tek yapıdır `modifier` .

Aşağıdaki örnek C2710 oluşturur:

```cpp
// C2710.cpp
__declspec(restrict) void f();   // C2710
// try the following line instead
__declspec(restrict) int * g();
```
