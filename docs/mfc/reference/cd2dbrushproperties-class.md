---
title: CD2DBrushProperties sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
ms.openlocfilehash: 8fa93a6dda6b15b972ea399fc6522a8dec7c8de5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539028"
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties sınıfı

İçin sarmalayıcı `D2D1_BRUSH_PROPERTIES`.

## <a name="syntax"></a>Sözdizimi

```
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrushProperties::CD2DBrushProperties](#cd2dbrushproperties)|Fazla Yüklendi. Oluşturur bir `CD2D_BRUSH_PROPERTIES` yapısı|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrushProperties::CommonInit](#commoninit)|Nesneyi başlatır|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_BRUSH_PROPERTIES`

`CD2DBrushProperties`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="cd2dbrushproperties"></a>  CD2DBrushProperties::CD2DBrushProperties

CD2D_BRUSH_PROPERTIES yapısını oluşturur

```
CD2DBrushProperties();
CD2DBrushProperties(FLOAT _opacity);

CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,
    FLOAT _opacity = 1.);
```

### <a name="parameters"></a>Parametreler

*_opacity*<br/>
Fırça opaklığını temel. 1.0 varsayılan değerdir.

*_transform*<br/>
Dönüşüm fırçaya uygulamak için

##  <a name="commoninit"></a>  CD2DBrushProperties::CommonInit

Nesneyi başlatır

```
void CommonInit();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
