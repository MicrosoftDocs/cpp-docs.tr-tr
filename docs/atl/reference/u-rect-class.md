---
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
ms.openlocfilehash: 306092a00a1e119263f4563eea181d7d3ee2b4b2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326380"
---
# <a name="urect-class"></a>_U_RECT sınıfı

Bu bağımsız değişken bağdaştırıcı sınıfı ya da tanır `RECT` işaretçiler veya başvurular açısından işaretçileri uygulanan bir işleve geçirilecek.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class _U_RECT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[_U_RECT::_U_RECT](#_u_rect___u_rect)|Oluşturucu.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[_U_RECT::m_lpRect](#_u_rect__m_lprect)|İşaretçi bir `RECT`.|

## <a name="remarks"></a>Açıklamalar

İki oluşturucu aşırı yüklemeleri sınıfı tanımlar: bir kabul bir **RECT &** ve diğer bağımsız değişken kabul eden bir `LPRECT` bağımsız değişken. İlk Oluşturucu, sınıfın tek veri üyesi içinde başvuru bağımsız değişkeni adresini depolar [m_lpRect](#_u_rect__m_lprect). İşaretçi oluşturucusu için bağımsız değişken doğrudan dönüştürme depolanır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

##  <a name="_u_rect__m_lprect"></a>  _U_RECT::m_lpRect

Sınıf ya da kendi oluşturucular için genel geçirilen değeri içerir `LPRECT` veri üyesi.

```
LPRECT m_lpRect;
```

##  <a name="_u_rect___u_rect"></a>  _U_RECT::_U_RECT

Adresini başvuru bağımsız değişkeni sınıfın tek veri üyesi içinde depolanan [m_lpRect](#_u_rect__m_lprect).

```
_U_RECT(RECT& rc);
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*RC*<br/>
A `RECT` başvuru.

*lpRect*<br/>
A `RECT` işaretçi.

### <a name="remarks"></a>Açıklamalar

İşaretçi oluşturucusu için bağımsız değişken doğrudan dönüştürme depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
