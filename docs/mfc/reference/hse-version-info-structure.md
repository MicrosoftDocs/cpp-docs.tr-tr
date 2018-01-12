---
title: "Hse_versıon_ınfo yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: HSE_VERSION_INFO
dev_langs: C++
helpviewer_keywords: HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 108f826ffaa17de65dafe246ab6724fac2b134f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hseversioninfo-structure"></a>HSE_VERSION_INFO Yapısı
Bu yapı işaret ediyor `pVer` parametresinde `CHttpServer::GetExtensionVersion` üye işlevi. ISA sürüm numarasını ve ISA metin açıklamasını sağlar  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef struct _HSE_VERSION_INFO {  
    DWORD dwExtensionVersion;  
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *dwExtensionVersion*  
 ISA sürüm numarası  
  
 *lpszExtensionDesc*  
 ISA metin açıklaması Varsayılan uygulama yer tutucu metin sağlar; geçersiz kılma `CHttpServer::GetExtensionVersion` kendi açıklamanızı sağlamak için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** httpext.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

