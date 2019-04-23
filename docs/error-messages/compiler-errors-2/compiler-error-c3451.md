---
title: Derleyici Hatası C3451
ms.date: 11/04/2016
f1_keywords:
- C3451
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
ms.openlocfilehash: 5ef4352101541391a7cda88471fbaa6aeae4ffb4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776385"
---
# <a name="compiler-error-c3451"></a>Derleyici Hatası C3451

'attribute': Yönetilmeyen öznitelik 'türü için ' uygulanamaz

Bir C++ özniteliği bir CLR türüne uygulanamıyor. Bkz: [C++ öznitelikleri başvurusu](../../windows/attributes/attributes-alphabetical-reference.md) daha fazla bilgi için.

Daha fazla bilgi için [kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md).

Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulan: [UUID](../../windows/uuid-cpp-attributes.md) özniteliğine artık CLR programlama kullanarak kullanıcı tanımlı bir öznitelikte izin verilir. Bunun yerine <xref:System.Runtime.InteropServices.GuidAttribute> kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3451 oluşturur.

```
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