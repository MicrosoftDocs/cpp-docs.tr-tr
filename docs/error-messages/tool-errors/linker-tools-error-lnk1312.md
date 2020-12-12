---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1312'
title: Bağlayıcı Araçları Hatası LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: d861b6976f9b065e3a693e916164879a3311d3db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193636"
---
# <a name="linker-tools-error-lnk1312"></a>Bağlayıcı Araçları Hatası LNK1312

dosya geçersiz veya bozuk: derleme içeri aktarılamıyor

Bir derleme oluştururken, **/ASSEMBLYMODULE** bağlayıcı seçeneğine bir modül veya **/clr** ile derlenen bütünleştirilmiş kod dışında bir dosya geçildi.  Bir nesne dosyasını **/ASSEMBLYMODULE** öğesine geçirmezseniz, nesneyi **/ASSEMBLYMODULE** yerine doğrudan bağlayıcıya geçirmeniz yeterlidir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek. obj dosyasını oluşturdu.

```cpp
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

Aşağıdaki örnek LNK1312 oluşturur.

```cpp
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```
