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
ms.openlocfilehash: 3bde1d369ce5339f07ea36979ef50ddccb0d30d1
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860283"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>(Yalnızca C++) Kaydedici koduna statik bağlantı ayarlama

C++ istemciler şirketinin kod statik bir bağlantı oluşturabilirsiniz. Statik bağlama şirketinin ayrıştırıcı bir yayın yapısı için yaklaşık 5 K ekler.

Statik bağlama ayarlamak için en basit yolu, belirttiğiniz varsayar [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) nesnenizin bildirimi. (Bu, ATL tarafından kullanılan varsayılan belirtimi)

## <a name="to-create-a-static-link-using-declareregistryresourceid"></a>DECLARE_REGISTRY_RESOURCEID kullanarak statik bir bağlantı oluşturmak için

1. Belirtin [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` /D yerine **_ATL_DLL**.

1. Yeniden derleyin.

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt defteri bileşeni (Kaydedici)](../atl/atl-registry-component-registrar.md)
