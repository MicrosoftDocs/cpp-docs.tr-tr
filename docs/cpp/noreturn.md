---
title: noreturn | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noreturn_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6133fc70c5c2b8bb8f794746c1d5ca11be97b817
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031047"
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