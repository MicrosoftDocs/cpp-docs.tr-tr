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
ms.openlocfilehash: b8eb77bc6f99ab6b7d8ca9d51f1a7a8549d8f0c9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>Kaydedici kod (C++ yalnızca) statik bağlantı kurma
C++ istemcileri kayıt şirketinin kod statik bağlantı oluşturabilirsiniz. Statik kayıt şirketinin ayrıştırıcı bağlama yayın derlemesi için yaklaşık 5 K ekler.  
  
 Statik bağlama ayarlamak için en basit yolu, belirttiğiniz varsayar [DECLARE_REGISTRY_RESOURCEID](reference/registry-macros.md#declare_registry_resourceid) , nesnenin bildirimi. (ATL tarafından kullanılan varsayılan belirtimi budur)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>DECLARE_REGISTRY_RESOURCEID kullanarak statik bir bağlantı oluşturmak için  
  
1.  Belirtin [/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` /D yerine**_ATL_DLL**.  
  
2.  Yeniden derleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt defteri bileşeni (Kaydedici)](../atl/atl-registry-component-registrar.md)

