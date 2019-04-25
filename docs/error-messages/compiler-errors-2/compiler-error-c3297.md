---
title: Derleyici Hatası C3297
ms.date: 11/04/2016
f1_keywords:
- C3297
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
ms.openlocfilehash: e4661119680dff34dfaa43fb9ce71bf97150a8bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222498"
---
# <a name="compiler-error-c3297"></a>Derleyici Hatası C3297

'constraint_2': 'constraint_1' değer kısıtlaması olduğundan 'constraint_1' bir kısıtlama olarak kullanılamaz

Değer sınıfları korumalıdır. Kısıtlama değer sınıfı, başka bir kısıtlama hiçbir zaman buradan türetebilirsiniz.

Daha fazla bilgi için [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

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