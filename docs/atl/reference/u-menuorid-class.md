---
title: _U_MENUorID Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
ms.openlocfilehash: 419c9e79178db12efe278838ec8630e04ac3c461
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325831"
---
# <a name="_u_menuorid-class"></a>_U_MENUorID Sınıfı

Bu sınıf için `CreateWindow` sarmalayıcıları sağlar ve. `CreateWindowEx`

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class _U_MENUorID
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[_U_MENUorID:_U_MENUorID](#_u_menuorid___u_menuorid)|Oluşturucu.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[_U_MENUorID:m_hMenu](#_u_menuorid__m_hmenu)|Menüye bir tutamaç.|

## <a name="remarks"></a>Açıklamalar

Bu bağımsız değişken bağdaştırıcı sınıfı, arayan kişi üzerinde açık bir döküm gerektirmeden, adlarının (UINTs) veya menü tutamaçlarının (HMENUs) bir işleve geçirilmesini sağlar.

Bu sınıf, windows API'ye, özellikle CreateWindow ve [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindoww) işlevlerine sarıcılar uygulamak için tasarlanmıştır ve her ikisi de menü tutamacı yerine alt pencere tanımlayıcısı (UINT) olabilecek bir HMENU bağımsız değişkenini kabul eder. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) Örneğin, bu sınıfı [CWindowImpl](cwindowimpl-class.md#create)için bir parametre olarak kullanmak görebilirsiniz::Oluştur .

Sınıf iki oluşturucu aşırı yükleri tanımlar: biri UINT bağımsız değişkenini, diğeri ise Bir HMENU bağımsız değişkenini kabul eder. UINT bağımsız değişkeni yalnızca oluşturucudaki bir HMENU'a ve sınıfın tek veri üyesinde depolanan sonuca [m_hMenu.](#_u_menuorid__m_hmenu) HMENU oluşturucuya bağımsız değişken doğrudan dönüştürme olmadan saklanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="_u_menuoridm_hmenu"></a><a name="_u_menuorid__m_hmenu"></a>_U_MENUorID:m_hMenu

Sınıf, ortak HMENU veri üyesi olarak oluşturucularından herhangi biri için geçirilen değeri tutar.

```
HMENU m_hMenu;
```

## <a name="_u_menuorid_u_menuorid"></a><a name="_u_menuorid___u_menuorid"></a>_U_MENUorID:_U_MENUorID

UINT bağımsız değişkeni yalnızca oluşturucudaki bir HMENU'a ve sınıfın tek veri üyesinde depolanan sonuca [m_hMenu.](#_u_menuorid__m_hmenu)

```
_U_MENUorID(UINT nID);
_U_MENUorID(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Bir çocuk pencere tanımlayıcısı.

*Hmenu*<br/>
Menü tutamacı.

### <a name="remarks"></a>Açıklamalar

HMENU oluşturucuya bağımsız değişken doğrudan dönüştürme olmadan saklanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
