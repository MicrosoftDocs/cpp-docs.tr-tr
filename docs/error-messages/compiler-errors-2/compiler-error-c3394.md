---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3394'
title: Derleyici hatası C3394
ms.date: 11/04/2016
f1_keywords:
- C3394
helpviewer_keywords:
- C3394
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
ms.openlocfilehash: ea805ef8ff9bf6e19498135ae6fcd9ba7e3ff9e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313365"
---
# <a name="compiler-error-c3394"></a>Derleyici hatası C3394

kısıtlama yan tümcesinde sözdizimi hatası: bulunan ' Identifier ' bir tür bekliyordu

Kısıtlama hatalı oluşturulmuş.  Daha fazla bilgi için bkz. [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3394 oluşturur:

```cpp
// C3394.cpp
// compile with: /clr /c
ref class MyClass {};
ref class R {
   generic<typename T>
   where T : static   // C3394
   // try the following line instead
   // where T : MyClass
   void f() {}
};
```
