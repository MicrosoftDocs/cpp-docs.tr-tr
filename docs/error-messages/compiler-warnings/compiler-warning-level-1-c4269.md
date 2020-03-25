---
title: Derleyici Uyarısı (düzey 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: e2e1781bf4c1b9ac0ee29d0b5900daa6cfe94b45
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199777"
---
# <a name="compiler-warning-level-1-c4269"></a>Derleyici Uyarısı (düzey 1) C4269

' tanımlayıcı ': derleyicinin ürettiği varsayılan oluşturucuyla başlatılan ' const ' otomatik verileri güvenilmez sonuçlar oluşturuyor

Basit olmayan bir sınıfın **const** otomatik örneği, derleyici tarafından oluşturulan bir varsayılan Oluşturucu ile başlatılır.

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

Sınıfın bu örneği yığında oluşturulduğundan, `m_data` ilk değeri herhangi bir şey olabilir. Ayrıca, bir **const** örneği olduğundan `m_data` değeri hiçbir şekilde değiştirilemez.
