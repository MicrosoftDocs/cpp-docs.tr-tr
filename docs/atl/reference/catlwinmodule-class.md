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
ms.openlocfilehash: 14b918747d9b7bee1b661eebd61fbb35325861e7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358058"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule sınıfı
Bu sınıf ATL Pencereleme bileşenleri için destek sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAtlWinModule : public _ATL_WIN_MODULE
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlWinModule::CAtlWinModule](#catlwinmodule)|Oluşturucu.|  
|[CAtlWinModule:: ~ CAtlWinModule](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|Bir veri nesnesi ekler.|  
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Bir işaretçi pencere modülü veri nesnesi döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf Pencereleme özellikleri gerektiren tüm ATL sınıfları için destek sağlar.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)  
  
 `CAtlWinModule`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="addcreatewnddata"></a>  CAtlWinModule::AddCreateWndData  
 Bu yöntem, başlatır ve ekler bir `_AtlCreateWndData` yapısı.  
  
```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `pData`  
 İşaretçi `_AtlCreateWndData` başlatıldı ve geçerli modülüne eklenmiş yapısı.  
  
 `pObject`  
 Bir nesnenin işaretçi **bu** işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) hangi başlatır bir [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısı. Bu yapı depolayacak **bu** işaretçi, pencere yordamları sınıf örneği elde etmek üzere kullanılır.  
  
##  <a name="catlwinmodule"></a>  CAtlWinModule::CAtlWinModule  
 Oluşturucu.  
  
```
CAtlWinModule();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatma başarısız olursa bir **EXCEPTION_NONCONTINUABLE** özel durum oluşturulur.  
  
##  <a name="dtor"></a>  CAtlWinModule:: ~ CAtlWinModule  
 Yok Edicisi.  
  
```
~CAtlWinModule();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="extractcreatewnddata"></a>  CAtlWinModule::ExtractCreateWndData  
 Bu yöntem için bir işaretçi bir `_AtlCreateWndData` yapısı.  
  
```
void* ExtractCreateWndData();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür `_AtlCreateWndData` ile daha önce eklediğiniz yapısı [CAtlWinModule::AddCreateWndData](#addcreatewnddata), veya nesne yok yoksa NULL.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Modül sınıfları](../../atl/atl-module-classes.md)
