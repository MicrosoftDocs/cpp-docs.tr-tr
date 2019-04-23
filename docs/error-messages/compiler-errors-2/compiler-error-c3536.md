---
title: Derleyici Hatası C3536
ms.date: 11/04/2016
f1_keywords:
- C3536
helpviewer_keywords:
- C3536
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
ms.openlocfilehash: a16c5bd46d806d09861d5734b637c2c9d9b2f9d0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031911"
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

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)