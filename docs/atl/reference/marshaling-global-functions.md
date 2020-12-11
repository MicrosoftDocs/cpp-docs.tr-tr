---
description: 'Daha fazla bilgi edinin: genel Işlevleri sıralama'
title: Genel Işlevleri sıralama
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
ms.openlocfilehash: 5652ccf89090ba1d0f00c03472e29da9158b781e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157951"
---
# <a name="marshaling-global-functions"></a>Genel Işlevleri sıralama

Bu işlevler sıralama verilerini sıralama ve arabirim işaretçilerine dönüştürme desteği sağlar.

> [!IMPORTANT]
> Aşağıdaki tabloda listelenen işlevler, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

|Ad|Açıklama|
|-|-|
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Sıralama verilerini ve `IStream` işaretçiyi yayınlar.|
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Yeni bir akış nesnesi oluşturur ve belirtilen arabirim işaretçisini sıralar.|
|[AtlUnmarshalPtr](#atlunmarshalptr)|Bir akışın sıralama verilerini bir arabirim işaretçisine dönüştürür.|

## <a name="requirements"></a>Gereksinimler:

**Üstbilgi:** atlbase. h

## <a name="atlfreemarshalstream"></a><a name="atlfreemarshalstream"></a> AtlFreeMarshalStream

Akıştaki sıralama verilerini serbest bırakır, ardından da akış işaretçisini serbest bırakır.

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
'ndaki `IStream` Sıralama için kullanılan akıştaki arabirime yönelik bir işaretçi.

### <a name="example"></a>Örnek

[Atlmarshalptrinproc](#atlmarshalptrinproc)örneğine bakın.

## <a name="atlmarshalptrinproc"></a><a name="atlmarshalptrinproc"></a> AtlMarshalPtrInProc

Yeni bir akış nesnesi oluşturur, proxy CLSID değerini akışa yazar ve proxy'yi akış içinde başlatmak üzere gerekli olan veriyi yazarak belirtilen arabirim işaretçisini sıralar.

```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki Sıralanabilen arabirime yönelik bir işaretçi.

*'si*<br/>
'ndaki Sıralanan arabirimin GUID 'ı.

*ppStream*<br/>
dışı `IStream` Sıralama için kullanılan yeni Stream nesnesindeki arabirime yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

MSHLFLAGS_TABLESTRONG bayrağı, işaretçinin birden çok akış için sıralanabilmesi için ayarlanır. İşaretçi birden çok kez sıralanabilen bir sıra olabilir.

Sıralama başarısız olursa, akış işaretçisi serbest bırakılır.

`AtlMarshalPtrInProc` yalnızca işlem içi bir nesne için bir işaretçi üzerinde kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]

## <a name="atlunmarshalptr"></a><a name="atlunmarshalptr"></a> AtlUnmarshalPtr

Akışın sıralama verilerini istemci tarafından kullanılabilen bir arabirim işaretçisine dönüştürür.

```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```

### <a name="parameters"></a>Parametreler

*pStream*<br/>
'ndaki Sıralanmakta olan akışa yönelik bir işaretçi.

*'si*<br/>
'ndaki Sıralanmakta olan arabirimin GUID 'SI.

*ppUnk*<br/>
dışı Sıralanabilen arabirime yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="example"></a>Örnek

[Atlmarshalptrinproc](#atlmarshalptrinproc)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
