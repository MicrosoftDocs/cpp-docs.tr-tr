---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: f37ce13e27f9b141eab928b88102813a5b6d65f8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177891"
---
# <a name="noreturn"></a>noreturn

**Microsoft 'a özgü**

Bu **__declspec** özniteliği derleyiciye bir işlevin döndürmeyeceğini söyler. Sonuç olarak, derleyici bir **__declspec (noreturn)** işlevine yapılan çağrıyı izleyen kodun ulaşılamaz olduğunu bilir.

Derleyici bir işlevi değer döndürmeyen bir denetim yolu ile bulursa, (C4715) uyarısı veya hata iletisi (C2202) oluşturur. Hiçbir yerde döndürmeyen bir işlev nedeniyle denetim yoluna ulaşılamadığından, bu uyarıyı veya hatayı engellemek için **__declspec (noreturn)** kullanabilirsiniz.

> [!NOTE]
>  Döndürülmesi beklenen bir işleve **__declspec (noreturn)** eklemek, tanımsız davranışa neden olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, **Else** yan tümcesi return deyimi içermez.  `fatal` **__declspec (noreturn)** olarak bildirmek bir hata veya uyarı iletisini önler.

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
