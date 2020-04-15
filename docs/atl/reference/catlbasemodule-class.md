---
title: CAtlBaseModule Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::AddResourceInstance
- ATLCORE/ATL::CAtlBaseModule::GetHInstanceAt
- ATLCORE/ATL::CAtlBaseModule::GetModuleInstance
- ATLCORE/ATL::CAtlBaseModule::GetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::RemoveResourceInstance
- ATLCORE/ATL::CAtlBaseModule::SetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::m_bInitFailed
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
ms.openlocfilehash: a55412eff18fd04ac4e41c0f001991c1cf725b9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321505"
---
# <a name="catlbasemodule-class"></a>CAtlBaseModule Sınıfı

Bu sınıf her ATL projesinde anında hazırlanır.

## <a name="syntax"></a>Sözdizimi

```
class CAtlBaseModule : public _ATL_BASE_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlBaseModülü::CAtlBaseModülü](#catlbasemodule)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|Depolanan işler listesine bir kaynak örneği ekler.|
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|Bir işbıt'ı belirli bir kaynak örneğine döndürür.|
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|Modül örneğini bir `CAtlBaseModule` nesneden döndürür.|
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|Kaynak örneğini bir `CAtlBaseModule` nesneden döndürür.|
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|Bir kaynak örneğini depolanan tanıtıcılar listesinden kaldırır.|
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|`CAtlBaseModule` Nesnenin kaynak örneğini ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAtlBaseModülü::m_bInitFailed](#m_binitfailed)|Modül başlatma başarısız olup olmadığını gösteren bir değişken.|

## <a name="remarks"></a>Açıklamalar

`CAtlBaseModule` Modül örneğine bir tanıtıcı, kaynakları içeren modüle bir tutamaç (varsayılan olarak bir ve aynıdır) ve birincil kaynakları sağlayan modüllere bir dizi tutamaç içeren her ATL projesinde adlandırılmış _AtlBaseModule bir örneği bulunur. `CAtlBaseModule`birden fazla iş parçacığı ndan güvenle erişilebilir.

Bu sınıf, ATL'nin önceki sürümlerinde kullanılan eski [CComModule](../../atl/reference/ccommodule-class.md) sınıfının yerini alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)

`CAtlBaseModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore.h

## <a name="catlbasemoduleaddresourceinstance"></a><a name="addresourceinstance"></a>CAtlBaseModule::AddResourceInstance

Depolanan işler listesine bir kaynak örneği ekler.

```
bool AddResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parametreler

*hInst*<br/>
Eklenecek kaynak örneği.

### <a name="return-value"></a>Dönüş Değeri

Kaynak başarıyla ekildiyse doğru döndürür, aksi takdirde yanlış.

## <a name="catlbasemodulecatlbasemodule"></a><a name="catlbasemodule"></a>CAtlBaseModülü::CAtlBaseModülü

Oluşturucu.

```
CAtlBaseModule() throw();
```

### <a name="remarks"></a>Açıklamalar

`CAtlBaseModule`Oluşturur.

## <a name="catlbasemodulegethinstanceat"></a><a name="gethinstanceat"></a>CAtlBaseModule::GetHInstanceAt

Bir işbıt'ı belirli bir kaynak örneğine döndürür.

```
HINSTANCE GetHInstanceAt(int i) throw();
```

### <a name="parameters"></a>Parametreler

*Ⅰ*<br/>
Kaynak örneğinin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Karşılık gelen kaynak örneği yoksa işbiti kaynak örneğine veya NULL'a döndürür.

## <a name="catlbasemodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CAtlBaseModule::GetModuleInstance

Modül örneğini bir `CAtlBaseModule` nesneden döndürür.

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Modül örneğini döndürür.

## <a name="catlbasemodulegetresourceinstance"></a><a name="getresourceinstance"></a>CAtlBaseModule::GetResourceInstance

Kaynak örneğini döndürür.

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak örneğini döndürür.

## <a name="catlbasemodulem_binitfailed"></a><a name="m_binitfailed"></a>CAtlBaseModülü::m_bInitFailed

Modül başlatma başarısız olup olmadığını gösteren bir değişken.

```
static bool m_bInitFailed;
```

### <a name="remarks"></a>Açıklamalar

Modül başharfe bürünseydi doğru, başharfe atılamadıysa yanlış.

## <a name="catlbasemoduleremoveresourceinstance"></a><a name="removeresourceinstance"></a>CAtlBaseModule::RemoveResourceInstance

Bir kaynak örneğini depolanan tanıtıcılar listesinden kaldırır.

```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parametreler

*hInst*<br/>
Kaldırılacak kaynak örneği.

### <a name="return-value"></a>Dönüş Değeri

Kaynak başarıyla kaldırıldıysa doğru döndürür, aksi takdirde yanlış.

## <a name="catlbasemodulesetresourceinstance"></a><a name="setresourceinstance"></a>CAtlBaseModule::SetResourceInstance

`CAtlBaseModule` Nesnenin kaynak örneğini ayarlar.

```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parametreler

*hInst*<br/>
Yeni kaynak örneği.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş kaynak örneğini döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Modül Sınıfları](../../atl/atl-module-classes.md)
