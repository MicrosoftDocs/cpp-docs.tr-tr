---
title: "Kaydedici kod (C++ yalnızca) statik bağlantı kurma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d49ed2a56738ec784c8a1a2cc3c13239f7317270
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Kaydedici kod (C++ yalnızca) statik bağlantı kurma
C++ istemcileri kayıt şirketinin kod statik bağlantı oluşturabilirsiniz. Statik kayıt şirketinin ayrıştırıcı bağlama yayın derlemesi için yaklaşık 5 K ekler.  
  
 Statik bağlama ayarlamak için en basit yolu, belirttiğiniz varsayar [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) , nesnenin bildirimi. (ATL tarafından kullanılan varsayılan belirtimi budur)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>DECLARE_REGISTRY_RESOURCEID kullanarak statik bir bağlantı oluşturmak için  
  
1.  Belirtin [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` /D yerine**_ATL_DLL**.  
  
2.  Yeniden derleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt defteri bileşeni (Kaydedici)](../atl/atl-registry-component-registrar.md)

