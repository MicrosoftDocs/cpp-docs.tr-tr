---
title: Bağlantı noktası genel işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f68c22ff88ac92357dabfef8076c160271a76378
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756496"
---
# <a name="connection-point-global-functions"></a>Bağlantı noktası genel işlevleri

Bu işlevler, bağlantı noktaları için destek sağlar ve havuz eşlemeleri.

> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen İşlevler, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlAdvise](#atladvise)|Bir nesnenin bağlantı noktası ve istemcinin havuzu arasında bir bağlantı oluşturur.|
|[AtlUnadvise](#atlunadvise)|Yoluyla kurulmuş bağlantıyı sonlandırır `AtlAdvise`.|
|[AtlAdviseSinkMap](#atladvisesinkmap)|Öneren veya bir olay havuzu eşlemesi girişleri unadvises.|  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="atladvise"></a>  AtlAdvise

Bir nesnenin bağlantı noktası ve istemcinin havuzu arasında bir bağlantı oluşturur.

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```

### <a name="parameters"></a>Parametreler

*pUnkCP*  
[in] Bir işaretçi `IUnknown` bağlanmak istemci nesne istemektedir.

*pUnk*  
[in] İstemcinin bir işaretçiye `IUnknown`.

*IID*  
[in] Bağlantı noktası GUİD'si. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimi aynıdır.

*PDW*  
[out] Bağlantı benzersiz olarak tanıtan bir tanımlama bilgisi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Havuz bağlantı noktası tarafından desteklenen giden arabirimi uygular. İstemcinin kullandığı *pdw* aktararak bağlantısını kaldırmak için tanımlama bilgisi [AtlUnadvise](#atlunadvise).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

##  <a name="atlunadvise"></a>  AtlUnadvise

Yoluyla kurulmuş bağlantıyı sonlandırır [AtlAdvise](#atladvise).

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```

### <a name="parameters"></a>Parametreler

*pUnkCP*  
[in] Bir işaretçi `IUnknown` istemci ile bağlı nesne.

*IID*  
[in] Bağlantı noktası GUİD'si. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimi aynıdır.

*dw*  
[in] Bağlantı benzersiz olarak tanımlayan tanımlama bilgisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

##  <a name="atladvisesinkmap"></a>  AtlAdviseSinkMap

Nesnenin havuz olayı eşlemesindeki tüm girişleri önermek veya öneriyi kaldırmak için bu işlevi çağırın. 

> [!IMPORTANT]
>  Bu işlev, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>Parametreler

*PT*  
[in] Havuz harita içeren nesneye bir işaretçi.

*bAdvise*  
[in] Tüm havuz girişleri olun gerekiyorsa TRUE; Tüm havuz girişleri unadvised olması gerekiyorsa FALSE.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevleri](../../atl/reference/atl-functions.md)   
[Bağlantı Noktası Makroları](../../atl/reference/connection-point-macros.md)
