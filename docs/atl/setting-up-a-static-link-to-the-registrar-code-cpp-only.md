---
title: Kaydedici kod (C++ yalnızca) statik bağlantı kurma | Microsoft Docs
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
ms.openlocfilehash: dca93c8f0fcae578700a9d9970977179fbd142d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360194"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Kaydedici kod (C++ yalnızca) statik bağlantı kurma
C++ istemcileri kayıt şirketinin kod statik bağlantı oluşturabilirsiniz. Statik kayıt şirketinin ayrıştırıcı bağlama yayın derlemesi için yaklaşık 5 K ekler.  
  
 Statik bağlama ayarlamak için en basit yolu, belirttiğiniz varsayar [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) , nesnenin bildirimi. (ATL tarafından kullanılan varsayılan belirtimi budur)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>DECLARE_REGISTRY_RESOURCEID kullanarak statik bir bağlantı oluşturmak için  
  
1.  Belirtin [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` /D yerine **_ATL_DLL**.  
  
2.  Yeniden derleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt defteri bileşeni (Kaydedici)](../atl/atl-registry-component-registrar.md)

