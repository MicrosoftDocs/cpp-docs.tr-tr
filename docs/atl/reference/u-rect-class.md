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
ms.openlocfilehash: a4f3139498c9954026bd0247316eee1155f1b737
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642084"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
