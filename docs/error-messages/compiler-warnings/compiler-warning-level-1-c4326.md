---
title: Derleyici Uyarısı (düzey 1) C4326
ms.date: 08/27/2018
f1_keywords:
- C4326
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
ms.openlocfilehash: d14a1902db4dcf2224ce6a58db120a81ebb5620f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601168"
---
# <a name="compiler-warning-level-1-c4326"></a>Derleyici Uyarısı (düzey 1) C4326

> dönüş türü '*işlevi*'olmalıdır'*type1*'veya'*type2*'

## <a name="remarks"></a>Açıklamalar

Bir işlev dışında bir tür döndürdü *type1*. Örneğin, kullanarak [/Za](../../build/reference/za-ze-disable-language-extensions.md), **ana** değil döndürmedi bir **int**.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4326 oluşturur ve bu sorunun nasıl gösterir:

```cpp
// C4326.cpp
// compile with: /Za /W1
char main()
{
    // C4326, instead use int main()
}
```