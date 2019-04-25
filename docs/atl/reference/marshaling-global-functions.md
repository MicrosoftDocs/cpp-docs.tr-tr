---
title: Hazırlama genel işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
ms.openlocfilehash: cac6e316ad6b5d3f49c171c940d9129060744aee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274700"
---
# <a name="marshaling-global-functions"></a>Hazırlama genel işlevleri

Bu işlevler, hazırlama ve veri hazırlama, arabirim işaretçilerini dönüştürme için destek sağlar.

> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen İşlevler, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

|||
|-|-|
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Sıralama verilerini serbest bırakır ve `IStream` işaretçi.|
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Yeni bir akış nesnesi oluşturur ve belirtilen arabirim işaretçisini sıralar.|
|[AtlUnmarshalPtr](#atlunmarshalptr)|Bir akışın sıralama verilerini bir arabirim işaretçisi dönüştürür.|

## <a name="requirements"></a>Gereksinimler:

**Başlık:** atlbase.h

##  <a name="atlfreemarshalstream"></a>  AtlFreeMarshalStream

Akıştaki sıralama verilerini serbest bırakır, ardından da akış işaretçisini serbest bırakır.

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[in] Bir işaretçi `IStream` arabirimde sıralama için kullanılan akış.

### <a name="example"></a>Örnek

Örneğin bakın [AtlMarshalPtrInProc](#atlmarshalptrinproc).

##  <a name="atlmarshalptrinproc"></a>  AtlMarshalPtrInProc

Yeni bir akış nesnesi oluşturur, proxy CLSID değerini akışa yazar ve proxy'yi akış içinde başlatmak üzere gerekli olan veriyi yazarak belirtilen arabirim işaretçisini sıralar.

```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```

### <a name="parameters"></a>Parametreler

*pUnk*<br/>
[in] Sıralanması arabirim işaretçisi.

*IID*<br/>
[in] Sıralanmış arabiriminin GUID'si.

*ppStream*<br/>
[out] Bir işaretçi `IStream` arabirimde sıralama için kullanılan yeni akış nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

İşaretçi için birden çok akış sıralanabilir şekilde MSHLFLAGS_TABLESTRONG bayrağı ayarlanır. İşaretçiyi, ayrıca birden çok kez iptal olabilir.

Hazırlama başarısız olursa, akış işaretçisini serbest bırakılır.

`AtlMarshalPtrInProc` yalnızca işlem içi nesneye bir işaretçi üzerinde kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]

##  <a name="atlunmarshalptr"></a>  AtlUnmarshalPtr

Akışın sıralama verilerini istemci tarafından kullanılabilen bir arabirim işaretçisine dönüştürür.

```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
[in] Yanlış akış için bir işaretçi.

*IID*<br/>
[in] Yanlış arabiriminin GUID'si.

*ppUnk*<br/>
[out] İptal arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="example"></a>Örnek

Örneğin bakın [AtlMarshalPtrInProc](#atlmarshalptrinproc).

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
