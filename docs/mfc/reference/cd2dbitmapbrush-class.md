---
description: 'Daha fazla bilgi edinin: CD2DBitmapBrush Class'
title: CD2DBitmapBrush sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::Attach
- AFXRENDERTARGET/CD2DBitmapBrush::Create
- AFXRENDERTARGET/CD2DBitmapBrush::Destroy
- AFXRENDERTARGET/CD2DBitmapBrush::Detach
- AFXRENDERTARGET/CD2DBitmapBrush::Get
- AFXRENDERTARGET/CD2DBitmapBrush::GetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::GetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::SetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::SetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::CommonInit
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrushProperties
helpviewer_keywords:
- CD2DBitmapBrush [MFC], CD2DBitmapBrush
- CD2DBitmapBrush [MFC], Attach
- CD2DBitmapBrush [MFC], Create
- CD2DBitmapBrush [MFC], Destroy
- CD2DBitmapBrush [MFC], Detach
- CD2DBitmapBrush [MFC], Get
- CD2DBitmapBrush [MFC], GetBitmap
- CD2DBitmapBrush [MFC], GetExtendModeX
- CD2DBitmapBrush [MFC], GetExtendModeY
- CD2DBitmapBrush [MFC], GetInterpolationMode
- CD2DBitmapBrush [MFC], SetBitmap
- CD2DBitmapBrush [MFC], SetExtendModeX
- CD2DBitmapBrush [MFC], SetExtendModeY
- CD2DBitmapBrush [MFC], SetInterpolationMode
- CD2DBitmapBrush [MFC], CommonInit
- CD2DBitmapBrush [MFC], m_pBitmap
- CD2DBitmapBrush [MFC], m_pBitmapBrush
- CD2DBitmapBrush [MFC], m_pBitmapBrushProperties
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
ms.openlocfilehash: a9d4c1955b1318ecb273482cd49025090bf97d3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227591"
---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush sınıfı

ID2D1BitmapBrush için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DBitmapBrush : public CD2DBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|Fazla Yüklendi. Dosyadan bir CD2DBitmapBrush nesnesi oluşturur.|
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|Yok edicisi. Bir D2D bit eşlem fırçası nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush:: Attach](#attach)|Varolan kaynak arabirimini nesneye iliştirir|
|[CD2DBitmapBrush:: Create](#create)|Bir CD2DBitmapBrush oluşturur. (Geçersiz kılmalar [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DBitmapBrush::D estroy](#destroy)|Bir CD2DBitmapBrush nesnesini yok eder. (Geçersiz kılmalar [CD2DBrush::D estroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DBitmapBrush::D etach](#detach)|Nesneden kaynak arabirimini ayırır|
|[CD2DBitmapBrush:: Get](#get)|ID2D1BitmapBrush arabirimini döndürür|
|[CD2DBitmapBrush:: GetBitmap](#getbitmap)|Bu fırçanın boyamak için kullandığı bit eşlem kaynağını alır|
|[CD2DBitmapBrush:: Getbıdmodex](#getextendmodex)|Fırçanın, bit eşlemden daha fazla genişleyen olan bu alanlara yatay olarak döşeme yaptığı yöntemi alır|
|[CD2DBitmapBrush:: Gebir Dmodey](#getextendmodey)|Fırçanın, bit eşlemden daha fazla genişleyen olan bu bölgeleri dikey olarak döşeme yöntemini alır|
|[CD2DBitmapBrush:: Getınterlationmode](#getinterpolationmode)|Fırça bit eşlemi ölçeklendirildiğinde veya döndürüldüğünde kullanılan enterpolasyon yöntemini alır|
|[CD2DBitmapBrush:: SetBit eşlem](#setbitmap)|Bu fırçanın boyamak için kullandığı bit eşlem kaynağını belirtir|
|[CD2DBitmapBrush:: Setbıdmodex](#setextendmodex)|Fırçanın, bit eşlemden daha fazla genişleyen bu alanlara yatay olarak nasıl döşeme gösterdiğini belirtir|
|[CD2DBitmapBrush:: Sedtu Dmodey](#setextendmodey)|Fırçanın, bit eşlemden daha fazla genişleyen olan bu alanların dikey olarak nasıl taşmadığını belirtir|
|[CD2DBitmapBrush:: Setınterlationmode](#setinterpolationmode)|Fırça bit eşlemi ölçeklendirildiğinde veya döndürüldüğünde kullanılan enterpolasyon modunu belirtir|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush:: CommonInit](#commoninit)|Nesneyi başlatır|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush:: operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|ID2D1BitmapBrush arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush:: m_pBitmap](#m_pbitmap)|Bir CD2DBitmap nesnesine bir işaretçi depolar.|
|[CD2DBitmapBrush:: m_pBitmapBrush](#m_pbitmapbrush)|Bir ID2D1BitmapBrush nesnesine bir işaretçi depolar.|
|[CD2DBitmapBrush:: m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|Bit eşlem fırçası özellikleri.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DBitmapBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="dtor"></a> CD2DBitmapBrush:: ~ CD2DBitmapBrush

Yok edicisi. Bir D2D bit eşlem fırçası nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DBitmapBrush();
```

## <a name="cd2dbitmapbrushattach"></a><a name="attach"></a> CD2DBitmapBrush:: Attach

Varolan kaynak arabirimini nesneye iliştirir

```cpp
void Attach(ID2D1BitmapBrush* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="cd2dbitmapbrush"></a> CD2DBitmapBrush::CD2DBitmapBrush

Bir CD2DBitmapBrush nesnesi oluşturur.

```
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszImagePath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi işaretçisi.

*Pbitmapbrühproperties*<br/>
Bit eşlem fırçasının uzatma modlarına ve ilişkilendirme moduna yönelik bir işaretçi.

*Pbrühproperties*<br/>
Fırçaya yönelik opaklık ve dönüştürme işaretçisi.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

*Uırestıd*<br/>
Kaynağın kaynak KIMLIĞI numarası.

*lpszType*<br/>
Kaynak türünü içeren, null ile sonlandırılmış bir dize işaretçisi.

*sizeDest*<br/>
Bit eşlemin hedef boyutu.

*lpszImagePath*<br/>
Dosya adını içeren, null ile sonlandırılmış bir dize işaretçisi.

## <a name="cd2dbitmapbrushcommoninit"></a><a name="commoninit"></a> CD2DBitmapBrush:: CommonInit

Nesneyi başlatır

```cpp
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```

### <a name="parameters"></a>Parametreler

*Pbitmapbrühproperties*<br/>
Bit eşlem fırçası özelliklerine yönelik bir işaretçi.

## <a name="cd2dbitmapbrushcreate"></a><a name="create"></a> CD2DBitmapBrush:: Create

Bir CD2DBitmapBrush oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dbitmapbrushdestroy"></a><a name="destroy"></a> CD2DBitmapBrush::D estroy

Bir CD2DBitmapBrush nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dbitmapbrushdetach"></a><a name="detach"></a> CD2DBitmapBrush::D etach

Nesneden kaynak arabirimini ayırır

```
ID2D1BitmapBrush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılan kaynak arabirimine yönelik işaretçi.

## <a name="cd2dbitmapbrushget"></a><a name="get"></a> CD2DBitmapBrush:: Get

ID2D1BitmapBrush arabirimini döndürür

```
ID2D1BitmapBrush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1BitmapBrush arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dbitmapbrushgetbitmap"></a><a name="getbitmap"></a> CD2DBitmapBrush:: GetBitmap

Bu fırçanın boyamak için kullandığı bit eşlem kaynağını alır

```
CD2DBitmap* GetBitmap();
```

### <a name="return-value"></a>Dönüş Değeri

CD2DBitmap nesnesine işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dbitmapbrushgetextendmodex"></a><a name="getextendmodex"></a> CD2DBitmapBrush:: Getbıdmodex

Fırçanın, bit eşlemden daha fazla genişleyen olan bu alanlara yatay olarak döşeme yaptığı yöntemi alır

```
D2D1_EXTEND_MODE GetExtendModeX() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırçanın, bit eşlemden daha fazla genişleyen bu alanlara yatay olarak nasıl döşeme gösterdiğini belirten bir değer

## <a name="cd2dbitmapbrushgetextendmodey"></a><a name="getextendmodey"></a> CD2DBitmapBrush:: Gebir Dmodey

Fırçanın, bit eşlemden daha fazla genişleyen olan bu bölgeleri dikey olarak döşeme yöntemini alır

```
D2D1_EXTEND_MODE GetExtendModeY() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırçanın, bit eşlemden daha fazla genişleyen bu alanlara dikey olarak nasıl döşeme gösterdiğini belirten bir değer

## <a name="cd2dbitmapbrushgetinterpolationmode"></a><a name="getinterpolationmode"></a> CD2DBitmapBrush:: Getınterlationmode

Fırça bit eşlemi ölçeklendirildiğinde veya döndürüldüğünde kullanılan enterpolasyon yöntemini alır

```
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırça bit eşlemi ölçeklendirildiğinde veya döndürüldüğünde kullanılan enterpolasyon yöntemi

## <a name="cd2dbitmapbrushm_pbitmap"></a><a name="m_pbitmap"></a> CD2DBitmapBrush:: m_pBitmap

Bir CD2DBitmap nesnesine bir işaretçi depolar.

```
CD2DBitmap* m_pBitmap;
```

## <a name="cd2dbitmapbrushm_pbitmapbrush"></a><a name="m_pbitmapbrush"></a> CD2DBitmapBrush:: m_pBitmapBrush

Bir ID2D1BitmapBrush nesnesine bir işaretçi depolar.

```
ID2D1BitmapBrush* m_pBitmapBrush;
```

## <a name="cd2dbitmapbrushm_pbitmapbrushproperties"></a><a name="m_pbitmapbrushproperties"></a> CD2DBitmapBrush:: m_pBitmapBrushProperties

Bit eşlem fırçası özellikleri.

```
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;
```

## <a name="cd2dbitmapbrushoperator-id2d1bitmapbrush"></a><a name="operator_id2d1bitmapbrush_star"></a> CD2DBitmapBrush:: operator ID2D1BitmapBrush *

ID2D1BitmapBrush arabirimini döndürür

```
operator ID2D1BitmapBrush*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1BitmapBrush arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dbitmapbrushsetbitmap"></a><a name="setbitmap"></a> CD2DBitmapBrush:: SetBit eşlem

Bu fırçanın boyamak için kullandığı bit eşlem kaynağını belirtir

```cpp
void SetBitmap(CD2DBitmap* pBitmap);
```

### <a name="parameters"></a>Parametreler

*Pbımap*<br/>
Fırça tarafından kullanılan bit eşlem kaynağı

## <a name="cd2dbitmapbrushsetextendmodex"></a><a name="setextendmodex"></a> CD2DBitmapBrush:: Setbıdmodex

Fırçanın, bit eşlemden daha fazla genişleyen bu alanlara yatay olarak nasıl döşeme gösterdiğini belirtir

```cpp
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```

### <a name="parameters"></a>Parametreler

*extendModeX*<br/>
Fırçanın, bit eşlemden daha fazla genişleyen bu alanlara yatay olarak nasıl döşeme gösterdiğini belirten bir değer

## <a name="cd2dbitmapbrushsetextendmodey"></a><a name="setextendmodey"></a> CD2DBitmapBrush:: Sedtu Dmodey

Fırçanın, bit eşlemden daha fazla genişleyen olan bu alanların dikey olarak nasıl taşmadığını belirtir

```cpp
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```

### <a name="parameters"></a>Parametreler

*extendModeY*<br/>
Fırçanın, bit eşlemden daha fazla genişleyen bu alanlara dikey olarak nasıl döşeme gösterdiğini belirten bir değer

## <a name="cd2dbitmapbrushsetinterpolationmode"></a><a name="setinterpolationmode"></a> CD2DBitmapBrush:: Setınterlationmode

Fırça bit eşlemi ölçeklendirildiğinde veya döndürüldüğünde kullanılan enterpolasyon modunu belirtir

```cpp
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```

### <a name="parameters"></a>Parametreler

*Enterpolationmode*<br/>
Fırça bit eşlemi ölçeklendirildiğinde veya döndürüldüğünde kullanılan enterpolasyon modu

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
