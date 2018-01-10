---
title: "AFX_EXTENSION_MODULE yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AFX_EXTENSION_MODULE
dev_langs: C++
helpviewer_keywords: AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4ac896fb16aa3c338cadd6273e226eebe986ae7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="afxextensionmodule-structure"></a>AFX_EXTENSION_MODULE Yapısı
`AFX_EXTENSION_MODULE` MFC uzantı DLL'leri başlatma sırasında MFC uzantı DLL modülü durumunu tutmak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct AFX_EXTENSION_MODULE  
{  
    BOOL bInitialized;  
    HMODULE hModule;  
    HMODULE hResource;  
    CRuntimeClass* pFirstSharedClass;  
    COleObjectFactory* pFirstSharedFactory;  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 *bInitialized*  
 **DOĞRU** DLL modülü ile başlatılmışsa `AfxInitExtensionModule`.  
  
 `hModule`  
 DLL modülü tanıtıcısı belirtir.  
  
 *hResource*  
 DLL özel kaynak modülü tanıtıcısı belirtir.  
  
 *pFirstSharedClass*  
 Bir işaretçi bilgilere ( `CRuntimeClass` yapısı) DLL modülünün ilk çalışma zamanı sınıfı hakkında. Çalışma zamanı sınıf listesi başlamasını sağlamak için kullanılır.  
  
 *pFirstSharedFactory*  
 DLL modülünün ilk nesne üreteci için bir işaretçi (bir `COleObjectFactory` nesnesi). Sınıf Fabrika listesi başlangıcı sağlamak üzere kullanılır.  
  
## <a name="remarks"></a>Açıklamalar  
 MFC uzantı DLL'leri iki şeyler gerek kendi `DllMain` işlevi:  
  
-   Çağrı [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) ve dönüş değerini denetleyin.  
  
-   Oluşturma bir **CDynLinkLibrary** DLL verme durumunda nesne [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesneleri veya kendi özel kaynaklar içeriyor.  
  
 `AFX_EXTENSION_MODULE` Yapısı MFC uzantı DLL modül durumu, normal statik nesne oluşturması önce yürütülen bir parçası olarak MFC uzantı DLL'si başlatılmadı çalışma zamanı sınıf nesnelerin bir kopyasını dahil olmak üzere bir kopyasını tutmak için kullanılan `DllMain` olduğu girdi. Örneğin:  
  
 [!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 Depolanan modül bilgilerini `AFX_EXTENSION_MODULE` yapısı halinde kopyalanabilir **CDynLinkLibrary** nesnesi. Örneğin:  
  
 [!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)   
 [AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)

