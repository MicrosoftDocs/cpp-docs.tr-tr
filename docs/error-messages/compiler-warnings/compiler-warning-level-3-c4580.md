---
title: Derleyici Uyarısı (Düzey 3) C4580
ms.date: 11/04/2016
f1_keywords:
- C4580
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
ms.openlocfilehash: e215dc98f62a90325e83068a640b0503a612c434
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50427813"
---
# <a name="compiler-warning-level-3-c4580"></a>Derleyici Uyarısı (Düzey 3) C4580

[attribute] Kullanımdan kalktı; Bunun yerine bir temel sınıf olarak System::Attribute veya Platform::Metadata belirtin

[[özniteliği](../../windows/attributes/attribute.md)] artık kullanıcı tanımlı öznitelikler oluşturmak için tercih edilen sözdizimi aşağıdaki gibidir. Daha fazla bilgi için [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md). CLR kod için öznitelikleri türetilen `System::Attribute`. Windows çalışma zamanı kodunu öznitelikleri türetilen `Platform::Metadata`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3454 oluşturur ve bu sorunun nasıl gösterir.

```cpp
// C4580.cpp
// compile with: /W3 /c /clr
[attribute]   // C4580
public ref class Attr {
public:
   int m_t;
};

public ref class Attr2 : System::Attribute {
public:
   int m_t;
};
```