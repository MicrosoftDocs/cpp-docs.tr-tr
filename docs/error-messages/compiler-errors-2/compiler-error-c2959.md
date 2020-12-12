---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2959'
title: Derleyici hatası C2959
ms.date: 11/04/2016
f1_keywords:
- C2959
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
ms.openlocfilehash: aa5da1db36ce8544e95ad509402b066e664faf18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210432"
---
# <a name="compiler-error-c2959"></a>Derleyici hatası C2959

genel bir sınıf veya işlev bir şablonun üyesi olamaz

Daha fazla bilgi için bkz. [Windows çalışma zamanı ve yönetilen şablonlar](../../extensions/windows-runtime-and-managed-templates-cpp-component-extensions.md) ve [Genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2959 oluşturur.

```cpp
// C2959.cpp
// compile with: /clr /c
template <class T> ref struct S {
   generic <class U> ref struct GR1;   // C2959
};
```
