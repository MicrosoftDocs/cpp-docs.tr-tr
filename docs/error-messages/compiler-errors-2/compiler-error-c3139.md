---
title: Derleyici hatası C3139
ms.date: 11/04/2016
f1_keywords:
- C3139
helpviewer_keywords:
- C3139
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
ms.openlocfilehash: 274f3cdb3425a8a0e1e282ca6e9ca79f70077233
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761266"
---
# <a name="compiler-error-c3139"></a>Derleyici hatası C3139

' struct ': üye olmadan bir UDT dışarı aktarılamıyor

[Export](../../windows/export.md) özniteliğini boş bir udt 'ye (Kullanıcı tanımlı tür) uygulamaya çalıştınız. Örneğin:

```cpp
// C3139.cpp
#include "unknwn.h"
[emitidl];
[module(name=xx)];

[export] struct MyStruct {   // C3139 empty type
};
int main(){}
```
