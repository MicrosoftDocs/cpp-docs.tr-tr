---
title: AFX_EXTENSION_MODULE Yapısı
ms.date: 11/04/2016
f1_keywords:
- AFX_EXTENSION_MODULE
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
ms.openlocfilehash: ee39fcec3083145dbc23c7739897bf89d47578a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539041"
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

*bInitialized*<br/>
DLL modülü ile başlatılmışsa doğru `AfxInitExtensionModule`.

*hModule'ü*<br/>
DLL modül tanıtıcısını belirtir.

*hResource*<br/>
Özel kaynak DLL modül tanıtıcısını belirtir.

*pFirstSharedClass*<br/>
Bilgi için bir işaretçi ( `CRuntimeClass` yapısı) DLL modülün ilk çalışma zamanı sınıf hakkında. Çalışma zamanı sınıf listesi başlamasını sağlamak için kullanılır.

*pFirstSharedFactory*<br/>
DLL modülün ilk nesne üreteci için bir işaretçi (bir `COleObjectFactory` nesne). Sınıf üreteci listesi başlangıcını sağlamak için kullanılır.

## <a name="remarks"></a>Açıklamalar

MFC uzantısı DLL'leri iki şeyler gerek kendi `DllMain` işlevi:

- Çağrı [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) ve dönüş değeri denetleyin.

- Oluşturma bir `CDynLinkLibrary` DLL dışa, nesne [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesneleri veya kendi özel kaynaklara sahip.

`AFX_EXTENSION_MODULE` Yapısı MFC uzantısı DLL modül durumu, normal durağan nesnenin yapımı önce yürütülen bir parçası olarak MFC uzantısı DLL tarafından başlatılmamış. çalışma zamanı sınıf nesnelerin bir kopyasını dahil olmak üzere bir kopyasını tutmak için kullanılan `DllMain` olduğu girdi. Örneğin:

[!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]

İçinde depolanan modülü bilgilerini `AFX_EXTENSION_MODULE` yapısı içine kopyalanabilir `CDynLinkLibrary` nesne. Örneğin:

[!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)<br/>
[AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)

