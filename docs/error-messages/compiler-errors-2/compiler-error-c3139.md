---
title: Derleyici hatası C3139
ms.date: 11/04/2016
f1_keywords:
- C3139
helpviewer_keywords:
- C3139
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
ms.openlocfilehash: 86f905653c6e1574a1d1c0a1225294b3a4dc5f3e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506183"
---
# <a name="compiler-error-c3139"></a>Derleyici hatası C3139

' struct ': üye olmadan bir UDT dışarı aktarılamıyor

[Export](../../windows/attributes/export.md) özniteliğini boş bir udt 'ye (Kullanıcı tanımlı tür) uygulamaya çalıştınız. Örnek:

```cpp
// C3139.cpp
#include "unknwn.h"
[emitidl];
[module(name=xx)];

[export] struct MyStruct {   // C3139 empty type
};
int main(){}
```
