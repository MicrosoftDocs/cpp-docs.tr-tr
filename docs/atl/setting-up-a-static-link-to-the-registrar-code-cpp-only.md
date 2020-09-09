---
title: Kayıt Şirketi koduna statik bağlantı ayarlama (yalnızca C++)
description: C++ kodunu ATL kaydedici koduna statik olarak bağlama.
ms.date: 09/03/2020
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
ms.openlocfilehash: f08f7d9433ae1344c7a98a5c52502d03bad21e91
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609160"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Kaydedici koduna statik bağlantı ayarlama (yalnızca C++)

C++ istemcileri, Kaydediconun koduna statik bir bağlantı oluşturabilir. Kaydedicisinin ayrıştırıcının statik bağlanması, yayın derlemesine yaklaşık 5 k ekler.

Statik bağlantı kurmanın en kolay yolu, nesnenizin bildiriminde belirttiğinizi varsayar [`DECLARE_REGISTRY_RESOURCEID`](reference/registry-macros.md#declare_registry_resourceid) . (ATL tarafından kullanılan varsayılan belirtimdir.)

## <a name="to-create-a-static-link-using-declare_registry_resourceid"></a>Kullanarak statik bağlantı oluşturmak için `DECLARE_REGISTRY_RESOURCEID`

1. Öğesini **`/D _ATL_STATIC_REGISTRY`** **`/D _ATL_DLL`** CL komut satırı yerine belirtin. Daha fazla bilgi için bkz. [`/D`](../build/reference/d-preprocessor-definitions.md).

1. Kodu.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt defteri bileşeni (kaydedici)](../atl/atl-registry-component-registrar.md)
