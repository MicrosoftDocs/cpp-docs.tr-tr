---
title: (Yalnızca C++) Kaydedici koduna statik bağlantı ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
ms.openlocfilehash: b95bd17abca3237710956f3a1bf1b1d6fa9df51e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196672"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>(Yalnızca C++) Kaydedici koduna statik bağlantı ayarlama

C++ istemciler şirketinin kod statik bir bağlantı oluşturabilirsiniz. Statik bağlama şirketinin ayrıştırıcı bir yayın yapısı için yaklaşık 5 K ekler.

Statik bağlama ayarlamak için en basit yolu, belirttiğiniz varsayar [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) nesnenizin bildirimi. (Bu, ATL tarafından kullanılan varsayılan belirtimi)

## <a name="to-create-a-static-link-using-declareregistryresourceid"></a>DECLARE_REGISTRY_RESOURCEID kullanarak statik bir bağlantı oluşturmak için

1. Belirtin [/D](../build/reference/d-preprocessor-definitions.md)  **\_ATL\_statik\_kayıt defteri** yerine **/D \_ATL\_DLL**.

1. Yeniden derleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt defteri bileşeni (Kaydedici)](../atl/atl-registry-component-registrar.md)
