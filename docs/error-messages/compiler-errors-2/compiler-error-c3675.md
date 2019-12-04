---
title: Derleyici hatası C3675
ms.date: 11/04/2016
f1_keywords:
- C3675
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
ms.openlocfilehash: 6772572d29765370d6cdbf52ed8470ff2f3f054e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758079"
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
