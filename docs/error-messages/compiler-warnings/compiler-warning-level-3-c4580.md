---
title: Derleyici Uyarısı (düzey 3) C4580
ms.date: 11/04/2016
f1_keywords:
- C4580
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
ms.openlocfilehash: 28d8534dad5fc1b234c180b879ad0645f05cfd65
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198620"
---
# <a name="compiler-warning-level-3-c4580"></a>Derleyici Uyarısı (düzey 3) C4580

[Attribute] kullanım dışıdır; Bunun yerine, System:: Attribute veya platform:: Metadata öğesini temel sınıf olarak belirtin

[[Attribute](../../windows/attributes/attribute.md)] artık Kullanıcı tanımlı öznitelikler oluşturmak için tercih edilen sözdizimi değil. Daha fazla bilgi için bkz. [Kullanıcı tanımlı öznitelikler](../../extensions/user-defined-attributes-cpp-component-extensions.md). CLR kodu için `System::Attribute`öznitelikleri türetirsiniz. Windows Çalışma Zamanı kod için `Platform::Metadata`öznitelikleri türetirsiniz.

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
