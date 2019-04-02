---
title: Derleyici Hatası C3099
ms.date: 11/04/2016
f1_keywords:
- C3099
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
ms.openlocfilehash: 0f3eac1c232ef159d220a347d6b6dc3aed2fdd9a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771493"
---
# <a name="compiler-error-c3099"></a>Derleyici Hatası C3099

'anahtar sözcüğü': [System::AttributeUsageAttribute] yönetilen öznitelikleri için; kullanın. [Windows::Foundation::Metadata::AttributeUsageAttribute] WinRT öznitelikleri için kullanın.

Kullanım <xref:System.AttributeUsageAttribute> bildirmek için **/CLR** öznitelikleri. Kullanım `Windows::Foundation::Metadata::AttributeUsageAttribute` Windows çalışma zamanı öznitelik bildirmek için.

/ CLR öznitelikleri hakkında daha fazla bilgi için bkz. [kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md). Windows çalışma zamanı için desteklenen öznitelik [Windows.Foundation.Metadata ad alanı](/uwp/api/windows.foundation.metadata)

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