---
title: (Yalnızca C++) Kaydedici koduna statik bağlantı ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a66ca33aa95ea6ffd59860cf0a55e51266ef5cb
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757704"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>(Yalnızca C++) Kaydedici koduna statik bağlantı ayarlama

C++ istemciler şirketinin kod statik bir bağlantı oluşturabilirsiniz. Statik bağlama şirketinin ayrıştırıcı bir yayın yapısı için yaklaşık 5 K ekler.

Statik bağlama ayarlamak için en basit yolu, belirttiğiniz varsayar [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) nesnenizin bildirimi. (Bu, ATL tarafından kullanılan varsayılan belirtimi)

### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>DECLARE_REGISTRY_RESOURCEID kullanarak statik bir bağlantı oluşturmak için

1. Belirtin [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` /D yerine **_ATL_DLL**.

2. Yeniden derleyin.

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt defteri bileşeni (Kaydedici)](../atl/atl-registry-component-registrar.md)

