---
title: Derleyici Hatası C3360
ms.date: 11/04/2016
f1_keywords:
- C3360
helpviewer_keywords:
- C3360
ms.assetid: 6acf983a-dbb6-422b-b045-a34bb4ba6761
ms.openlocfilehash: 1d08c53aad50d2cbc10c8c0e398fe3a18de3849d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606498"
---
# <a name="compiler-error-c3360"></a>Derleyici Hatası C3360

'string': ad oluşturulamıyor

İçin geçirilen değer [UUID](../../windows/uuid-cpp-attributes.md) özniteliği geçerli değildi.

Aşağıdaki örnek, C3360 oluşturur:

```
// C3360.cpp
[ uuid("1") ]
// try this line instead
// [ uuid("12341234-1234-1234-1234-123412341234") ]
struct A   // C3360
{
};

int main()
{
}
```