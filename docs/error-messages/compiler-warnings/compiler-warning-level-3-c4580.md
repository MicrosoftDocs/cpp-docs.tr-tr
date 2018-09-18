---
title: Derleyici Uyarısı (Düzey 3) C4580 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9d25a77b6936a3b5b741a1da927c6beb24cbb1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072231"
---
# <a name="compiler-warning-level-3-c4580"></a>Derleyici Uyarısı (Düzey 3) C4580

[attribute] Kullanımdan kalktı; Bunun yerine bir temel sınıf olarak System::Attribute veya Platform::Metadata belirtin

[[özniteliği](../../windows/attribute.md)] artık kullanıcı tanımlı öznitelikler oluşturmak için tercih edilen sözdizimi aşağıdaki gibidir. Daha fazla bilgi için [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md). CLR kod için öznitelikleri türetilen `System::Attribute`. Windows çalışma zamanı kodunu öznitelikleri türetilen `Platform::Metadata`.

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