---
title: AFX_EXTENSION_MODULE yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65f1f2a6416ef93395f7ec73b27a89bf44e2d885
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339390"
---
# <a name="afxextensionmodule-structure"></a>AFX_EXTENSION_MODULE Yapısı
`AFX_EXTENSION_MODULE` MFC uzantısı DLL'leri başlatma sırasında MFC uzantısı DLL modülü durumunu tutmak için kullanılır.  
  
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
 DLL modülü ile başlatılmışsa doğru `AfxInitExtensionModule`.  
  
 *hModule'ü*  
 DLL modül tanıtıcısını belirtir.  
  
 *hResource*  
 Özel kaynak DLL modül tanıtıcısını belirtir.  
  
 *pFirstSharedClass*  
 Bilgi için bir işaretçi ( `CRuntimeClass` yapısı) DLL modülün ilk çalışma zamanı sınıf hakkında. Çalışma zamanı sınıf listesi başlamasını sağlamak için kullanılır.  
  
 *pFirstSharedFactory*  
 DLL modülün ilk nesne üreteci için bir işaretçi (bir `COleObjectFactory` nesne). Sınıf üreteci listesi başlangıcını sağlamak için kullanılır.  
  
## <a name="remarks"></a>Açıklamalar  
 MFC uzantısı DLL'leri iki şeyler gerek kendi `DllMain` işlevi:  
  
-   Çağrı [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) ve dönüş değeri denetleyin.  
  
-   Oluşturma bir `CDynLinkLibrary` DLL dışa, nesne [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesneleri veya kendi özel kaynaklara sahip.  
  
 `AFX_EXTENSION_MODULE` Yapısı MFC uzantısı DLL modül durumu, normal durağan nesnenin yapımı önce yürütülen bir parçası olarak MFC uzantısı DLL tarafından başlatılmamış. çalışma zamanı sınıf nesnelerin bir kopyasını dahil olmak üzere bir kopyasını tutmak için kullanılan `DllMain` olduğu girdi. Örneğin:  
  
 [!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 İçinde depolanan modülü bilgilerini `AFX_EXTENSION_MODULE` yapısı içine kopyalanabilir `CDynLinkLibrary` nesne. Örneğin:  
  
 [!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)   
 [AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)

