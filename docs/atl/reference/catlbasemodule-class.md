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
ms.openlocfilehash: d57d6e631cb287496a4ff5516e97e65ec0152e30
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168299"
---
# <a name="catlbasemodule-class"></a>CAtlBaseModule Sınıfı

Bu sınıf, her ATL projesinde örneği oluşturulur.

## <a name="syntax"></a>Sözdizimi

```cpp
class CAtlBaseModule : public _ATL_BASE_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlBaseModule:: CAtlBaseModule](#catlbasemodule)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlBaseModule:: Addresourceınstance](#addresourceinstance)|Depolanan tutamaçlar listesine bir kaynak örneği ekler.|
|[CAtlBaseModule:: Gethınstanceat](#gethinstanceat)|Belirtilen kaynak örneğine bir tanıtıcı döndürür.|
|[CAtlBaseModule:: GetModuleInstance](#getmoduleinstance)|Bir `CAtlBaseModule` nesneden modül örneğini döndürür.|
|[CAtlBaseModule:: GetResourceInstance](#getresourceinstance)|Bir `CAtlBaseModule` nesneden kaynak örneğini döndürür.|
|[CAtlBaseModule:: Removeresourceınstance](#removeresourceinstance)|Depolanan tutamaçlar listesinden bir kaynak örneğini kaldırır.|
|[CAtlBaseModule:: Setresourceınstance](#setresourceinstance)|Bir `CAtlBaseModule` nesnenin kaynak örneğini ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAtlBaseModule:: m_bInitFailed](#m_binitfailed)|Modül başlatmanın başarısız olup olmadığını gösteren bir değişken.|

## <a name="remarks"></a>Açıklamalar

Bir `CAtlBaseModule` adlandırılmış _AtlBaseModule örneği, modül örneğine bir tanıtıcı, kaynakları içeren modül tanıtıcısı (varsayılan olarak, bir ve aynı) ve birincil kaynakları sağlayan modüllerle bir dizi tanıtıcı IÇEREN her atl projesinde bulunur. `CAtlBaseModule`, birden fazla iş parçacığından güvenle erişilebilir.

Bu sınıf, ATL 'nin önceki sürümlerinde kullanılan eski [CComModule](../../atl/reference/ccommodule-class.md) sınıfının yerini alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)

`CAtlBaseModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="catlbasemoduleaddresourceinstance"></a><a name="addresourceinstance"></a>CAtlBaseModule:: Addresourceınstance

Depolanan tutamaçlar listesine bir kaynak örneği ekler.

```cpp
bool AddResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parametreler

*hInst*<br/>
Eklenecek kaynak örneği.

### <a name="return-value"></a>Dönüş Değeri

Kaynak başarıyla eklendiyse true, aksi takdirde false döndürür.

## <a name="catlbasemodulecatlbasemodule"></a><a name="catlbasemodule"></a>CAtlBaseModule:: CAtlBaseModule

Oluşturucu.

```cpp
CAtlBaseModule() throw();
```

### <a name="remarks"></a>Açıklamalar

Öğesini oluşturur `CAtlBaseModule`.

## <a name="catlbasemodulegethinstanceat"></a><a name="gethinstanceat"></a>CAtlBaseModule:: Gethınstanceat

Belirtilen kaynak örneğine bir tanıtıcı döndürür.

```cpp
HINSTANCE GetHInstanceAt(int i) throw();
```

### <a name="parameters"></a>Parametreler

*kaydedemiyorum*<br/>
Kaynak örneğinin numarası.

### <a name="return-value"></a>Dönüş Değeri

Kaynak örneğine tanıtıcıyı döndürür veya karşılık gelen kaynak örneği yoksa NULL değeri döndürür.

## <a name="catlbasemodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CAtlBaseModule:: GetModuleInstance

Bir `CAtlBaseModule` nesneden modül örneğini döndürür.

```cpp
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Modül örneğini döndürür.

## <a name="catlbasemodulegetresourceinstance"></a><a name="getresourceinstance"></a>CAtlBaseModule:: GetResourceInstance

Kaynak örneğini döndürür.

```cpp
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak örneğini döndürür.

## <a name="catlbasemodulem_binitfailed"></a><a name="m_binitfailed"></a>CAtlBaseModule:: m_bInitFailed

Modül başlatmanın başarısız olup olmadığını gösteren bir değişken.

```cpp
static bool m_bInitFailed;
```

### <a name="remarks"></a>Açıklamalar

Modül başlatılmışsa true, başlatılamadığından false.

## <a name="catlbasemoduleremoveresourceinstance"></a><a name="removeresourceinstance"></a>CAtlBaseModule:: Removeresourceınstance

Depolanan tutamaçlar listesinden bir kaynak örneğini kaldırır.

```cpp
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parametreler

*hInst*<br/>
Kaldırılacak kaynak örneği.

### <a name="return-value"></a>Dönüş Değeri

Kaynak başarıyla kaldırılmışsa true, aksi takdirde false döndürür.

## <a name="catlbasemodulesetresourceinstance"></a><a name="setresourceinstance"></a>CAtlBaseModule:: Setresourceınstance

Bir `CAtlBaseModule` nesnenin kaynak örneğini ayarlar.

```cpp
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parametreler

*hInst*<br/>
Yeni kaynak örneği.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş kaynak örneğini döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
