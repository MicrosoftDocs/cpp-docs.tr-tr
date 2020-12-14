---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3734'
title: Derleyici hatası C3734
ms.date: 11/04/2016
f1_keywords:
- C3734
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
ms.openlocfilehash: f24c81c06a0e140f7970e8a6fc96d90aae3780f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245011"
---
# <a name="compiler-error-c3734"></a>Derleyici hatası C3734

' class ': yönetilen veya WinRT sınıfı coclass olamaz

[Coclass](../../windows/attributes/coclass.md) özniteliği yönetilen veya WinRT sınıflarıyla birlikte kullanılamaz.

Aşağıdaki örnek C3734 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3734.cpp
// compile with: /clr /c
[module(name="x")];

[coclass]
ref class CMyClass {   // C3734 remove the ref keyword to resolve
};
```
