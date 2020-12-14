---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4580'
title: Derleyici Uyarısı (düzey 3) C4580
ms.date: 11/04/2016
f1_keywords:
- C4580
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
ms.openlocfilehash: 0bda682526081023c9208d548023f7c8b7316db9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294723"
---
# <a name="compiler-warning-level-3-c4580"></a>Derleyici Uyarısı (düzey 3) C4580

[Attribute] kullanım dışıdır; Bunun yerine, System:: Attribute veya platform:: Metadata öğesini temel sınıf olarak belirtin

[[Attribute](../../windows/attributes/attribute.md)] artık Kullanıcı tanımlı öznitelikler oluşturmak için tercih edilen sözdizimi değil. Daha fazla bilgi için bkz. [Kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md). CLR kodu için özniteliklerini türetirsiniz `System::Attribute` . Windows Çalışma Zamanı kod için, öğesinden öznitelikleri türetirsiniz `Platform::Metadata` .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3454 oluşturur ve nasıl düzeltileceğini gösterir.

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
