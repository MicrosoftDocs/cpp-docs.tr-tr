---
title: Derleyici Uyarısı (düzey 1) C4269 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4269
dev_langs:
- C++
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6dc986c98028530b8a5d4d25047305fd1a8effef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027289"
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