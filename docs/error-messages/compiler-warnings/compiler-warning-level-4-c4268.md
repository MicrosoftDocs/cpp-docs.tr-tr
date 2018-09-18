---
title: Derleyici Uyarısı (düzey 4) C4268 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4268
dev_langs:
- C++
helpviewer_keywords:
- C4268
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f91a8152ef690b9ded63b91b2b6e6f1da6dc2524
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063716"
---
# <a name="compiler-warning-level-4-c4268"></a>Derleyici Uyarısı (düzey 4) C4268

'identifier': derleyicinin ürettiği varsayılan oluşturucuyla başlatılan 'const' statik/genel verileri nesneyi sıfırlarla dolduruyor

A **const** genel veya statik Önemsiz olmayan bir sınıfın örneğini bir derleyicinin ürettiği varsayılan oluşturucuyla başlatılan.

## <a name="example"></a>Örnek

```
// C4268.cpp
// compile with: /c /LD /W4
class X {
public:
   int m_data;
};

const X x1;   // C4268
```

Bu sınıf örneği olarak **const**, değerini `m_data` değiştirilemez.