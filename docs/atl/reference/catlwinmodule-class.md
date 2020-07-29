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
ms.openlocfilehash: 04dc7e5b8c0c5dd21567f23395b4bafd4ae839dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229993"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule sınıfı

Bu sınıf, ATL Pencereleme bileşenleri için destek sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlWinModule:: CAtlWinModule](#catlwinmodule)|Oluşturucu.|
|[CAtlWinModule:: ~ CAtlWinModule](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
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

Bu yöntem başlatır ve bir `_AtlCreateWndData` Yapı ekler.

```cpp
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>Parametreler

*pData*<br/>
`_AtlCreateWndData`Başlatılacak ve geçerli modüle eklenecek yapıya yönelik işaretçi.

*Nesnesini*<br/>
Nesne **`this`** işaretçisinin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısını başlatan [AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) öğesini çağırır. Bu yapı **`this`** , sınıf örneğini bir pencere yordamlarında elde etmek için kullanılan işaretçiyi depolayacaktır.

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

Bu yöntem bir yapıya bir işaretçi döndürür `_AtlCreateWndData` .

```cpp
void* ExtractCreateWndData();
```

### <a name="return-value"></a>Dönüş Değeri

`_AtlCreateWndData`Daha önce [CAtlWinModule:: AddCreateWndData](#addcreatewnddata)ile eklenmiş yapıya bir işaretçi döndürür veya KULLANILABILIR nesne yoksa null değeri döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
