---
title: _U_RECT Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
ms.openlocfilehash: 8a4d5b2a770b3f0ecfe10be0fbad22a702aa0531
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325803"
---
# <a name="_u_rect-class"></a>_U_RECT Sınıfı

Bu bağımsız değişken bağdaştırıcı sı, işaretçilerin `RECT` veya başvuruların işaretçiler açısından uygulanan bir işleve geçirilmesine izin verir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class _U_RECT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[_U_RECT::_U_RECT](#_u_rect___u_rect)|Oluşturucu.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[_U_RECT:m_lpRect](#_u_rect__m_lprect)|İşaretçi `RECT`bir .|

## <a name="remarks"></a>Açıklamalar

Sınıf iki oluşturucu aşırı tanımlar: biri **RECT&** bağımsız değişkenini, diğeri ise bir `LPRECT` bağımsız değişkeni kabul eder. İlk oluşturucu, başvuru bağımsız değişkeninin adresini sınıfın tek veri [üyesinde m_lpRect.](#_u_rect__m_lprect) İşaretçi oluşturucuya bağımsız değişken dönüştürme olmadan doğrudan depolanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="_u_rectm_lprect"></a><a name="_u_rect__m_lprect"></a>_U_RECT:m_lpRect

Sınıf, ortak `LPRECT` veri üyesi olarak oluşturucularından herhangi biri için geçirilen değeri tutar.

```
LPRECT m_lpRect;
```

## <a name="_u_rect_u_rect"></a><a name="_u_rect___u_rect"></a>_U_RECT::_U_RECT

Başvuru bağımsız değişkeninin adresi sınıfın tek veri üyesinde [depolanır, m_lpRect.](#_u_rect__m_lprect)

```
_U_RECT(RECT& rc);
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*Rc*<br/>
Bir `RECT` referans.

*Lprect*<br/>
Bir `RECT` işaretçi.

### <a name="remarks"></a>Açıklamalar

İşaretçi oluşturucuya bağımsız değişken dönüştürme olmadan doğrudan depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
