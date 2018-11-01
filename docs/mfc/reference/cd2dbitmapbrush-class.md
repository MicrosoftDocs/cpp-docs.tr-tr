---
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
ms.openlocfilehash: 59c4e5f4e55947a4eab7a5258d8fe2b943bab3ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501575"
---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush sınıfı

ID2D1BitmapBrush için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DBitmapBrush : public CD2DBrush;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|Fazla Yüklendi. Dosyadan CD2DBitmapBrush bir nesne oluşturur.|
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|Yıkıcı. Bit eşlem fırça D2D nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush::Attach](#attach)|Var olan kaynak arabirimi nesnesine ekler|
|[CD2DBitmapBrush::Create](#create)|Bir CD2DBitmapBrush oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DBitmapBrush::Destroy](#destroy)|CD2DBitmapBrush nesnesini yok eder. (Geçersiz kılmaları [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DBitmapBrush::detach](#detach)|Kaynak arabirimi nesnesinden ayırır|
|[CD2DBitmapBrush::get](#get)|Döndürür ID2D1BitmapBrush arabirimi|
|[CD2DBitmapBrush::GetBitmap](#getbitmap)|Bu fırça boyamak için kullandığı bir bit eşlem kaynağı alır|
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|Tarafından Fırça, bit eşlem genişleten bu alanların yatay kutucukları yöntemi alır|
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|Tarafından Fırça, bit eşlem genişleten bu alanların dikey kutucukları yöntemi alır|
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|Fırça bit eşlem ölçeği ya da döndürüldüğünde kullanılan ilişkilendirme yöntemi alır|
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|Bu fırça boyamak için kullandığı bir bit eşlem kaynağı belirtir|
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|Yatay olarak genişletmek, bit eşlem bu alanların nasıl fırça kutucukları belirtir|
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|Dikey, bit eşlem genişleten bu alanların nasıl fırça kutucukları belirtir|
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|Fırça bit eşlem ölçeği ya da döndürüldüğünde kullanılan ilişkilendirme modunu belirtir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush::CommonInit](#commoninit)|Nesneyi başlatır|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush::operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|Döndürür ID2D1BitmapBrush arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmapBrush::m_pBitmap](#m_pbitmap)|CD2DBitmap nesnesine bir işaretçi depolar.|
|[CD2DBitmapBrush::m_pBitmapBrush](#m_pbitmapbrush)|ID2D1BitmapBrush nesneye bir işaretçi depolar.|
|[CD2DBitmapBrush::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|Fırça özellikleri bit eşlem.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DBitmapBrush`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="dtor"></a>  CD2DBitmapBrush:: ~ CD2DBitmapBrush

Yıkıcı. Bit eşlem fırça D2D nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DBitmapBrush();
```

##  <a name="attach"></a>  CD2DBitmapBrush::Attach

Var olan kaynak arabirimi nesnesine ekler

```
void Attach(ID2D1BitmapBrush* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz

##  <a name="cd2dbitmapbrush"></a>  CD2DBitmapBrush::CD2DBitmapBrush

CD2DBitmapBrush bir nesne oluşturur.

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
İşleme hedefi için bir işaretçi.

*pBitmapBrushProperties*<br/>
Genişletme modu ve bir bit eşlem fırça ilişkilendirme modu için bir işaretçi.

*pBrushProperties*<br/>
Fırça dönüşümü ve opaklık yönelik işaretçi.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

*uiResID*<br/>
Kaynak Kimliği kaynak sayısı.

*lpszType*<br/>
Kaynak türü içeren null ile sonlandırılmış bir dize işaretçisi.

*sizeDest*<br/>
Bit eşlem hedef boyutu.

*lpszImagePath*<br/>
Dosya adını içeren null ile sonlandırılmış bir dize işaretçisi.

##  <a name="commoninit"></a>  CD2DBitmapBrush::CommonInit

Nesneyi başlatır

```
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```

### <a name="parameters"></a>Parametreler

*pBitmapBrushProperties*<br/>
Bit eşlem Fırça özellikleri için bir işaretçi.

##  <a name="create"></a>  CD2DBitmapBrush::Create

Bir CD2DBitmapBrush oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="destroy"></a>  CD2DBitmapBrush::Destroy

CD2DBitmapBrush nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DBitmapBrush::detach

Kaynak arabirimi nesnesinden ayırır

```
ID2D1BitmapBrush* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirim işaretçisi.

##  <a name="get"></a>  CD2DBitmapBrush::get

Döndürür ID2D1BitmapBrush arabirimi

```
ID2D1BitmapBrush* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1BitmapBrush arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="getbitmap"></a>  CD2DBitmapBrush::GetBitmap

Bu fırça boyamak için kullandığı bir bit eşlem kaynağı alır

```
CD2DBitmap* GetBitmap();
```

### <a name="return-value"></a>Dönüş Değeri

CD2DBitmap nesneye veya nesnenin henüz başlatılmadı, NULL işaretçi.

##  <a name="getextendmodex"></a>  CD2DBitmapBrush::GetExtendModeX

Tarafından Fırça, bit eşlem genişleten bu alanların yatay kutucukları yöntemi alır

```
D2D1_EXTEND_MODE GetExtendModeX() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yatay olarak genişletmek, bit eşlem bu alanların nasıl fırça kutucukları belirten bir değeri

##  <a name="getextendmodey"></a>  CD2DBitmapBrush::GetExtendModeY

Tarafından Fırça, bit eşlem genişleten bu alanların dikey kutucukları yöntemi alır

```
D2D1_EXTEND_MODE GetExtendModeY() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dikey, bit eşlem genişleten bu alanların nasıl fırça kutucukları belirten bir değeri

##  <a name="getinterpolationmode"></a>  CD2DBitmapBrush::GetInterpolationMode

Fırça bit eşlem ölçeği ya da döndürüldüğünde kullanılan ilişkilendirme yöntemi alır

```
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Fırça bit eşlem ölçeği ya da döndürüldüğünde kullanılan ilişkilendirme yöntemi

##  <a name="m_pbitmap"></a>  CD2DBitmapBrush::m_pBitmap

CD2DBitmap nesnesine bir işaretçi depolar.

```
CD2DBitmap* m_pBitmap;
```

##  <a name="m_pbitmapbrush"></a>  CD2DBitmapBrush::m_pBitmapBrush

ID2D1BitmapBrush nesneye bir işaretçi depolar.

```
ID2D1BitmapBrush* m_pBitmapBrush;
```

##  <a name="m_pbitmapbrushproperties"></a>  CD2DBitmapBrush::m_pBitmapBrushProperties

Fırça özellikleri bit eşlem.

```
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;
```

##  <a name="operator_id2d1bitmapbrush_star"></a>  CD2DBitmapBrush::operator ID2D1BitmapBrush *

Döndürür ID2D1BitmapBrush arabirimi

```
operator ID2D1BitmapBrush*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1BitmapBrush arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="setbitmap"></a>  CD2DBitmapBrush::SetBitmap

Bu fırça boyamak için kullandığı bir bit eşlem kaynağı belirtir

```
void SetBitmap(CD2DBitmap* pBitmap);
```

### <a name="parameters"></a>Parametreler

*pBitmap*<br/>
Fırça tarafından kullanılan bit eşlem kaynağı

##  <a name="setextendmodex"></a>  CD2DBitmapBrush::SetExtendModeX

Yatay olarak genişletmek, bit eşlem bu alanların nasıl fırça kutucukları belirtir

```
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```

### <a name="parameters"></a>Parametreler

*extendModeX*<br/>
Yatay olarak genişletmek, bit eşlem bu alanların nasıl fırça kutucukları belirten bir değeri

##  <a name="setextendmodey"></a>  CD2DBitmapBrush::SetExtendModeY

Dikey, bit eşlem genişleten bu alanların nasıl fırça kutucukları belirtir

```
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```

### <a name="parameters"></a>Parametreler

*extendModeY*<br/>
Dikey, bit eşlem genişleten bu alanların nasıl fırça kutucukları belirten bir değeri

##  <a name="setinterpolationmode"></a>  CD2DBitmapBrush::SetInterpolationMode

Fırça bit eşlem ölçeği ya da döndürüldüğünde kullanılan ilişkilendirme modunu belirtir.

```
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```

### <a name="parameters"></a>Parametreler

*interpolationMode*<br/>
Fırça bit eşlem ölçeği ya da döndürüldüğünde kullanılan ilişkilendirme modu

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
