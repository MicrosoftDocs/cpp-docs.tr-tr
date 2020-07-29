---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: f0b5b17a6d64375f49a6d55021c72ba7119eb976
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213313"
---
# <a name="noreturn"></a>noreturn

**Microsoft'a Özgü**

Bu **`__declspec`** öznitelik, derleyiciye bir işlevin döndürmeyeceğini söyler. Sonuç olarak, derleyici bir işleve yapılan çağrıyı izleyen kodun ulaşılamaz olduğunu bilir **`__declspec(noreturn)`** .

Derleyici bir işlevi değer döndürmeyen bir denetim yolu ile bulursa, (C4715) uyarısı veya hata iletisi (C2202) oluşturur. Hiçbir süre döndürülmemiş bir işlev nedeniyle denetim yoluna ulaşılamadığından, **`__declspec(noreturn)`** Bu uyarıyı veya hatayı engellemek için kullanabilirsiniz.

> [!NOTE]
> **`__declspec(noreturn)`** Döndürülmesi beklenen bir işleve ekleme tanımsız davranışa neden olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, **`else`** yan tümce bir return deyimi içermez.  `fatal`Olarak bildirme **`__declspec(noreturn)`** bir hata veya uyarı iletisini önler.

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
[Anahtar sözcükler](../cpp/keywords-cpp.md)
