---
title: CAtlBaseModule sınıfı
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
ms.openlocfilehash: d382d1fe7d50a2fdeefc9b477625580792de7d6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247158"
---
# <a name="catlbasemodule-class"></a>CAtlBaseModule sınıfı

Bu sınıf, her bir ATL projesinde oluşturulur.

## <a name="syntax"></a>Sözdizimi

```
class CAtlBaseModule : public _ATL_BASE_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|Bir kaynak örneği saklı tanıtıcıları listesine ekler.|
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|Belirtilen kaynak örneğine bir tanıtıcı döndürür.|
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|Modül örneğinden döndürür bir `CAtlBaseModule` nesne.|
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|Kaynak örneği döndüren bir `CAtlBaseModule` nesne.|
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|Bir kaynak örneğini saklı tanıtıcıları listesinden kaldırır.|
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|Kaynak örneği ayarlar bir `CAtlBaseModule` nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|Modül başlatma başarısız oldu gösteren bir değişken.|

## <a name="remarks"></a>Açıklamalar

Örneği `CAtlBaseModule` adlandırılmış _AtlBaseModule içeren modül örneği için bir tanıtıcı, (varsayılan olarak, bir aynı) kaynakları içeren modül ve birincil sağlayan modülü tanıtıcıları bir dizi için bir tanıtıcı, her bir ATL projesi içinde mevcut kaynaklar. `CAtlBaseModule` birden fazla iş parçacığından güvenli bir şekilde erişilebilir.

Bu sınıf artık kullanılmıyor değiştirir [CComModule](../../atl/reference/ccommodule-class.md) ATL'ın önceki sürümlerinde kullanılan sınıf

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)

`CAtlBaseModule`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcore.h

##  <a name="addresourceinstance"></a>  CAtlBaseModule::AddResourceInstance

Bir kaynak örneği saklı tanıtıcıları listesine ekler.

```
bool AddResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parametreler

*hInst*<br/>
Eklemek için kaynak örneği.

### <a name="return-value"></a>Dönüş Değeri

Kaynak başarılı olduysa true döndürür eklendi, yanlış Aksi takdirde.

##  <a name="catlbasemodule"></a>  CAtlBaseModule::CAtlBaseModule

Oluşturucu.

```
CAtlBaseModule() throw();
```

### <a name="remarks"></a>Açıklamalar

Oluşturur `CAtlBaseModule`.

##  <a name="gethinstanceat"></a>  CAtlBaseModule::GetHInstanceAt

Belirtilen kaynak örneğine bir tanıtıcı döndürür.

```
HINSTANCE GetHInstanceAt(int i) throw();
```

### <a name="parameters"></a>Parametreler

*i*<br/>
Kaynak örneği sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlişkili kaynak örneği varsa, kaynak örneği veya NULL tanıtıcısını döndürür.

##  <a name="getmoduleinstance"></a>  CAtlBaseModule::GetModuleInstance

Modül örneğinden döndürür bir `CAtlBaseModule` nesne.

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Modül örneği döndürür.

##  <a name="getresourceinstance"></a>  CAtlBaseModule::GetResourceInstance

Kaynak örneği döndürür.

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak örneği döndürür.

##  <a name="m_binitfailed"></a>  CAtlBaseModule::m_bInitFailed

Modül başlatma başarısız oldu gösteren bir değişken.

```
static bool m_bInitFailed;
```

### <a name="remarks"></a>Açıklamalar

Modül başlatılamadı gerekiyorsa true, false başlatmak başarısız olursa.

##  <a name="removeresourceinstance"></a>  CAtlBaseModule::RemoveResourceInstance

Bir kaynak örneğini saklı tanıtıcıları listesinden kaldırır.

```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parametreler

*hInst*<br/>
Kaldırılacak kaynak örneği.

### <a name="return-value"></a>Dönüş Değeri

Kaynak, aksi halde başarıyla kaldırıldı, false ise, true döndürür.

##  <a name="setresourceinstance"></a>  CAtlBaseModule::SetResourceInstance

Kaynak örneği ayarlar bir `CAtlBaseModule` nesne.

```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>Parametreler

*hInst*<br/>
Yeni kaynak örneği.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş kaynak örneğini döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
