---
title: Derleyici Uyarısı (Düzey 3) C4580
ms.date: 11/04/2016
f1_keywords:
- C4580
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
ms.openlocfilehash: bd2ecff5adc6538f75c61772b785acbfc89092ae
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781776"
---
# <a name="compiler-warning-level-3-c4580"></a>Derleyici Uyarısı (Düzey 3) C4580

[attribute] Kullanımdan kalktı; Bunun yerine bir temel sınıf olarak System::Attribute veya Platform::Metadata belirtin

[[özniteliği](../../windows/attributes/attribute.md)] artık kullanıcı tanımlı öznitelikler oluşturmak için tercih edilen sözdizimi aşağıdaki gibidir. Daha fazla bilgi için [kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md). CLR kod için öznitelikleri türetilen `System::Attribute`. Windows çalışma zamanı kodunu öznitelikleri türetilen `Platform::Metadata`.

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