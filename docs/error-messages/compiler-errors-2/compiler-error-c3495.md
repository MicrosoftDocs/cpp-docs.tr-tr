---
title: Derleyici Hatası C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 81fcbb8102d5df8059aad00772b7ee0cc07c01d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452474"
---
# <a name="compiler-error-c3495"></a>Derleyici Hatası C3495

'var': bir lambda yakalama otomatik depolama süresine sahip olmalıdır

İşaretlenmiş bir değişken gibi otomatik depolama süresine sahip olmayan bir değişkeni yakalayamazsınız `static` veya `extern`.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Başarılı değil bir `static` veya `extern` değişken lambda ifadesinin yakalama listesi.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3495 oluşturur çünkü `static` değişkeni `n` bir lambda ifadesinin yakalama listesinde görüntülenir:

```
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)

