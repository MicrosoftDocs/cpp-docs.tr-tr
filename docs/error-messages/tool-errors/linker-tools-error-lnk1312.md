---
title: Bağlayıcı Araçları Hatası LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: 49fa7e7963d6bb561e1602b58fe1f26c5f3d54bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160477"
---
# <a name="linker-tools-error-lnk1312"></a>Bağlayıcı Araçları Hatası LNK1312

dosya geçersiz veya bozuk: derleme içeri aktarılamıyor

Oluşturma sırasında bir derleme, modül veya ile derlenmiş derlemenin dışında bir dosya **/CLR** geçildi **assemblymodule** bağlayıcı seçeneği.  Bir nesne dosyası için geçirilmiş **assemblymodule**, nesne bağlayıcı doğrudan yerine için geçirmeniz yeterlidir **assemblymodule**.

## <a name="example"></a>Örnek

Aşağıdaki örnek, .obj dosyası oluşturulur.

```
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, LNK1312 oluşturur.

```
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```