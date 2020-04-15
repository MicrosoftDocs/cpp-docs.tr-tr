---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: a30840aa0556a7324ba24c0f2aaec57dea88d082
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367863"
---
# <a name="noreturn"></a>noreturn

**Microsoft'a Özgü**

Bu **__declspec** özniteliği derleyiciye bir işlevin geri dönmediğini söyler. Sonuç olarak, **derleyici, __declspec (geri dönüş)** işlevine yapılan çağrıyı izleyen kodun erişilemez olduğunu bilir.

Derleyici bir işlevi değer döndürmeyen bir denetim yolu ile bulursa, (C4715) uyarısı veya hata iletisi (C2202) oluşturur. Denetim yoluna hiç dönmeyen bir işlev nedeniyle ulaşılamıyorsa, bu uyarı veya hatayı önlemek için **__declspec(geri dönüş)** kullanabilirsiniz.

> [!NOTE]
> Dönmesi beklenen bir işleve **__declspec(geri dönüş)** eklemek tanımlanmamış davranışlara neden olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, **diğer** yan tümce bir iade deyimi içermez.  `fatal` **__declspec(noreturn)** olarak bildirmek bir hata veya uyarı iletisi önler.

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

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
