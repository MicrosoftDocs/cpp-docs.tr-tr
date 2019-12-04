---
title: Derleyici hatası C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: 2e0122dd53ba5318077dd33f22a07492c52db26b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756220"
---
# <a name="compiler-error-c3451"></a>Derleyici hatası C3451

' Attribute ': yönetilmeyen öznitelik ' Type ' öğesine uygulanamıyor

Bir C++ ÖZNITELIK bir clr türüne uygulanamaz. Daha fazla bilgi için bkz [ C++ . öznitelikler başvurusu](../../windows/attributes/attributes-alphabetical-reference.md) .

Daha fazla bilgi için bkz. [Kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md).

Bu hata, Visual Studio 2005 için yapılan derleyici uygunluk işinin bir sonucu olarak oluşturulabilir: CLR programlama kullanılarak Kullanıcı tanımlı bir öznitelikte [UUID](../../windows/uuid-cpp-attributes.md) özniteliğine artık izin verilmez. Bunun yerine <xref:System.Runtime.InteropServices.GuidAttribute> kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3451 oluşturur.

```cpp
// C3451.cpp
// compile with: /clr /c
using namespace System;
[ attribute(AttributeTargets::All) ]
public ref struct MyAttr {};

[ MyAttr, helpstring("test") ]   // C3451
// try the following line instead
// [ MyAttr ]
public ref struct ABC {};
```
