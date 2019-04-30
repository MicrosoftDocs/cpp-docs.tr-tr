---
title: Derleyici Hatası C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: 6f4157db4a2a1b1864446a082deddc73df2e2fe9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406801"
---
# <a name="compiler-error-c3062"></a>Derleyici Hatası C3062

'enum': temeldeki tür 'type' olduğundan Numaralandırıcı değer gerektiriyor

Bir sabit listesi için bir temel türü belirtebilirsiniz. Ancak bazı türleri için her Numaralayıcı değerleri atamanızı gerektirir.

Numaralandırmalar hakkında daha fazla bilgi için bkz. [sabit listesi sınıfı](../../extensions/enum-class-cpp-component-extensions.md).

Aşağıdaki örnek, C3062 oluşturur:

```
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```