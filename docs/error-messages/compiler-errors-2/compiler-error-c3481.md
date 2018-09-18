---
title: Derleyici Hatası C3481 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3481
dev_langs:
- C++
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25634bb455a032ceff51d5e35f7a16e00e020326
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066901"
---
# <a name="compiler-error-c3481"></a>Derleyici Hatası C3481

'var': lambda yakalama değişkeni bulunamadı

Derleyici bir lambda ifadesinin yakalama listesine geçirilen bir değişkenin tanımı bulunamadı.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Değişkeni, lambda ifadesinin yakalama listeden kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3481 oluşturur çünkü değişken `n` tanımlı değil:

```
// C3481.cpp

int main()
{
   [n] {}(); // C3481
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)