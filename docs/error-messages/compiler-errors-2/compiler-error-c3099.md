---
title: Derleyici hatası C3099
ms.date: 11/04/2016
f1_keywords:
- C3099
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
ms.openlocfilehash: 81f508c47c678d86f8f95303861b42f8a70daa57
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750058"
---
# <a name="compiler-error-c3099"></a>Derleyici hatası C3099

' anahtar sözcüğü ': yönetilen öznitelikler için [System:: AttributeUsageAttribute] kullanın; WinRT öznitelikleri için [Windows:: Foundation:: Metadata:: AttributeUsageAttribute] kullanın

**/Clr** özniteliklerini bildirmek için <xref:System.AttributeUsageAttribute> kullanın. Windows Çalışma Zamanı özniteliklerini bildirmek için `Windows::Foundation::Metadata::AttributeUsageAttribute` kullanın.

/CLR öznitelikleri hakkında daha fazla bilgi için bkz. [Kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md). Windows Çalışma Zamanı desteklenen öznitelikler için bkz. [Windows. Foundation. Metadata ad alanı](/uwp/api/windows.foundation.metadata)

## <a name="example"></a>Örnek

Aşağıdaki örnek C3099 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// C3099.cpp
// compile with: /clr /c
using namespace System;
[usage(10)]   // C3099
// try the following line instead
// [AttributeUsageAttribute(AttributeTargets::All)]
ref class A : Attribute {};
```
