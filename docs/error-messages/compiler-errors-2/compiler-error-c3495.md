---
title: Derleyici Hatası C3495 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3495
dev_langs:
- C++
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dda1e2f2699969ad0bc446d9f79a0004e043998d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067395"
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


