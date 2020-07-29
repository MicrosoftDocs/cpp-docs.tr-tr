---
title: Derleyici Uyarısı (düzey 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: 1b63d1af49a53b7b15cdbae912d79a1b4f0cf787
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230720"
---
# <a name="compiler-warning-level-1-c4269"></a>Derleyici Uyarısı (düzey 1) C4269

' tanımlayıcı ': derleyicinin ürettiği varsayılan oluşturucuyla başlatılan ' const ' otomatik verileri güvenilmez sonuçlar oluşturuyor

**`const`** Basit olmayan bir sınıfın otomatik bir örneği, derleyici tarafından oluşturulan bir varsayılan Oluşturucu ile başlatılır.

## <a name="example"></a>Örnek

```cpp
// C4269.cpp
// compile with: /c /LD /W1
class X {
public:
   int m_data;
};

void g() {
   const X x1;   // C4269
};
```

Sınıfın bu örneği yığında oluşturulduğundan, ilk değeri `m_data` herhangi bir şey olabilir. Ayrıca, bir **`const`** örnek olduğundan, değeri `m_data` hiçbir şekilde değiştirilemez.
