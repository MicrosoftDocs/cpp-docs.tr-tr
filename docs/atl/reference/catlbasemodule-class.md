---
title: CAtlBaseModule sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07f1252fe993ff2f2e646528996c1a53d25c5a63
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="catlbasemodule-class"></a>CAtlBaseModule sınıfı
Bu sınıfın her ATL projede örneği.  
  
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
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|Bir işleyici için belirtilen kaynak örneği döndürür.|  
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|Modül örneğinden döndüren bir `CAtlBaseModule` nesnesi.|  
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|Kaynak örneğinden döndüren bir `CAtlBaseModule` nesnesi.|  
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|Bir kaynak örneği saklı tanıtıcıları listesinden kaldırır.|  
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|Kaynak örneği ayarlar bir `CAtlBaseModule` nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|Modülü başlatma başarısız oldu gösteren bir değişken.|  
  
## <a name="remarks"></a>Açıklamalar  
 Örneği `CAtlBaseModule` adlandırılmış _AtlBaseModule içeren modülü örneği için bir tanıtıcı, varsayılan olarak, bir aynı) kaynakları (içeren modülü ve birincil sağlayan modülü işleyicilerine dizisi için bir tanıtıcı her ATL projede mevcut kaynaklar. `CAtlBaseModule` birden çok iş parçacığı güvenli bir şekilde erişilebilir.  
  
 Bu sınıf artık kullanılmıyor değiştirir [CComModule](../../atl/reference/ccommodule-class.md) ATL önceki sürümlerinde kullanılan sınıf  
  
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
 `hInst`  
 Eklenecek kaynak örneği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynak başarıyla true değerini döndürür eklenen, false Aksi takdirde.  
  
##  <a name="catlbasemodule"></a>  CAtlBaseModule::CAtlBaseModule  
 Oluşturucu.  
  
```
CAtlBaseModule() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturur `CAtlBaseModule`.  
  
##  <a name="gethinstanceat"></a>  CAtlBaseModule::GetHInstanceAt  
 Bir işleyici için belirtilen kaynak örneği döndürür.  
  
```
HINSTANCE GetHInstanceAt(int i) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *i*  
 Kaynak örneği sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karşılık gelen hiçbir kaynak örneği varsa kaynak örneği veya NULL ile işleyicisini döndürür.  
  
##  <a name="getmoduleinstance"></a>  CAtlBaseModule::GetModuleInstance  
 Modül örneğinden döndüren bir `CAtlBaseModule` nesnesi.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Modül örneğini döndürür.  
  
##  <a name="getresourceinstance"></a>  CAtlBaseModule::GetResourceInstance  
 Kaynak örneğini döndürür.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynak örneğini döndürür.  
  
##  <a name="m_binitfailed"></a>  CAtlBaseModule::m_bInitFailed  
 Modülü başlatma başarısız oldu gösteren bir değişken.  
  
```
static bool m_bInitFailed;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Modül başlatıldı, true, false başlatmak başarısız olursa.  
  
##  <a name="removeresourceinstance"></a>  CAtlBaseModule::RemoveResourceInstance  
 Bir kaynak örneği saklı tanıtıcıları listesinden kaldırır.  
  
```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hInst`  
 Kaldırmak için kaynak örneği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynak Aksi halde başarıyla kaldırıldı, false ise, true döndürür.  
  
##  <a name="setresourceinstance"></a>  CAtlBaseModule::SetResourceInstance  
 Kaynak örneği ayarlar bir `CAtlBaseModule` nesnesi.  
  
```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hInst`  
 Yeni kaynak örneği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş kaynak örneğini döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Modül sınıfları](../../atl/atl-module-classes.md)
