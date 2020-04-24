---
title: CD2DBitmap Sınıfı
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
ms.openlocfilehash: a3cabb00ded7dbc5f9c396a1de767058443a4436
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754211"
---
# <a name="cd2dbitmap-class"></a>CD2DBitmap Sınıfı

ID2D1Bitmap için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DBitmap : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Fazla Yüklendi. HBITMAP'ten bir CD2DBitmap nesnesi oluşturur.|
|[CD2DBitmap::~CD2DBitmap](#_dtorcd2dbitmap)|Yıkıcı. D2D bitmap nesnesi yok edildiğinde çağrılır.|

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Fazla Yüklendi. CD2DBitmap nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBitmap::Ekle](#attach)|Nesneye varolan kaynak arabirimi ataştırır|
|[CD2DBitmap::CopyFromBitmap](#copyfrombitmap)|Belirtilen bölgeyi belirtilen bit eşleminden geçerli bit haritasına kopyalar|
|[CD2DBitmap::CopyFromMemory](#copyfrommemory)|Belirtilen bölgeyi bellekten geçerli bit eşleneği kopyalar|
|[CD2DBitmap::CopyFromRenderTarget](#copyfromrendertarget)|Belirtilen bölgeyi belirtilen işleme hedefinden geçerli bit haritasına kopyalar|
|[CD2DBitmap::Oluştur](#create)|BIR CD2DBitmap oluşturur. [(CD2DResource geçersiz kılar::Oluştur](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DBitmap::Destroy](#destroy)|CD2DBitmap nesnesini yok eder. (GEÇERSIZ Kılar [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DBitmap::Detach](#detach)|Kaynak arabirimini nesneden ayırıyor|
|[CD2DBitmap::Alın](#get)|ID2D1Bitmap arabirimini döndürür|
|[CD2DBitmap::GetDPI](#getdpi)|Bit haritasının inç başına noktalarını (DPI) döndürme|
|[CD2DBitmap::GetPixelFormat](#getpixelformat)|Bit haritasının piksel biçimini ve alfa modunu alır|
|[CD2DBitmap::GetPixelSize](#getpixelsize)|Bit eşboyutunu, aygıta bağımlı birimlerde (piksel) döndürür|
|[CD2DBitmap::GetSize](#getsize)|Bit eşboyutunu, aygıttan bağımsız piksellerde (DIPs) döndürür|
|[CD2DBitmap::Geçersiz](#isvalid)|Kaynak geçerliliğini denetler [(CD2DResource geçersiz kılar::Geçerlidir](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBitmap::CommonInit](#commoninit)|Nesneyi başharfe alar|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBitmap::operatör ID2D1Bitmap*](#operator_id2d1bitmap_star)|ID2D1Bitmap arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DBitmap::m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|m_hBmpSrc yok edilmesi halinde DOĞRU; aksi takdirde YANLIŞ.|
|[CD2DBitmap::m_hBmpSrc](#m_hbmpsrc)|Kaynak bitmap tutamacı.|
|[CD2DBitmap::m_lpszType](#m_lpsztype)|Kaynak türü.|
|[CD2DBitmap::m_pBitmap](#m_pbitmap)|Bir işaretçiyi ID2D1Bitmap nesnesine depolar.|
|[CD2DBitmap::m_sizeDest](#m_sizedest)|Bitmap hedef boyutu.|
|[CD2DBitmap::m_strPath](#m_strpath)|Botmap dosya yolu.|
|[CD2DBitmap::m_uiResID](#m_uiresid)|Bitmap kaynak kimliği.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CD2DKaynak](../../mfc/reference/cd2dresource-class.md)

`CD2DBitmap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dbitmapcd2dbitmap"></a><a name="_dtorcd2dbitmap"></a>CD2DBitmap::~CD2DBitmap

Yıkıcı. D2D bitmap nesnesi yok edildiğinde çağrılır.

```
virtual ~CD2DBitmap();
```

## <a name="cd2dbitmapattach"></a><a name="attach"></a>CD2DBitmap::Ekle

Nesneye varolan kaynak arabirimi ataştırır.

```cpp
void Attach(ID2D1Bitmap* pResource);
```

### <a name="parameters"></a>Parametreler

*pKaynak*<br/>
Varolan kaynak arabirimi. NULL olamaz.

## <a name="cd2dbitmapcd2dbitmap"></a><a name="cd2dbitmap"></a>CD2DBitmap::CD2DBitmap

Kaynaktan bir CD2DBitmap nesnesi oluşturur.

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
İşleme hedefine işaretçi.

*uiResID*<br/>
Kaynağın kaynak kimlik numarası.

*lpszType*<br/>
Kaynak türünü içeren null-sonlandırılan dize işaretçi.

*boyutDest*<br/>
Bit eşleninhedef boyutu.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

*lpszPath*<br/>
Dosya nın adını içeren null-sonlandırılan dize işaretçi.

*hbmpSrc*<br/>
Bit eşlenini ele alın.

## <a name="cd2dbitmapcommoninit"></a><a name="commoninit"></a>CD2DBitmap::CommonInit

Nesneyi baş harfe doğru laştırır.

```cpp
void CommonInit();
```

## <a name="cd2dbitmapcopyfrombitmap"></a><a name="copyfrombitmap"></a>CD2DBitmap::CopyFromBitmap

Belirtilen bölgeyi belirtilen bit eşleminden geçerli bit eşlemine kopyalar.

```
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pBitmap*<br/>
Kopyalanması gereken bit eşlemi.

*destPoint*<br/>
Geçerli bit haritasında, srcRect tarafından belirtilen bölgenin bulunduğu alanın sol üst köşesi kopyalanır.

*Srcrect*<br/>
Kopyalamak için bitmap alanı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dbitmapcopyfrommemory"></a><a name="copyfrommemory"></a>CD2DBitmap::CopyFromMemory

Belirtilen bölgeyi bellekten geçerli bit eşleneği kopyalar.

```
HRESULT CopyFromMemory(
    const void* srcData,
    UINT32 pitch,
    const CD2DRectU* destRect = NULL);
```

### <a name="parameters"></a>Parametreler

*srcData*<br/>
Kopyalanması gereken veriler.

*Pitch*<br/>
SrcData'da depolanan kaynak bit haritasının adımı veya perdesi. Adım, bir scanline 'nin (bellekteki bir piksel satırı) bayt sayısıdır. Adım aşağıdaki formülden hesaplanabilir: piksel başına \* piksel genişliği bayt + bellek doldurma.

*destRect*<br/>
Geçerli bit haritasında, srcRect tarafından belirtilen bölgenin bulunduğu alanın sol üst köşesi kopyalanır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dbitmapcopyfromrendertarget"></a><a name="copyfromrendertarget"></a>CD2DBitmap::CopyFromRenderTarget

Belirtilen bölgeyi belirtilen işleme hedefinden geçerli bit eşlene kopyalar.

```
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
Kopyalanması gereken bölgeyi içeren render hedefi.

*destPoint*<br/>
Geçerli bit haritasında, srcRect tarafından belirtilen bölgenin bulunduğu alanın sol üst köşesi kopyalanır.

*Srcrect*<br/>
Kopyalamak için renderTarget alanı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dbitmapcreate"></a><a name="create"></a>CD2DBitmap::Oluştur

BIR CD2DBitmap oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dbitmapdestroy"></a><a name="destroy"></a>CD2DBitmap::Destroy

CD2DBitmap nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dbitmapdetach"></a><a name="detach"></a>CD2DBitmap::Detach

Kaynak arabirimini nesneden ayırır.

```
ID2D1Bitmap* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirimine işaretçi.

## <a name="cd2dbitmapget"></a><a name="get"></a>CD2DBitmap::Alın

ID2D1Bitmap arabirimini döndürür.

```
ID2D1Bitmap* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1Bitmap arabirimine veya NULL'a işaretçi.

## <a name="cd2dbitmapgetdpi"></a><a name="getdpi"></a>CD2DBitmap::GetDPI

Bit eşleninin inç başına noktalarını (DPI) döndürün.

```
CD2DSizeF GetDPI() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit haritasının yatay ve dikey DPI'si.

## <a name="cd2dbitmapgetpixelformat"></a><a name="getpixelformat"></a>CD2DBitmap::GetPixelFormat

Bit haritasının piksel biçimini ve alfa modunu alır

```
D2D1_PIXEL_FORMAT GetPixelFormat() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit haritasının piksel biçimi ve alfa modu.

## <a name="cd2dbitmapgetpixelsize"></a><a name="getpixelsize"></a>CD2DBitmap::GetPixelSize

Bit eşboyutunu aygıta bağımlı birimlerde (pikseller) döndürür.

```
CD2DSizeU GetPixelSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Boyutu, piksel, bitmap ...

## <a name="cd2dbitmapgetsize"></a><a name="getsize"></a>CD2DBitmap::GetSize

Bit eşboyutunu, aygıttan bağımsız piksellerde (DIPs) döndürür.

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit haritasının DIPs boyutu.

## <a name="cd2dbitmapisvalid"></a><a name="isvalid"></a>CD2DBitmap::Geçersiz

Kaynak geçerliliğini denetler.

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2dbitmapm_bautodestroyhbmp"></a><a name="m_bautodestroyhbmp"></a>CD2DBitmap::m_bAutoDestroyHBMP

m_hBmpSrc yok edilmesi halinde DOĞRU; aksi takdirde YANLIŞ.

```
BOOL m_bAutoDestroyHBMP;
```

## <a name="cd2dbitmapm_hbmpsrc"></a><a name="m_hbmpsrc"></a>CD2DBitmap::m_hBmpSrc

Kaynak bitmap tutamacı.

```
HBITMAP m_hBmpSrc;
```

## <a name="cd2dbitmapm_lpsztype"></a><a name="m_lpsztype"></a>CD2DBitmap::m_lpszType

Kaynak türü.

```
LPCTSTR m_lpszType;
```

## <a name="cd2dbitmapm_pbitmap"></a><a name="m_pbitmap"></a>CD2DBitmap::m_pBitmap

Bir işaretçiyi ID2D1Bitmap nesnesine depolar.

```
ID2D1Bitmap* m_pBitmap;
```

## <a name="cd2dbitmapm_sizedest"></a><a name="m_sizedest"></a>CD2DBitmap::m_sizeDest

Bitmap hedef boyutu.

```
CD2DSizeU m_sizeDest;
```

## <a name="cd2dbitmapm_strpath"></a><a name="m_strpath"></a>CD2DBitmap::m_strPath

Botmap dosya yolu.

```
CString m_strPath;
```

## <a name="cd2dbitmapm_uiresid"></a><a name="m_uiresid"></a>CD2DBitmap::m_uiResID

Bitmap kaynak kimliği.

```
UINT m_uiResID;
```

## <a name="cd2dbitmapoperator-id2d1bitmap"></a><a name="operator_id2d1bitmap_star"></a>CD2DBitmap::operatör ID2D1Bitmap*

ID2D1Bitmap arabirimini döndürür

```
operator ID2D1Bitmap*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe çevrilmediyse ID2D1Bitmap arabirimine veya NULL'a işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
