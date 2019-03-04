---
title: Bağlantı noktası genel işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
ms.openlocfilehash: 0313e93ee82bb96f3bfe08e45f70ccfee30dbee6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263890"
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

*pUnkCP*<br/>
[in] Bir işaretçi `IUnknown` bağlanmak istemci nesne istemektedir.

*pUnk*<br/>
[in] İstemcinin bir işaretçiye `IUnknown`.

*IID*<br/>
[in] Bağlantı noktası GUİD'si. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimi aynıdır.

*PDW*<br/>
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

*pUnkCP*<br/>
[in] Bir işaretçi `IUnknown` istemci ile bağlı nesne.

*IID*<br/>
[in] Bağlantı noktası GUİD'si. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimi aynıdır.

*dw*<br/>
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

*PT*<br/>
[in] Havuz harita içeren nesneye bir işaretçi.

*bAdvise*<br/>
[in] Tüm havuz girişleri olun gerekiyorsa TRUE; Tüm havuz girişleri unadvised olması gerekiyorsa FALSE.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Bağlantı Noktası Makroları](../../atl/reference/connection-point-macros.md)
