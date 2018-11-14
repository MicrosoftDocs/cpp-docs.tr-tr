---
title: (Yalnızca C++) Kaydedici koduna statik bağlantı ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
ms.openlocfilehash: 11600b47abbbd247d099d871fce5e9d5d17d3cf4
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327895"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>(Yalnızca C++) Kaydedici koduna statik bağlantı ayarlama

C++ istemciler şirketinin kod statik bir bağlantı oluşturabilirsiniz. Statik bağlama şirketinin ayrıştırıcı bir yayın yapısı için yaklaşık 5 K ekler.

Statik bağlama ayarlamak için en basit yolu, belirttiğiniz varsayar [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) nesnenizin bildirimi. (Bu, ATL tarafından kullanılan varsayılan belirtimi)

## <a name="to-create-a-static-link-using-declareregistryresourceid"></a>DECLARE_REGISTRY_RESOURCEID kullanarak statik bir bağlantı oluşturmak için

1. Belirtin [/D](../build/reference/d-preprocessor-definitions.md)  **\_ATL\_statik\_kayıt defteri** yerine **/D \_ATL\_DLL**.

1. Yeniden derleyin.

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt defteri bileşeni (Kaydedici)](../atl/atl-registry-component-registrar.md)
