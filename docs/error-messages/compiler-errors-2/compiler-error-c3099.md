---
title: Derleyici Hatası C3099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3099
dev_langs:
- C++
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5f11e049965fb7374a2294e813502d1279f9f26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067421"
---
# <a name="compiler-error-c3099"></a>Derleyici Hatası C3099

'anahtar sözcüğü': [System::AttributeUsageAttribute] yönetilen öznitelikleri için; kullanın. [Windows::Foundation::Metadata::AttributeUsageAttribute] WinRT öznitelikleri için kullanın.

Kullanım <xref:System.AttributeUsageAttribute> bildirmek için **/CLR** öznitelikleri. Kullanım `Windows::Foundation::Metadata::AttributeUsageAttribute` Windows çalışma zamanı öznitelik bildirmek için.

/ CLR öznitelikleri hakkında daha fazla bilgi için bkz. [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md). Windows çalışma zamanı için desteklenen öznitelik [Windows.Foundation.Metadata ad alanı](https://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3099 oluşturur ve bu sorunun nasıl gösterir.

```
// C3099.cpp
// compile with: /clr /c
using namespace System;
[usage(10)]   // C3099
// try the following line instead
// [AttributeUsageAttribute(AttributeTargets::All)]
ref class A : Attribute {};
```