---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3099'
title: Derleyici hatası C3099
ms.date: 11/04/2016
f1_keywords:
- C3099
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
ms.openlocfilehash: d065edd58df1e9196dc6aa31cfd4fb263f062f1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116229"
---
# <a name="compiler-error-c3099"></a>Derleyici hatası C3099

' anahtar sözcüğü ': yönetilen öznitelikler için [System:: AttributeUsageAttribute] kullanın; WinRT öznitelikleri için [Windows:: Foundation:: Metadata:: AttributeUsageAttribute] kullanın

<xref:System.AttributeUsageAttribute> **/Clr** özniteliklerini bildirmek için kullanın. `Windows::Foundation::Metadata::AttributeUsageAttribute`Windows çalışma zamanı özniteliklerini bildirmek için kullanın.

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
