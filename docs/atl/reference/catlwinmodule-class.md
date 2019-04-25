---
title: CAtlWinModule sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
ms.openlocfilehash: d0bc98fa48f84e67ab38106dea3fe22d5ad1757d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246830"
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

*pData*<br/>
İşaretçi `_AtlCreateWndData` yapısı başlatılamadı ve geçerli modülüne eklendi.

*pObject*<br/>
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

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
