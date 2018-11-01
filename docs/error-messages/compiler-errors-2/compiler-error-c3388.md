---
title: Derleyici Hatası C3388
ms.date: 11/04/2016
f1_keywords:
- C3388
helpviewer_keywords:
- C3388
ms.assetid: 34336545-ed13-4d81-ab5f-f869799fe4c2
ms.openlocfilehash: 1f6e51542cc852543d648f9f94a964ae0cab3b30
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512702"
---
# <a name="compiler-error-c3388"></a>Derleyici Hatası C3388

'type': 'ref class' varsayılıyor bir kısıtlama olarak kullanılamaz ayrıştırmaya devam etmek için

Genel türde bir kısıtlama belirtildi, ancak kısıtlaması düzgün belirtilmedi. Bkz: [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3388 oluşturur.

```
// C3388.cpp
// compile with: /clr /c
interface class AA {};

generic <class T>
where T : interface class   // C3388
ref class C {};

// OK
generic <class T>
where T : AA
ref class D {};
```