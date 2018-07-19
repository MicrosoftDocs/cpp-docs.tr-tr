---
title: CAtlWinModule sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cbbee8a404b679c8411470215821b8cdcccc695e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885227"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule sınıfı
Bu sınıf, ATL Pencereleme bileşenleri için destek sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAtlWinModule : public _ATL_WIN_MODULE
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlWinModule::CAtlWinModule](#catlwinmodule)|Oluşturucu.|  
|[CAtlWinModule:: ~ CAtlWinModule](#dtor)|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|Bir veri nesnesine ekler.|  
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Pencere modülü veri nesnesine bir işaretçi döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf Pencereleme özellikleri gerektiren tüm ATL sınıfları için destek sağlar.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)  
  
 `CAtlWinModule`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="addcreatewnddata"></a>  CAtlWinModule::AddCreateWndData  
 Bu yöntem başlatır ve ekler bir `_AtlCreateWndData` yapısı.  
  
```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```  
  
### <a name="parameters"></a>Parametreler  
 *pData*  
 İşaretçi `_AtlCreateWndData` yapısı başlatılamadı ve geçerli modülüne eklendi.  
  
 *pObject*  
 Bir nesnenin işaretçisine **bu** işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin çağırdığı [AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) hangi başlatır bir [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısı. Bu yapı depolayacak **bu** işaretçisi, pencere yordamları sınıfı örneğinde elde etmek üzere kullanılır.  
  
##  <a name="catlwinmodule"></a>  CAtlWinModule::CAtlWinModule  
 Oluşturucu.  
  
```
CAtlWinModule();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatma başarısız olursa bir **EXCEPTION_NONCONTINUABLE** özel durumu oluşturulur.  
  
##  <a name="dtor"></a>  CAtlWinModule:: ~ CAtlWinModule  
 Yıkıcı.  
  
```
~CAtlWinModule();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="extractcreatewnddata"></a>  CAtlWinModule::ExtractCreateWndData  
 Bu yöntem bir işaretçi döndürür. bir `_AtlCreateWndData` yapısı.  
  
```
void* ExtractCreateWndData();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür `_AtlCreateWndData` yapısı ile daha önce eklediğiniz [CAtlWinModule::AddCreateWndData](#addcreatewnddata), ya da nesne mevcut yoksa NULL.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)   
 [Modül sınıfları](../../atl/atl-module-classes.md)
