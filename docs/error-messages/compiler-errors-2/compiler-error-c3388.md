---
title: Derleyici Hatası C3388
ms.date: 11/04/2016
f1_keywords:
- C3388
helpviewer_keywords:
- C3388
ms.assetid: 34336545-ed13-4d81-ab5f-f869799fe4c2
ms.openlocfilehash: 3b56aae115b1a1721f3f8a8688e36b25edc7f33f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776736"
---
# <a name="compiler-error-c3388"></a>Derleyici Hatası C3388

'type': 'ref class' varsayılıyor bir kısıtlama olarak kullanılamaz ayrıştırmaya devam etmek için

Genel türde bir kısıtlama belirtildi, ancak kısıtlaması düzgün belirtilmedi. Bkz: [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) daha fazla bilgi için.

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