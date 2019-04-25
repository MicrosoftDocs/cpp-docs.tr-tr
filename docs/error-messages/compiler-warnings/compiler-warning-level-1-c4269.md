---
title: Derleyici Uyarısı (düzey 1) C4269
ms.date: 11/04/2016
f1_keywords:
- C4269
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
ms.openlocfilehash: 9a7f42b2dd65644d3f2abec58236a0b93cc6f635
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207239"
---
# <a name="compiler-warning-level-1-c4269"></a>Derleyici Uyarısı (düzey 1) C4269

'identifier': derleyicinin ürettiği varsayılan oluşturucuyla başlatılan 'const' otomatik verileri güvenilmez sonuçlar üretiyor

A **const** otomatik Önemsiz olmayan bir sınıf örneği, derleyicinin ürettiği varsayılan oluşturucuyla başlatılır.

## <a name="example"></a>Örnek

```
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

Yığında, başlangıç değeri oluşan bu sınıf örneği oluşturulan bu yana `m_data` herhangi bir şey olabilir. Ayrıca, beri olduğu bir **const** örneği, değerini `m_data` hiçbir zaman değiştirilebilir.