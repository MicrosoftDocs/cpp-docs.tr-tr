---
title: Bağlantı Noktası Genel İşlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
ms.openlocfilehash: 6474297f8b9adf04541f7d232fb88d5e52d4e88c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331526"
---
# <a name="connection-point-global-functions"></a>Bağlantı Noktası Genel İşlevleri

Bu işlevler bağlantı noktaları ve lavabo haritaları için destek sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler Windows Runtime'da çalışan uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlAdvise](#atladvise)|Bir nesnenin bağlantı noktası ve istemcinin havuzu arasında bir bağlantı oluşturur.|
|[AtlUnadvise](#atlunadvise)|Üzerinden kurulan bağlantıyı `AtlAdvise`sonlandırır.|
|[AtlAdviseSinkHaritası](#atladvisesinkmap)|Bir olay lavabo haritasındaki girişleri önerir veya tavsiye etmem.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="atladvise"></a><a name="atladvise"></a>AtlAdvise

Bir nesnenin bağlantı noktası ve istemcinin havuzu arasında bir bağlantı oluşturur.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```

### <a name="parameters"></a>Parametreler

*pUnkCP*<br/>
[içinde] İstemcinin `IUnknown` bağlanmak istediği nesnenin işaretçisi.

*Punk*<br/>
[içinde] İstemci için bir `IUnknown`işaretçi .

*ııd*<br/>
[içinde] Bağlantı noktasının GUID'i. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirim aynıdır.

*Pdw*<br/>
[çıkış] Bağlantıyı benzersiz olarak tanımlayan çerez için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Lavabo, bağlantı noktası tarafından desteklenen giden arabirimi uygular. İstemci, bağlantıyı [AtlUnadvise'a](#atlunadvise)geçirerek kaldırmak için *pdw* çerezini kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

## <a name="atlunadvise"></a><a name="atlunadvise"></a>AtlUnadvise

[AtlAdvise](#atladvise)aracılığıyla kurulan bağlantıyı sonlandırır.

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```

### <a name="parameters"></a>Parametreler

*pUnkCP*<br/>
[içinde] İstemcinin `IUnknown` bağlı olduğu nesnenin işaretçisi.

*ııd*<br/>
[içinde] Bağlantı noktasının GUID'i. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirim aynıdır.

*Dw*<br/>
[içinde] Bağlantıyı benzersiz olarak tanımlayan tanımlama bilgisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

## <a name="atladvisesinkmap"></a><a name="atladvisesinkmap"></a>AtlAdviseSinkHaritası

Nesnenin havuz olayı eşlemesindeki tüm girişleri önermek veya öneriyi kaldırmak için bu işlevi çağırın. 

> [!IMPORTANT]
> Bu işlev, Windows Runtime'da çalışan uygulamalarda kullanılamaz.

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
[içinde] Lavabo eşlemi içeren nesneye bir işaretçi.

*bAdvise*<br/>
[içinde] Tüm lavabo girişleri tavsiye edilecekse DOĞRU; Tüm lavabo girişleri tavsiye edilmezse YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Bağlantı Noktası Makroları](../../atl/reference/connection-point-macros.md)
