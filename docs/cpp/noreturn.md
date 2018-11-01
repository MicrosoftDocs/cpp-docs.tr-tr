---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: 1d78e8f5116eabf9073205b938156197bf1001a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611867"
---
# <a name="noreturn"></a>noreturn

## <a name="microsoft-specific"></a>Microsoft'a Özgü

Bu **__declspec** öznitelik derleyiciye bir işlev değil döndürür. Sonuç olarak derleyici olduğunu bilir çağrıyı izleyen kodu bir **__declspec(noreturn)** işlevi erişilemez.

Derleyici bir işlevi değer döndürmeyen bir denetim yolu ile bulursa, (C4715) uyarısı veya hata iletisi (C2202) oluşturur. Hiçbir zaman döndüren bir işlev nedeniyle denetim yoluna ulaşılamıyorsa kullanabileceğiniz **__declspec(noreturn)** bu uyarı veya hatayı önlemek için.

> [!NOTE]
>  Ekleme **__declspec(noreturn)** dönmesi beklenen bir işleve tanımsız davranışlara neden olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, **başka** yan tümcesi bir dönüş deyimi içermez.  Bildirme `fatal` olarak **__declspec(noreturn)** bir hata veya uyarı iletisi önler.

```cpp
// noreturn2.cpp
__declspec(noreturn) extern void fatal () {}

int main() {
   if(1)
     return 1;
   else if(0)
     return 0;
   else
     fatal();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)