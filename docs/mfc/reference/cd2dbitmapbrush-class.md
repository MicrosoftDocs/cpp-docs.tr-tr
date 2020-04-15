---
title: CD2DBitmapFırça Sınıfı
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
ms.openlocfilehash: e26202392bf4783598aec0dddfea514fce806a8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369307"
---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapFırça Sınıfı

ID2D1BitmapBrush için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DBitmapBrush : public CD2DBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|Fazla Yüklendi. Dosyadan bir CD2DBitmapBrush nesnesi oluşturur.|
|[CD2DBitmapBrush::~CD2DBitmapBrush](#dtor)|Yıkıcı. D2D bitmap fırça nesnesi yok edildiğinde çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush::Ekle](#attach)|Nesneye varolan kaynak arabirimi ataştırır|
|[CD2DBitmapBrush::Oluştur](#create)|BIR CD2DBitmapBrush oluşturur. [(CD2DResource geçersiz kılar::Oluştur](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DBitmapBrush::Destroy](#destroy)|BIR CD2DBitmapBrush nesnesini yok eder. [(Overrides CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DBitmapBrush::Detach](#detach)|Kaynak arabirimini nesneden ayırıyor|
|[CD2DBitmapBrush::Alın](#get)|ID2D1BitmapBrush arabirimini döndürür|
|[CD2DBitmapBrush::GetBitmap](#getbitmap)|Bu fırçanın boyamak için kullandığı bit eşlemi kaynağını alır|
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|Fırçanın bit haritasını geçen alanları yatay olarak kutulama yöntemini alır|
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|Fırçanın bit eşleminin ötesine uzanan alanları dikey olarak kutulama yöntemini alır|
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|Fırça bit eşlemi ölçeklendirildiğinde veya döndürüldüğünde kullanılan enterpolasyon yöntemini alır|
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|Bu fırçanın boyamak için kullandığı bit eşlemi kaynağını belirtir|
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|Fırçanın bit haritasını geçen alanları yatay olarak nasıl kutuladığını belirtir|
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|Fırçanın bit eşleminin ötesine uzanan alanları dikey olarak nasıl kutuladığını belirtir|
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|Fırça bit eşlemi ölçeklendiğinde veya döndürüldüğünde kullanılan enterpolasyon modunu belirtir|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush::CommonInit](#commoninit)|Nesneyi başharfe alar|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush::operatör ID2D1BitmapBrush*](#operator_id2d1bitmapbrush_star)|ID2D1BitmapBrush arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBitmapFırça::m_pBitmap](#m_pbitmap)|Bir işaretçiyi CD2DBitmap nesnesine depolar.|
|[CD2DBitmapFırça::m_pBitmapBrush](#m_pbitmapbrush)|Bir işaretçiyi ID2D1BitmapBrush nesnesine depolar.|
|[CD2DBitmapFırça::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|Bitmap fırça özellikleri.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CD2DKaynak](../../mfc/reference/cd2dresource-class.md)

[CD2DFırça](../../mfc/reference/cd2dbrush-class.md)

`CD2DBitmapBrush`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="dtor"></a>CD2DBitmapBrush::~CD2DBitmapBrush

Yıkıcı. D2D bitmap fırça nesnesi yok edildiğinde çağrılır.

```
virtual ~CD2DBitmapBrush();
```

## <a name="cd2dbitmapbrushattach"></a><a name="attach"></a>CD2DBitmapBrush::Ekle

Nesneye varolan kaynak arabirimi ataştırır

```
void Attach(ID2D1BitmapBrush* pResource);
```

### <a name="parameters"></a>Parametreler

*pKaynak*<br/>
Varolan kaynak arabirimi. NULL olamaz

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="cd2dbitmapbrush"></a>CD2DBitmapBrush::CD2DBitmapBrush

BIR CD2DBitmapBrush nesnesi oluşturur.

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
İşleme hedefine işaretçi.

*pBitmapBrushProperties*<br/>
Genişletme modlarına ve bitmap fırçasının enterpolasyon moduna işaretçi.

*pBrushProperties*<br/>
Bir fırçanın opaklığına ve dönüşümüne işaret eden bir işaretçi.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

*uiResID*<br/>
Kaynağın kaynak kimlik numarası.

*lpszType*<br/>
Kaynak türünü içeren null-sonlandırılan dize işaretçi.

*boyutDest*<br/>
Bit eşleninhedef boyutu.

*lpszImagePath*<br/>
Dosya nın adını içeren null-sonlandırılan dize işaretçi.

## <a name="cd2dbitmapbrushcommoninit"></a><a name="commoninit"></a>CD2DBitmapBrush::CommonInit

Nesneyi başharfe alar

```
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```

### <a name="parameters"></a>Parametreler

*pBitmapBrushProperties*<br/>
Bitmap fırça özellikleri için bir işaretçi.

## <a name="cd2dbitmapbrushcreate"></a><a name="create"></a>CD2DBitmapBrush::Oluştur

BIR CD2DBitmapBrush oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dbitmapbrushdestroy"></a><a name="destroy"></a>CD2DBitmapBrush::Destroy

BIR CD2DBitmapBrush nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dbitmapbrushdetach"></a><a name="detach"></a>CD2DBitmapBrush::Detach

Kaynak arabirimini nesneden ayırıyor

```
ID2D1BitmapBrush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirimine işaretçi.

## <a name="cd2dbitmapbrushget"></a><a name="get"></a>CD2DBitmapBrush::Alın

ID2D1BitmapBrush arabirimini döndürür

```
ID2D1BitmapBrush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1BitmapBrush arabirimine veya NULL'a işaretçi.

## <a name="cd2dbitmapbrushgetbitmap"></a><a name="getbitmap"></a>CD2DBitmapBrush::GetBitmap

Bu fırçanın boyamak için kullandığı bit eşlemi kaynağını alır

```
CD2DBitmap* GetBitmap();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse CD2DBitmap nesnesine veya NULL'a işaretçi.

## <a name="cd2dbitmapbrushgetextendmodex"></a><a name="getextendmodex"></a>CD2DBitmapBrush::GetExtendModeX

Fırçanın bit haritasını geçen alanları yatay olarak kutulama yöntemini alır

```
D2D1_EXTEND_MODE GetExtendModeX() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırçanın bit haritasını geçen alanları yatay olarak nasıl kutuladığını belirten bir değer

## <a name="cd2dbitmapbrushgetextendmodey"></a><a name="getextendmodey"></a>CD2DBitmapBrush::GetExtendModeY

Fırçanın bit eşleminin ötesine uzanan alanları dikey olarak kutulama yöntemini alır

```
D2D1_EXTEND_MODE GetExtendModeY() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırçanın bit haritasını geçen alanları dikey olarak nasıl kutuladığını belirten bir değer

## <a name="cd2dbitmapbrushgetinterpolationmode"></a><a name="getinterpolationmode"></a>CD2DBitmapBrush::GetInterpolationMode

Fırça bit eşlemi ölçeklendirildiğinde veya döndürüldüğünde kullanılan enterpolasyon yöntemini alır

```
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırça bit eşlemi ölçeklendirildiğinde veya döndürüldüğünde kullanılan enterpolasyon yöntemi

## <a name="cd2dbitmapbrushm_pbitmap"></a><a name="m_pbitmap"></a>CD2DBitmapFırça::m_pBitmap

Bir işaretçiyi CD2DBitmap nesnesine depolar.

```
CD2DBitmap* m_pBitmap;
```

## <a name="cd2dbitmapbrushm_pbitmapbrush"></a><a name="m_pbitmapbrush"></a>CD2DBitmapFırça::m_pBitmapBrush

Bir işaretçiyi ID2D1BitmapBrush nesnesine depolar.

```
ID2D1BitmapBrush* m_pBitmapBrush;
```

## <a name="cd2dbitmapbrushm_pbitmapbrushproperties"></a><a name="m_pbitmapbrushproperties"></a>CD2DBitmapFırça::m_pBitmapBrushProperties

Bitmap fırça özellikleri.

```
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;
```

## <a name="cd2dbitmapbrushoperator-id2d1bitmapbrush"></a><a name="operator_id2d1bitmapbrush_star"></a>CD2DBitmapBrush::operatör ID2D1BitmapBrush*

ID2D1BitmapBrush arabirimini döndürür

```
operator ID2D1BitmapBrush*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1BitmapBrush arabirimine veya NULL'a işaretçi.

## <a name="cd2dbitmapbrushsetbitmap"></a><a name="setbitmap"></a>CD2DBitmapBrush::SetBitmap

Bu fırçanın boyamak için kullandığı bit eşlemi kaynağını belirtir

```
void SetBitmap(CD2DBitmap* pBitmap);
```

### <a name="parameters"></a>Parametreler

*pBitmap*<br/>
Fırça tarafından kullanılan bitmap kaynağı

## <a name="cd2dbitmapbrushsetextendmodex"></a><a name="setextendmodex"></a>CD2DBitmapBrush::SetExtendModeX

Fırçanın bit haritasını geçen alanları yatay olarak nasıl kutuladığını belirtir

```
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```

### <a name="parameters"></a>Parametreler

*extendModeX*<br/>
Fırçanın bit haritasını geçen alanları yatay olarak nasıl kutuladığını belirten bir değer

## <a name="cd2dbitmapbrushsetextendmodey"></a><a name="setextendmodey"></a>CD2DBitmapBrush::SetExtendModeY

Fırçanın bit eşleminin ötesine uzanan alanları dikey olarak nasıl kutuladığını belirtir

```
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```

### <a name="parameters"></a>Parametreler

*extendModeY*<br/>
Fırçanın bit haritasını geçen alanları dikey olarak nasıl kutuladığını belirten bir değer

## <a name="cd2dbitmapbrushsetinterpolationmode"></a><a name="setinterpolationmode"></a>CD2DBitmapBrush::SetInterpolationMode

Fırça bit eşlemi ölçeklendiğinde veya döndürüldüğünde kullanılan enterpolasyon modunu belirtir

```
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```

### <a name="parameters"></a>Parametreler

*interpolasyonMode*<br/>
Fırça bit eşlemi ölçeklendirildiğinde veya döndürüldüğünde kullanılan enterpolasyon modu

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
