---
title: Derleyici Hatası C3297
ms.date: 11/04/2016
f1_keywords:
- C3297
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
ms.openlocfilehash: 6df8fd3df023602f65c872dedd74da36bbbc6bd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649923"
---
# <a name="compiler-error-c3297"></a>Derleyici Hatası C3297

'constraint_2': 'constraint_1' değer kısıtlaması olduğundan 'constraint_1' bir kısıtlama olarak kullanılamaz

Değer sınıfları korumalıdır. Kısıtlama değer sınıfı, başka bir kısıtlama hiçbir zaman buradan türetebilirsiniz.

Daha fazla bilgi için [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3297 oluşturur.

```
// C3297.cpp
// compile with: /clr /c
generic<class T, class U>
where T : value class
where U : T   // C3297
public ref struct R {};
```