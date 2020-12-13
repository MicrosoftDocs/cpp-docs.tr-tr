---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3296'
title: Derleyici hatası C3296
ms.date: 11/04/2016
f1_keywords:
- C3296
helpviewer_keywords:
- C3296
ms.assetid: fc4c9dcd-16cf-4eee-a1ac-c43e7c29e443
ms.openlocfilehash: 18c4cd35cda096cbb9e335e30da8d0631d247f60
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144618"
---
# <a name="compiler-error-c3296"></a>Derleyici hatası C3296

' Property ': Bu ada sahip bir özellik zaten var

Derleyici aynı ada sahip birden fazla özellik ile karşılaştı. Bir tür içindeki her bir özelliğin benzersiz bir adı olmalıdır.

Daha fazla bilgi için bkz. [özellik](../../extensions/property-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3296 oluşturur.

```cpp
// C3296.cpp
// compile with: /clr /c
using namespace System;

ref class R {
public:
   property int MyProp[int] { int get(int); }

   property String^ MyProp[int] { void set(int, String^); }   // C3296
};
```
