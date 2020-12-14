---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3393'
title: Derleyici hatası C3393
ms.date: 11/04/2016
f1_keywords:
- C3393
helpviewer_keywords:
- C3393
ms.assetid: d57f7c69-0a02-4fe3-9e45-bc62644fd77c
ms.openlocfilehash: d870498fe235fa1336ea784b7da1dcdd12f8c7cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316329"
---
# <a name="compiler-error-c3393"></a>Derleyici hatası C3393

kısıtlama yan tümcesinde sözdizimi hatası: ' Identifier ' bir tür değil

Bir tür olması gereken bir kısıtlamaya geçirilen tanımlayıcı bir tür değil.  Daha fazla bilgi için bkz. [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3393 oluşturur:

```cpp
// C3393.cpp
// compile with: /clr /c
void MyInterface() {}
interface class MyInterface2 {};

generic<typename T>
where T : MyInterface   // C3393
// try the following line instead
// where T : MyInterface2
ref class R {};
```
