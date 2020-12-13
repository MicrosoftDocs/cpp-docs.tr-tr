---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3657'
title: Derleyici hatası C3657
ms.date: 11/04/2016
f1_keywords:
- C3657
helpviewer_keywords:
- C3657
ms.assetid: 89a28a18-4c17-43a1-bda6-deb52c32d203
ms.openlocfilehash: 6e5cf5dd0b3739acdd703e5ef11d3eb553fa9e90
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134426"
---
# <a name="compiler-error-c3657"></a>Derleyici hatası C3657

yok ediciler açıkça geçersiz kılınamaz veya açıkça geçersiz kılınamaz

Yok ediciler veya sonlandırıcılar açıkça geçersiz kılınamaz. Daha fazla bilgi için bkz. [Açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3657 oluşturur.

```cpp
// C3657.cpp
// compile with: /clr
public ref struct I {
   virtual ~I() { }
   virtual void a();
};

public ref struct D : I {
   virtual ~D() = I::~I {}   // C3657
   virtual void a() = I::a {}   // OK
};
```
