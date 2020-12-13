---
description: 'Daha fazla bilgi edinin: bağlantı noktası genel Işlevleri'
title: Bağlantı noktası genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
ms.openlocfilehash: 33a9f81b086b572bb31f730e4a6ce1bac0fb45d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141147"
---
# <a name="connection-point-global-functions"></a>Bağlantı noktası genel Işlevleri

Bu işlevler bağlantı noktaları ve havuz haritaları için destek sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

|İşlev|Açıklama|
|-|-|
|[AtlAdvise](#atladvise)|Bir nesnenin bağlantı noktası ve istemcinin havuzu arasında bir bağlantı oluşturur.|
|[AtlUnadvise](#atlunadvise)|İle kurulan bağlantıyı sonlandırır `AtlAdvise` .|
|[AtlAdviseSinkMap](#atladvisesinkmap)|Bir olay havuzu eşlemesindeki girişlerin bir veya daha fazla giriş olduğunu önerir veya vermez.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="atladvise"></a><a name="atladvise"></a> AtlAdvise

Bir nesnenin bağlantı noktası ve istemcinin havuzu arasında bir bağlantı oluşturur.

> [!IMPORTANT]
> Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```

### <a name="parameters"></a>Parametreler

*pUnkCP*<br/>
'ndaki `IUnknown` İstemcinin bağlanmak istediği nesnenin işaretçisi.

*pUnk dili*<br/>
'ndaki İstemci için bir işaretçi `IUnknown` .

*'si*<br/>
'ndaki Bağlantı noktasının GUID 'SI. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimle aynıdır.

*PDW*<br/>
dışı Bağlantıyı benzersiz bir şekilde tanımlayan tanımlama bilgisine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Havuz, bağlantı noktası tarafından desteklenen giden arabirimi uygular. İstemci, *PDW* tanımlama bilgisini kullanarak bağlantıyı [AtlUnadvise](#atlunadvise)'e geçirerek bağlantıyı kaldırır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

## <a name="atlunadvise"></a><a name="atlunadvise"></a> AtlUnadvise

[AtlAdvise](#atladvise)aracılığıyla kurulan bağlantıyı sonlandırır.

> [!IMPORTANT]
> Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```

### <a name="parameters"></a>Parametreler

*pUnkCP*<br/>
'ndaki `IUnknown` İstemcinin bağlandığı nesnenin bir işaretçisi.

*'si*<br/>
'ndaki Bağlantı noktasının GUID 'SI. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimle aynıdır.

*DW*<br/>
'ndaki Bağlantıyı benzersiz bir şekilde tanımlayan tanımlama bilgisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

## <a name="atladvisesinkmap"></a><a name="atladvisesinkmap"></a> AtlAdviseSinkMap

Nesnenin havuz olayı eşlemesindeki tüm girişleri önermek veya öneriyi kaldırmak için bu işlevi çağırın. 

> [!IMPORTANT]
> Bu işlev, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>Parametreler

*Yönergelerinin*<br/>
'ndaki Havuz eşlemesini içeren nesneye yönelik bir işaretçi.

*Rozzden*<br/>
'ndaki Tüm havuz girişleri önermeliyse doğru; Tüm havuz girişlerinin önerilemedi durumunda FALSE.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Bağlantı noktası makroları](../../atl/reference/connection-point-macros.md)
