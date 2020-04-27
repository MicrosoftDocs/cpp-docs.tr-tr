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
ms.openlocfilehash: 5cdf13ebbb982ad8184a52dcf1a3e30d71e4e5b0
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167714"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule Sınıfı

Bu sınıf, ATL Pencereleme bileşenleri için destek sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlWinModule:: CAtlWinModule](#catlwinmodule)|Oluşturucu.|
|[CAtlWinModule:: ~ CAtlWinModule](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlWinModule:: AddCreateWndData](#addcreatewnddata)|Veri nesnesi ekler.|
|[CAtlWinModule:: ExtractCreateWndData](#extractcreatewnddata)|Pencere modülü veri nesnesine bir işaretçi döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, Pencereleme özellikleri gerektiren tüm ATL sınıfları için destek sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)

`CAtlWinModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="catlwinmoduleaddcreatewnddata"></a><a name="addcreatewnddata"></a>CAtlWinModule:: AddCreateWndData

Bu yöntem başlatır ve bir `_AtlCreateWndData` yapı ekler.

```cpp
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>Parametreler

*pData*<br/>
Başlatılacak ve geçerli `_AtlCreateWndData` modüle eklenecek yapıya yönelik işaretçi.

*Nesnesini*<br/>
Nesnenin **Bu** işaretçisine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısını başlatan [AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) öğesini çağırır. Bu yapı bu işaretçiyi depolayacak ve **Bu** işaretçi, sınıf örneğini pencere yordamlarında elde etmek için kullanılır.

## <a name="catlwinmodulecatlwinmodule"></a><a name="catlwinmodule"></a>CAtlWinModule:: CAtlWinModule

Oluşturucu.

```cpp
CAtlWinModule();
```

### <a name="remarks"></a>Açıklamalar

Başlatma başarısız olursa, bir **EXCEPTION_NONCONTINUABLE** özel durumu oluşturulur.

## <a name="catlwinmodulecatlwinmodule"></a><a name="dtor"></a>CAtlWinModule:: ~ CAtlWinModule

Yok edicisi.

```cpp
~CAtlWinModule();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

## <a name="catlwinmoduleextractcreatewnddata"></a><a name="extractcreatewnddata"></a>CAtlWinModule:: ExtractCreateWndData

Bu yöntem bir `_AtlCreateWndData` yapıya bir işaretçi döndürür.

```cpp
void* ExtractCreateWndData();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce `_AtlCreateWndData` [CAtlWinModule:: AddCreateWndData](#addcreatewnddata)ile eklenmiş yapıya bir işaretçi döndürür veya kullanılabilir nesne yoksa null değeri döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
