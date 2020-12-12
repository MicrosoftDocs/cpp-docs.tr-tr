---
description: 'Daha fazla bilgi edinin: CD2DBrushProperties Class'
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
ms.openlocfilehash: d16d08041b5096c8a5ad188201c6a06e21681849
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227565"
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties sınıfı

İçin bir sarmalayıcı `D2D1_BRUSH_PROPERTIES` .

## <a name="syntax"></a>Syntax

```
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrushProperties::CD2DBrushProperties](#cd2dbrushproperties)|Fazla Yüklendi. Bir `CD2D_BRUSH_PROPERTIES` yapı oluşturur|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBrushProperties:: CommonInit](#commoninit)|Nesneyi başlatır|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_BRUSH_PROPERTIES`

`CD2DBrushProperties`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dbrushpropertiescd2dbrushproperties"></a><a name="cd2dbrushproperties"></a> CD2DBrushProperties::CD2DBrushProperties

CD2D_BRUSH_PROPERTIES yapısı oluşturur

```
CD2DBrushProperties();
CD2DBrushProperties(FLOAT _opacity);

CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,
    FLOAT _opacity = 1.);
```

### <a name="parameters"></a>Parametreler

*_opacity*<br/>
Fırçanın temel geçirgenliği. Varsayılan değer 1,0 ' dir.

*_transform*<br/>
Fırçaya uygulanacak dönüşüm

## <a name="cd2dbrushpropertiescommoninit"></a><a name="commoninit"></a> CD2DBrushProperties:: CommonInit

Nesneyi başlatır

```cpp
void CommonInit();
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
