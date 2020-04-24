---
title: CD2DBrushProperties Sınıfı
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
ms.openlocfilehash: 2db720fd09c62f8b86baecea9229d946f3892333
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754188"
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties Sınıfı

Bir sarmalayıcı. `D2D1_BRUSH_PROPERTIES`

## <a name="syntax"></a>Sözdizimi

```
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBrushÖzellikleri::CD2DBrushProperties](#cd2dbrushproperties)|Fazla Yüklendi. Bir `CD2D_BRUSH_PROPERTIES` yapı oluşturur|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBrushProperties::CommonInit](#commoninit)|Nesneyi başharfe alar|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`D2D1_BRUSH_PROPERTIES`

`CD2DBrushProperties`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dbrushpropertiescd2dbrushproperties"></a><a name="cd2dbrushproperties"></a>CD2DBrushÖzellikleri::CD2DBrushProperties

CD2D_BRUSH_PROPERTIES bir yapı oluşturur

```
CD2DBrushProperties();
CD2DBrushProperties(FLOAT _opacity);

CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,
    FLOAT _opacity = 1.);
```

### <a name="parameters"></a>Parametreler

*_opacity*<br/>
Fırçanın taban opaklığı. Varsayılan değer 1.0'dır.

*_transform*<br/>
Fırçaya uygulanacak dönüşüm

## <a name="cd2dbrushpropertiescommoninit"></a><a name="commoninit"></a>CD2DBrushProperties::CommonInit

Nesneyi başharfe alar

```cpp
void CommonInit();
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
