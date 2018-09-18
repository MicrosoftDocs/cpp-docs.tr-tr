---
title: Derleyici Hatası C3536 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3536
dev_langs:
- C++
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7585a75ebe9733c228756e92d8e5ae57699aca27
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088585"
---
# <a name="compiler-error-c3536"></a>Derleyici Hatası C3536

'symbol': başlatılmadan önce kullanılamaz

Belirtilen sembol başlatılmadan önce kullanılamaz. Uygulamada, kendisini başlatmak için bir değişken kullanılamaz anlamına gelir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Değişkeninin kendisiyle başlatmayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, her bir değişken kendisi ile başlatılmış olduğundan C3536 verir.

```
// C3536.cpp
// Compile with /Zc:auto
int main()
{
   auto a = a;     //C3536
   auto b = &b;    //C3536
   auto c = c + 1; //C3536
   auto* d = &d;   //C3536
   auto& e = e;    //C3536
   return 0;
};
```

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)