---
title: Bağlayıcı Araçları Hatası LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: 69af2bd2c22fdb1188cf0b7119791e451e80f966
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686502"
---
# <a name="linker-tools-error-lnk1312"></a>Bağlayıcı Araçları Hatası LNK1312

dosya geçersiz veya bozuk: derleme içeri aktarılamıyor

Bir derleme oluştururken, **/ASSEMBLYMODULE** bağlayıcı seçeneğine bir modül veya **/clr** ile derlenen bütünleştirilmiş kod dışında bir dosya geçildi.  Bir nesne dosyasını **/ASSEMBLYMODULE**öğesine geçirmezseniz, nesneyi **/ASSEMBLYMODULE**yerine doğrudan bağlayıcıya geçirmeniz yeterlidir.

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
