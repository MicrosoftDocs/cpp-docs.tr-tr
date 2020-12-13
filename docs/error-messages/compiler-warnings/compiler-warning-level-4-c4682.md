---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4682'
title: Derleyici Uyarısı (düzey 4) C4682
ms.date: 11/04/2016
f1_keywords:
- C4682
helpviewer_keywords:
- C4682
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
ms.openlocfilehash: c91b1b7f1ac378faa7032bbc9e8c508124773c6c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133853"
---
# <a name="compiler-warning-level-4-c4682"></a>Derleyici Uyarısı (düzey 4) C4682

' Parameter ': açıklamalı parametre özniteliği belirtilmedi, [in] varsayılan olarak ayarlanıyor

Öznitelikli bir arabirimdeki parametre üzerindeki bir yöntem, yönlü özniteliklerden birine sahip değil: [ın](../../windows/attributes/in-cpp.md) veya [Out](../../windows/attributes/out-cpp.md). Parametresi ' de varsayılan olarak olur.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4682 oluşturur:

```cpp
// C4682.cpp
// compile with: /W4
#pragma warning(default : 4682)
#include <windows.h>
[module(name="MyModule")];

[ library_block, object, uuid("c54ad59d-d516-41dd-9acd-afda17565c2b") ]
__interface IMyIface : IUnknown
{
   HRESULT f1(int i, int *pi); // C4682
   // try the following line
   // HRESULT f1([in] int i, [in] int *pi);
};

int main()
{
}
```
