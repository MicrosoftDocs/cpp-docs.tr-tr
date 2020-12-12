---
description: 'Daha fazla bilgi edinin: CD2DBitmap Class'
title: CD2DBitmap sınıfı
ms.date: 11/04/2016
f1_keywords:
- CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::Attach
- AFXRENDERTARGET/CD2DBitmap::CopyFromBitmap
- AFXRENDERTARGET/CD2DBitmap::CopyFromMemory
- AFXRENDERTARGET/CD2DBitmap::CopyFromRenderTarget
- AFXRENDERTARGET/CD2DBitmap::Create
- AFXRENDERTARGET/CD2DBitmap::Destroy
- AFXRENDERTARGET/CD2DBitmap::Detach
- AFXRENDERTARGET/CD2DBitmap::Get
- AFXRENDERTARGET/CD2DBitmap::GetDPI
- AFXRENDERTARGET/CD2DBitmap::GetPixelFormat
- AFXRENDERTARGET/CD2DBitmap::GetPixelSize
- AFXRENDERTARGET/CD2DBitmap::GetSize
- AFXRENDERTARGET/CD2DBitmap::IsValid
- AFXRENDERTARGET/CD2DBitmap::CommonInit
- AFXRENDERTARGET/CD2DBitmap::m_bAutoDestroyHBMP
- AFXRENDERTARGET/CD2DBitmap::m_hBmpSrc
- AFXRENDERTARGET/CD2DBitmap::m_lpszType
- AFXRENDERTARGET/CD2DBitmap::m_pBitmap
- AFXRENDERTARGET/CD2DBitmap::m_sizeDest
- AFXRENDERTARGET/CD2DBitmap::m_strPath
- AFXRENDERTARGET/CD2DBitmap::m_uiResID
helpviewer_keywords:
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], Attach
- CD2DBitmap [MFC], CopyFromBitmap
- CD2DBitmap [MFC], CopyFromMemory
- CD2DBitmap [MFC], CopyFromRenderTarget
- CD2DBitmap [MFC], Create
- CD2DBitmap [MFC], Destroy
- CD2DBitmap [MFC], Detach
- CD2DBitmap [MFC], Get
- CD2DBitmap [MFC], GetDPI
- CD2DBitmap [MFC], GetPixelFormat
- CD2DBitmap [MFC], GetPixelSize
- CD2DBitmap [MFC], GetSize
- CD2DBitmap [MFC], IsValid
- CD2DBitmap [MFC], CommonInit
- CD2DBitmap [MFC], m_bAutoDestroyHBMP
- CD2DBitmap [MFC], m_hBmpSrc
- CD2DBitmap [MFC], m_lpszType
- CD2DBitmap [MFC], m_pBitmap
- CD2DBitmap [MFC], m_sizeDest
- CD2DBitmap [MFC], m_strPath
- CD2DBitmap [MFC], m_uiResID
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
ms.openlocfilehash: ab023caa92683b24098db1a03d081922e3dfd48b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227656"
---
# <a name="cd2dbitmap-class"></a>CD2DBitmap sınıfı

ID2D1Bitmap için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DBitmap : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Fazla Yüklendi. HBITMAP 'ten bir CD2DBitmap nesnesi oluşturur.|
|[CD2DBitmap:: ~ CD2DBitmap](#_dtorcd2dbitmap)|Yok edicisi. Bir D2D bit eşlem nesnesi yok edildiğinde çağırılır.|

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Fazla Yüklendi. Bir CD2DBitmap nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap:: Attach](#attach)|Varolan kaynak arabirimini nesneye iliştirir|
|[CD2DBitmap:: CopyFromBitmap](#copyfrombitmap)|Belirtilen alt Bitmapten belirtilen bölgeyi geçerli bit eşleme kopyalar|
|[CD2DBitmap:: CopyFromMemory](#copyfrommemory)|Belirtilen bölgeyi bellekten geçerli bit eşlem 'e kopyalar|
|[CD2DBitmap:: CopyFromRenderTarget](#copyfromrendertarget)|Belirtilen oluşturma hedefinden belirtilen bölgeyi geçerli bit eşlem 'e kopyalar|
|[CD2DBitmap:: Create](#create)|Bir CD2DBitmap oluşturur. (Geçersiz kılmalar [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DBitmap::D estroy](#destroy)|Bir CD2DBitmap nesnesini yok eder. (Geçersiz kılmalar [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DBitmap::D etach](#detach)|Nesneden kaynak arabirimini ayırır|
|[CD2DBitmap:: Get](#get)|ID2D1Bitmap arabirimini döndürür|
|[CD2DBitmap:: GetDPI](#getdpi)|Bit eşlemin inç başına nokta (DPI) sayısını döndürür|
|[CD2DBitmap:: GetPixelFormat](#getpixelformat)|Bit eşlemin piksel biçimini ve Alfa modunu alır|
|[CD2DBitmap:: GetPixelSize](#getpixelsize)|Bit eşlemin cihaz bağımlı birimlerinde (piksel) boyutunu döndürür|
|[CD2DBitmap:: GetSize](#getsize)|Bit eşlemin cihazdan bağımsız piksel (DIP) cinsinden boyutu döndürür|
|[CD2DBitmap:: IsValid](#isvalid)|Kaynak geçerliliğini denetler (geçersiz kılmalar [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap:: CommonInit](#commoninit)|Nesneyi başlatır|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap:: operator ID2D1Bitmap *](#operator_id2d1bitmap_star)|ID2D1Bitmap arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap:: m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|M_hBmpSrc yok edilmesi gerekiyorsa TRUE; Aksi halde yanlış.|
|[CD2DBitmap:: m_hBmpSrc](#m_hbmpsrc)|Kaynak bit eşlem tanıtıcısı.|
|[CD2DBitmap:: m_lpszType](#m_lpsztype)|Kaynak türü.|
|[CD2DBitmap:: m_pBitmap](#m_pbitmap)|Bir ID2D1Bitmap nesnesine bir işaretçi depolar.|
|[CD2DBitmap:: m_sizeDest](#m_sizedest)|Bit eşlem hedef boyutu.|
|[CD2DBitmap:: m_strPath](#m_strpath)|Botmap dosya yolu.|
|[CD2DBitmap:: m_uiResID](#m_uiresid)|Bit eşlem kaynak KIMLIĞI.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DBitmap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dbitmapcd2dbitmap"></a><a name="_dtorcd2dbitmap"></a> CD2DBitmap:: ~ CD2DBitmap

Yok edicisi. Bir D2D bit eşlem nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DBitmap();
```

## <a name="cd2dbitmapattach"></a><a name="attach"></a> CD2DBitmap:: Attach

Varolan kaynak arabirimini nesneye ekler.

```cpp
void Attach(ID2D1Bitmap* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz.

## <a name="cd2dbitmapcd2dbitmap"></a><a name="cd2dbitmap"></a> CD2DBitmap::CD2DBitmap

Kaynağından bir CD2DBitmap nesnesi oluşturur.

```
CD2DBitmap(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszPath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    HBITMAP hbmpSrc,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi işaretçisi.

*Uırestıd*<br/>
Kaynağın kaynak KIMLIĞI numarası.

*lpszType*<br/>
Kaynak türünü içeren, null ile sonlandırılmış bir dize işaretçisi.

*sizeDest*<br/>
Bit eşlemin hedef boyutu.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

*lpszPath*<br/>
Dosya adını içeren, null ile sonlandırılmış bir dize işaretçisi.

*hbmpSrc*<br/>
Bit eşlemin tanıtıcısı.

## <a name="cd2dbitmapcommoninit"></a><a name="commoninit"></a> CD2DBitmap:: CommonInit

Nesnesini başlatır.

```cpp
void CommonInit();
```

## <a name="cd2dbitmapcopyfrombitmap"></a><a name="copyfrombitmap"></a> CD2DBitmap:: CopyFromBitmap

Belirtilen alt Bitmapten belirtilen bölgeyi geçerli bit eşleme kopyalar.

```
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>Parametreler

*Pbımap*<br/>
Kopyalanacak bit eşlem.

*Hedef noktası*<br/>
Geçerli bit eşlemde, srcRect tarafından belirtilen bölgenin kopyalandığı alanın sol üst köşesi kopyalanır.

*srcRect*<br/>
Kopyalanacak bit eşlemin alanı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dbitmapcopyfrommemory"></a><a name="copyfrommemory"></a> CD2DBitmap:: CopyFromMemory

Belirtilen bölgeyi bellekten geçerli bit eşlem 'e kopyalar.

```
HRESULT CopyFromMemory(
    const void* srcData,
    UINT32 pitch,
    const CD2DRectU* destRect = NULL);
```

### <a name="parameters"></a>Parametreler

*srcData*<br/>
Kopyalanacak veriler.

*perde*<br/>
SrcData 'da depolanan kaynak bit eşlemin ilerlemesiyle veya bir sıklığı. Bu adım, bir scanline 'in bayt sayısıdır (bellekteki bir piksel satırı). Bu adım şu formülden hesaplanabilir: \* piksel başına piksel genişliği + bellek doldurma.

*destRect*<br/>
Geçerli bit eşlemde, srcRect tarafından belirtilen bölgenin kopyalandığı alanın sol üst köşesi kopyalanır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dbitmapcopyfromrendertarget"></a><a name="copyfromrendertarget"></a> CD2DBitmap:: CopyFromRenderTarget

Belirtilen oluşturma hedefinden belirtilen bölgeyi geçerli bit eşlem 'e kopyalar.

```
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
Kopyalanacak bölgeyi içeren işleme hedefi.

*Hedef noktası*<br/>
Geçerli bit eşlemde, srcRect tarafından belirtilen bölgenin kopyalandığı alanın sol üst köşesi kopyalanır.

*srcRect*<br/>
Kopyalanacak renderTarget alanı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dbitmapcreate"></a><a name="create"></a> CD2DBitmap:: Create

Bir CD2DBitmap oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dbitmapdestroy"></a><a name="destroy"></a> CD2DBitmap::D estroy

Bir CD2DBitmap nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dbitmapdetach"></a><a name="detach"></a> CD2DBitmap::D etach

Nesneden kaynak arabirimini ayırır.

```
ID2D1Bitmap* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılan kaynak arabirimine yönelik işaretçi.

## <a name="cd2dbitmapget"></a><a name="get"></a> CD2DBitmap:: Get

ID2D1Bitmap arabirimini döndürür.

```
ID2D1Bitmap* Get();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1Bitmap arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dbitmapgetdpi"></a><a name="getdpi"></a> CD2DBitmap:: GetDPI

Bit eşlemin inç başına nokta (DPı) sayısını döndürür.

```
CD2DSizeF GetDPI() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlemin yatay ve dikey DPı değeri.

## <a name="cd2dbitmapgetpixelformat"></a><a name="getpixelformat"></a> CD2DBitmap:: GetPixelFormat

Bit eşlemin piksel biçimini ve Alfa modunu alır

```
D2D1_PIXEL_FORMAT GetPixelFormat() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlemin piksel biçimi ve alfa modu.

## <a name="cd2dbitmapgetpixelsize"></a><a name="getpixelsize"></a> CD2DBitmap:: GetPixelSize

Bit eşlemin cihaz bağımlı birimlerinde (piksel) boyutunu döndürür.

```
CD2DSizeU GetPixelSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlemin piksel cinsinden boyutu..

## <a name="cd2dbitmapgetsize"></a><a name="getsize"></a> CD2DBitmap:: GetSize

Bit eşlemin cihazdan bağımsız piksel (DIP) cinsinden boyutu döndürür.

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlemin DIPS cinsinden boyutu.

## <a name="cd2dbitmapisvalid"></a><a name="isvalid"></a> CD2DBitmap:: IsValid

Kaynak geçerliliğini denetler.

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse doğru; Aksi halde yanlış.

## <a name="cd2dbitmapm_bautodestroyhbmp"></a><a name="m_bautodestroyhbmp"></a> CD2DBitmap:: m_bAutoDestroyHBMP

M_hBmpSrc yok edilmesi gerekiyorsa TRUE; Aksi halde yanlış.

```
BOOL m_bAutoDestroyHBMP;
```

## <a name="cd2dbitmapm_hbmpsrc"></a><a name="m_hbmpsrc"></a> CD2DBitmap:: m_hBmpSrc

Kaynak bit eşlem tanıtıcısı.

```
HBITMAP m_hBmpSrc;
```

## <a name="cd2dbitmapm_lpsztype"></a><a name="m_lpsztype"></a> CD2DBitmap:: m_lpszType

Kaynak türü.

```
LPCTSTR m_lpszType;
```

## <a name="cd2dbitmapm_pbitmap"></a><a name="m_pbitmap"></a> CD2DBitmap:: m_pBitmap

Bir ID2D1Bitmap nesnesine bir işaretçi depolar.

```
ID2D1Bitmap* m_pBitmap;
```

## <a name="cd2dbitmapm_sizedest"></a><a name="m_sizedest"></a> CD2DBitmap:: m_sizeDest

Bit eşlem hedef boyutu.

```
CD2DSizeU m_sizeDest;
```

## <a name="cd2dbitmapm_strpath"></a><a name="m_strpath"></a> CD2DBitmap:: m_strPath

Botmap dosya yolu.

```
CString m_strPath;
```

## <a name="cd2dbitmapm_uiresid"></a><a name="m_uiresid"></a> CD2DBitmap:: m_uiResID

Bit eşlem kaynak KIMLIĞI.

```
UINT m_uiResID;
```

## <a name="cd2dbitmapoperator-id2d1bitmap"></a><a name="operator_id2d1bitmap_star"></a> CD2DBitmap:: operator ID2D1Bitmap *

ID2D1Bitmap arabirimini döndürür

```
operator ID2D1Bitmap*();
```

### <a name="return-value"></a>Dönüş Değeri

ID2D1Bitmap arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
