---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3062'
title: Derleyici hatası C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: b57d03f3ef09e1d01741866d99dfff87aa5aa28d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281749"
---
# <a name="compiler-error-c3062"></a>Derleyici hatası C3062

' Enum ': temeldeki tür ' Type ' olduğundan Numaralandırıcı değer gerektiriyor

Bir numaralandırma için temel alınan bir tür belirtebilirsiniz. Ancak, bazı türler her bir Numaralandırıcı için değerler atamanız gerekir.

Numaralandırmalar hakkında daha fazla bilgi için bkz. [enum class](../../extensions/enum-class-cpp-component-extensions.md).

Aşağıdaki örnek C3062 oluşturur:

```cpp
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```
