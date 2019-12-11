---
title: Bağlayıcı Araçları Hatası LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: e462d24f2eb54718ba73617146aab96bb14a66df
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990912"
---
# <a name="linker-tools-error-lnk1312"></a>Bağlayıcı Araçları Hatası LNK1312

dosya geçersiz veya bozuk: derleme içeri aktarılamıyor

Bir derleme oluştururken, **/ASSEMBLYMODULE** bağlayıcı seçeneğine bir modül veya **/clr** ile derlenen bütünleştirilmiş kod dışında bir dosya geçildi.  Bir nesne dosyasını **/ASSEMBLYMODULE**öğesine geçirmezseniz, nesneyi **/ASSEMBLYMODULE**yerine doğrudan bağlayıcıya geçirmeniz yeterlidir.

## <a name="example"></a>Örnek

Aşağıdaki örnek. obj dosyasını oluşturdu.

```cpp
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK1312 oluşturur.

```cpp
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```
