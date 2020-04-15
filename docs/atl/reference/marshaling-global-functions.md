---
title: Hazırlama Genel İşlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
ms.openlocfilehash: b839e93b6251a09ce79df60a49b4054d1af76cc9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326260"
---
# <a name="marshaling-global-functions"></a>Hazırlama Genel İşlevleri

Bu işlevler, mareşalveri verisini arabirim işaretçilerine dönüştürmek ve mareşallik etmek için destek sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler Windows Runtime'da çalışan uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Mareşal verilerini `IStream` ve işaretçiyi serbest bırakır.|
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Yeni bir akış nesnesi oluşturur ve belirtilen arabirim işaretçisini işareteder.|
|[AtlUnmarshalPtr](#atlunmarshalptr)|Bir akışın işaretçi verilerini arabirim işaretçisine dönüştürür.|

## <a name="requirements"></a>Gereksinimler:

**Üstbilgi:** atlbase.h

## <a name="atlfreemarshalstream"></a><a name="atlfreemarshalstream"></a>AtlFreeMarshalStream

Akıştaki sıralama verilerini serbest bırakır, ardından da akış işaretçisini serbest bırakır.

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[içinde] Mareşallik `IStream` için kullanılan akışüzerindeki arabirimeye işaretçi.

### <a name="example"></a>Örnek

[AtlMarshalPtrInProc](#atlmarshalptrinproc)örneğine bakın.

## <a name="atlmarshalptrinproc"></a><a name="atlmarshalptrinproc"></a>AtlMarshalPtrInProc

Yeni bir akış nesnesi oluşturur, proxy CLSID değerini akışa yazar ve proxy'yi akış içinde başlatmak üzere gerekli olan veriyi yazarak belirtilen arabirim işaretçisini sıralar.

```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
[içinde] Arabirimin işaretçisi.

*ııd*<br/>
[içinde] Arayüz GUID marshaled ediliyor.

*Ppstream*<br/>
[çıkış] Mareşallik `IStream` için kullanılan yeni akış nesnesi üzerinde arabirim için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

MSHLFLAGS_TABLESTRONG bayrağı, işaretçinin birden çok akışa marshaled böylece ayarlanır. İşaretçi birden çok kez de kıdamış olabilir.

Mareşallik başarısız olursa, akış işaretçisi serbest bırakılır.

`AtlMarshalPtrInProc`yalnızca işlem içi bir nesneye işaretçi üzerinde kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]

## <a name="atlunmarshalptr"></a><a name="atlunmarshalptr"></a>AtlUnmarshalPtr

Akışın sıralama verilerini istemci tarafından kullanılabilen bir arabirim işaretçisine dönüştürür.

```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[içinde] Derenin pişmeyen bir işaretçisi.

*ııd*<br/>
[içinde] Arabirimin GUID'i unmarshaled ediliyor.

*ppUnk*<br/>
[çıkış] Mareşal olmayan arabirime bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="example"></a>Örnek

[AtlMarshalPtrInProc](#atlmarshalptrinproc)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
