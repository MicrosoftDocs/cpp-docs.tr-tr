---
title: CAtlWinModule Sınıfı
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
ms.openlocfilehash: 40385fd592563837546b483bb80978cde6a56555
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321267"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule Sınıfı

Bu sınıf, ATL pencere bileşenleri için destek sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlWinModülü::CAtlWinModülü](#catlwinmodule)|Oluşturucu.|
|[CAtlWinModülü::~CAtlWinModülü](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|Bir veri nesnesi ekler.|
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|Pencere modülü veri nesnesine bir işaretçi döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, pencereleme özellikleri gerektiren tüm ATL sınıfları için destek sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)

`CAtlWinModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="catlwinmoduleaddcreatewnddata"></a><a name="addcreatewnddata"></a>CAtlWinModule::AddCreateWndData

Bu yöntem bir `_AtlCreateWndData` yapı yılaştırır ve ekler.

```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>Parametreler

*Pdata*<br/>
Başharfe `_AtlCreateWndData` bürünecek ve geçerli modüle eklenecek yapıya işaretçi.

*Pobject*<br/>
Bir nesneye işaretçi **bu** işaretçidir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) bir yapıyı ortaya çıkaran [AtlWinModuleAddCreateWndData'yı](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) çağırır. Bu yapı, pencere yordamlarında sınıf örneğini elde etmek için kullanılan **bu** işaretçiyi depolar.

## <a name="catlwinmodulecatlwinmodule"></a><a name="catlwinmodule"></a>CAtlWinModülü::CAtlWinModülü

Oluşturucu.

```
CAtlWinModule();
```

### <a name="remarks"></a>Açıklamalar

Başlatma başarısız olursa, **EXCEPTION_NONCONTINUABLE** bir özel durum yükseltilir.

## <a name="catlwinmodulecatlwinmodule"></a><a name="dtor"></a>CAtlWinModülü::~CAtlWinModülü

Yıkıcı.

```
~CAtlWinModule();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest sağlar.

## <a name="catlwinmoduleextractcreatewnddata"></a><a name="extractcreatewnddata"></a>CAtlWinModule::ExtractCreateWndData

Bu yöntem bir `_AtlCreateWndData` yapıya bir işaretçi döndürür.

```
void* ExtractCreateWndData();
```

### <a name="return-value"></a>Dönüş Değeri

`_AtlCreateWndData` [CAtlWinModule::AddCreateWndData](#addcreatewnddata)veya nesne yoksa NULL ile daha önce eklenen yapıya bir işaretçi döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[Modül Sınıfları](../../atl/atl-module-classes.md)
