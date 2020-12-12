---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3675'
title: Derleyici hatası C3675
ms.date: 11/04/2016
f1_keywords:
- C3675
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
ms.openlocfilehash: 0e8ea8d3450cd7a145e596f7122a5d2cbb31c5fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228748"
---
# <a name="compiler-error-c3675"></a>Derleyici hatası C3675

' Property ' tanımlandığından ' function ': ayrılmıştır

Basit bir özellik bildirdiğinizde, derleyici get ve set erişimcisi yöntemlerini oluşturur ve bu adlar programınızın kapsamında bulunur.  Derleyici tarafından oluşturulan adlar, ön bekleyen get_ tarafından oluşturulur ve özellik adına set_.  Bu nedenle, derleyici tarafından oluşturulan Erişimcilerde aynı ada sahip işlevleri bildiremezsiniz.

Daha fazla bilgi için bkz. [özelliği](../../extensions/property-cpp-component-extensions.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3675 oluşturur.

```cpp
// C3675.cpp
// compile with: /clr /c
ref struct C {
public:
   property int Size;
   int get_Size() { return 0; }   // C3675
};
```
