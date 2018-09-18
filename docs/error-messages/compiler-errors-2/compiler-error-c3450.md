---
title: Derleyici Hatası C3450 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3450
dev_langs:
- C++
helpviewer_keywords:
- C3450
ms.assetid: 78892cf7-0b82-4589-90d0-e06666247003
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee8e99dcf0055f6e37ad9f232c401000c76f3b13
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038392"
---
# <a name="compiler-error-c3450"></a>Derleyici Hatası C3450

'type': öznitelik değil; [System::AttributeUsageAttribute] belirtilemez. ya da [Windows::Foundation::Metadata::AttributeUsageAttribute]

Kullanıcı tanımlı yönetilen özniteliği devralmalıdır <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>. Bir Windows çalışma zamanı öznitelik tanımlanmalıdır `Windows::Foundation::Metadata` ad alanı.

Daha fazla bilgi için [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3450 oluşturur ve bu sorunun nasıl gösterir.

```
// C3450.cpp
// compile with: /clr
// C3450 expected
using namespace System;
using namespace System::Security;
using namespace System::Security::Permissions;

public ref class MyClass {};

class MyClass2 {};

[attribute(AttributeTargets::All)]
ref struct AtClass {
   AtClass(Type ^) {}
};

[attribute(AttributeTargets::All)]
ref struct AtClass2 {
   AtClass2() {}
};

// Apply the AtClass and AtClass2 attributes to class B
[AtClass(MyClass::typeid), AtClass2]
[AttributeUsage(AttributeTargets::All)]
// Delete the following line to resolve.
ref class B {};
// Uncomment the following line to resolve.
// ref class B : Attribute {};
```