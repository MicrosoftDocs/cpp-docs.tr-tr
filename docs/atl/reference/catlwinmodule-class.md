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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78857357"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule sınıfı

Bu sınıf, ATL Pencereleme bileşenleri için destek sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CAtlWinModule:: CAtlWinModule](#catlwinmodule)|Oluşturucu.|
|[CAtlWinModule:: ~ CAtlWinModule](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
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

##  <a name="addcreatewnddata"></a>CAtlWinModule:: AddCreateWndData

Bu yöntem bir `_AtlCreateWndData` yapısını başlatır ve ekler.

```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>Parametreler

*pData*<br/>
Başlatılacak ve geçerli modüle eklenecek `_AtlCreateWndData` yapısına yönelik işaretçi.

*Nesnesini*<br/>
Nesnenin **Bu** işaretçisine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) yapısını başlatan [AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata) öğesini çağırır. Bu yapı bu işaretçiyi depolayacak ve **Bu** işaretçi, sınıf örneğini pencere yordamlarında elde etmek için kullanılır.

##  <a name="catlwinmodule"></a>CAtlWinModule:: CAtlWinModule

Oluşturucu.

```
CAtlWinModule();
```

### <a name="remarks"></a>Açıklamalar

Başlatma başarısız olursa, bir **EXCEPTION_NONCONTINUABLE** özel durumu oluşturulur.

##  <a name="dtor"></a>CAtlWinModule:: ~ CAtlWinModule

Yok edicisi.

```
~CAtlWinModule();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="extractcreatewnddata"></a>CAtlWinModule:: ExtractCreateWndData

Bu yöntem `_AtlCreateWndData` yapısına bir işaretçi döndürür.

```
void* ExtractCreateWndData();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce [CAtlWinModule:: AddCreateWndData](#addcreatewnddata)ile eklenen `_AtlCreateWndData` yapısına yönelik bir işaretçi döndürür veya kullanılabilir nesne yoksa null değeri döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
