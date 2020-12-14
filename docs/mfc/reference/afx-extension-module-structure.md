---
description: 'Daha fazla bilgi edinin: AFX_EXTENSION_MODULE yapısı'
title: AFX_EXTENSION_MODULE Yapısı
ms.date: 11/04/2016
f1_keywords:
- AFX_EXTENSION_MODULE
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
ms.openlocfilehash: d3a5abd449f13a06aa5d7388b2dd2926a6011973
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248235"
---
# <a name="afx_extension_module-structure"></a>AFX_EXTENSION_MODULE Yapısı

MFC `AFX_EXTENSION_MODULE` UZANTı dll modülünün durumunu tutmak IÇIN MFC uzantı dll 'lerinin başlatılması sırasında kullanılır.

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

*Bağlanabilir*<br/>
DLL modülü ile başlatılmışsa TRUE `AfxInitExtensionModule` .

*hModule*<br/>
DLL modülünün tanıtıcısını belirtir.

*hResource*<br/>
DLL özel kaynak modülünün tanıtıcısını belirtir.

*pFirstSharedClass*<br/>
`CRuntimeClass`Dll modülünün ilk çalışma zamanı sınıfı hakkında bilgi (yapı) işaretçisi. Çalışma zamanı sınıf listesinin başlangıcını sağlamak için kullanılır.

*pFirstSharedFactory*<br/>
DLL modülünün ilk nesne Fabrikası (bir nesne) için bir işaretçi `COleObjectFactory` . Sınıf fabrikası listesinin başlangıcını sağlamak için kullanılır.

## <a name="remarks"></a>Açıklamalar

MFC uzantı dll 'Lerinin kendi işlevleriyle iki şey yapması gerekir `DllMain` :

- [AfxInitExtensionModule 'ü](extension-dll-macros.md#afxinitextensionmodule) çağırın ve dönüş değerini denetleyin.

- `CDynLinkLibrary`Dll [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnelerini dışarı aktaracaktır veya kendi özel kaynaklarına sahipse bir nesne oluşturun.

`AFX_EXTENSION_MODULE`Yapı, daha önce yürütülen normal statik nesne oluşturma 'nin bir parçası olarak MFC UZANTı dll tarafından başlatılmış çalışma zamanı sınıfı nesnelerinin bir kopyası dahil olmak üzere MFC UZANTı dll modülünün bir kopyasını tutmak için kullanılır `DllMain` . Örneğin:

[!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]

Yapıda depolanan modül bilgileri `AFX_EXTENSION_MODULE` `CDynLinkLibrary` nesnesine kopyalanabilir. Örneğin:

[!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)<br/>
[AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)
