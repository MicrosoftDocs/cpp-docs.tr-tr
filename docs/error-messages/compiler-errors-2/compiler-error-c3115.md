---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3115'
title: Derleyici hatası C3115
ms.date: 11/04/2016
f1_keywords:
- C3115
helpviewer_keywords:
- C3115
ms.assetid: 51726145-9782-4ec9-84b9-286f366d9cbd
ms.openlocfilehash: 4ac27ba71307d73526d82f72092150e0ca5559ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115969"
---
# <a name="compiler-error-c3115"></a>Derleyici hatası C3115

' Attribute ': Bu özniteliğe ' yapı ' üzerinde izin verilmiyor

Kendisine amaçlanan bir yapı için bir öznitelik uygulandı.  Daha fazla bilgi için bkz. [kullanıma göre öznitelikler](../../windows/attributes/attributes-by-usage.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3115 oluşturur.

```cpp
// C3115.cpp
// compile with: /c
#include <unknwn.h>
[module(name="xx")];

[object, helpstringdll(xx.dll), uuid("00000000-0000-0000-0000-000000000001")]   // C3115
// try the following line instead
// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI {
   HRESULT xx();
};
```
