---
description: 'Hakkında daha fazla bilgi edinin: _U_RECT sınıfı'
title: _U_RECT sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
ms.openlocfilehash: b3720107d1b64f930b4c64dff269de041d9b928c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157613"
---
# <a name="_u_rect-class"></a>_U_RECT sınıfı

Bu bağımsız değişken bağdaştırıcı sınıfı `RECT` , işaretçiler bakımından uygulanan bir işleve işaretçiler veya başvurular geçirilmesini sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class _U_RECT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[_U_RECT:: _U_RECT](#_u_rect___u_rect)|Oluşturucu.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[_U_RECT:: m_lpRect](#_u_rect__m_lprect)|Bir işaretçisi `RECT` .|

## <a name="remarks"></a>Açıklamalar

Sınıf iki Oluşturucu aşırı yüklemesini tanımlar: biri **RECT&** bağımsız değişkenini kabul eder ve diğeri bir `LPRECT` bağımsız değişkeni kabul eder. İlk Oluşturucu, başvuru bağımsız değişkeninin adresini sınıfın tek veri üyesinde depolar, [m_lpRect](#_u_rect__m_lprect). İşaretçi oluşturucusunun bağımsız değişkeni dönüştürme olmadan doğrudan saklanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="_u_rectm_lprect"></a><a name="_u_rect__m_lprect"></a> _U_RECT:: m_lpRect

Sınıfı, bir ortak veri üyesi olarak oluşturucularından birine geçirilen değeri barındırır `LPRECT` .

```
LPRECT m_lpRect;
```

## <a name="_u_rect_u_rect"></a><a name="_u_rect___u_rect"></a> _U_RECT:: _U_RECT

Başvuru bağımsız değişkeninin adresi, sınıfın tek veri üyesinde, [m_lpRect](#_u_rect__m_lprect)depolanır.

```
_U_RECT(RECT& rc);
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*RC*<br/>
Bir `RECT` başvuru.

*lpRect*<br/>
Bir `RECT` işaretçi.

### <a name="remarks"></a>Açıklamalar

İşaretçi oluşturucusunun bağımsız değişkeni dönüştürme olmadan doğrudan saklanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
