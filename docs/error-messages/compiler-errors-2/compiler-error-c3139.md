---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3139'
title: Derleyici hatası C3139
ms.date: 11/04/2016
f1_keywords:
- C3139
helpviewer_keywords:
- C3139
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
ms.openlocfilehash: c04e7b3da1325a473f90f26f99a1e187d9b8f71c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304239"
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
