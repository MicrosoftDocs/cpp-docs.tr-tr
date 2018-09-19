---
title: Bağlayıcı araçları hatası LNK1312 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1312
dev_langs:
- C++
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 335a3976675f36e3da295bc23c8e17440a56a505
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088661"
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