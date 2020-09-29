---
title: Derleyici hatası C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: d6a0d1234d8f25c6a55fffa7170f37aae27f5817
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501319"
---
# <a name="compiler-error-c3451"></a>Derleyici hatası C3451

' Attribute ': yönetilmeyen öznitelik ' Type ' öğesine uygulanamıyor

C++ özniteliği bir CLR türüne uygulanamaz. Daha fazla bilgi için bkz. [C++ öznitelikleri başvurusu](../../windows/attributes/attributes-alphabetical-reference.md) .

Daha fazla bilgi için bkz. [Kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md).

Bu hata, Visual Studio 2005 için yapılan derleyici uygunluk işinin bir sonucu olarak oluşturulabilir: CLR programlama kullanılarak Kullanıcı tanımlı bir öznitelikte [UUID](../../windows/attributes/uuid-cpp-attributes.md) özniteliğine artık izin verilmez. Bunun yerine <xref:System.Runtime.InteropServices.GuidAttribute> kullanın.

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
