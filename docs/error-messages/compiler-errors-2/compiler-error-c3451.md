---
title: Derleyici Hatası C3451 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3451
dev_langs:
- C++
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8685b75684827b4f202317e1df72a8248f1b41dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085205"
---
# <a name="compiler-error-c3451"></a>Derleyici Hatası C3451

'attribute': Yönetilmeyen öznitelik 'türü için ' uygulanamaz

Bir C++ özniteliği bir CLR türüne uygulanamıyor. Bkz: [C++ öznitelikleri başvurusu](../../windows/cpp-attributes-reference.md) daha fazla bilgi için.

Daha fazla bilgi için [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md).

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