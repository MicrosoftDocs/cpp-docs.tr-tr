---
title: Derleyici Hatası C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 3e387fe77c521a4f25ba67205f1fbd552397e272
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035828"
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

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)

