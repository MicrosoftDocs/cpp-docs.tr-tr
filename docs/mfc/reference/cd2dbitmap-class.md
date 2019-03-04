---
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
ms.openlocfilehash: 288ba5e1503a4e3eefe83624cf9a489274a10823
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264722"
---
# <a name="cd2dbitmap-class"></a>CD2DBitmap sınıfı

ID2D1Bitmap için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DBitmap : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Fazla Yüklendi. HBITMAP CD2DBitmap nesneden oluşturur.|
|[CD2DBitmap:: ~ CD2DBitmap](#_dtorcd2dbitmap)|Yıkıcı. D2D bitmap nesnesi yok ediliyorken çağırılır.|

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap::CD2DBitmap](#cd2dbitmap)|Fazla Yüklendi. CD2DBitmap bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap::Attach](#attach)|Var olan kaynak arabirimi nesnesine ekler|
|[CD2DBitmap::CopyFromBitmap](#copyfrombitmap)|Belirtilen bölge belirtilen bit eşlem geçerli bit eşleme kopyalar.|
|[CD2DBitmap::CopyFromMemory](#copyfrommemory)|Belirtilen bölge bellekten geçerli bit eşleme kopyalar.|
|[CD2DBitmap::CopyFromRenderTarget](#copyfromrendertarget)|Kopya belirtilen belirtilen bölgeden işleme hedefi geçerli bit eşleme|
|[CD2DBitmap::Create](#create)|Bir CD2DBitmap oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DBitmap::Destroy](#destroy)|CD2DBitmap nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DBitmap::detach](#detach)|Kaynak arabirimi nesnesinden ayırır|
|[CD2DBitmap::get](#get)|Döndürür ID2D1Bitmap arabirimi|
|[CD2DBitmap::GetDPI](#getdpi)|Nokta / inç (DPI) bit eşlemin döndürür|
|[CD2DBitmap::GetPixelFormat](#getpixelformat)|Bit eşlemin piksel biçimi ve alfa modunu alır.|
|[CD2DBitmap::GetPixelSize](#getpixelsize)|Bit eşlemin cihaza bağlı birimler (piksel) boyutunu döndürür|
|[CD2DBitmap::GetSize](#getsize)|Bit eşlemin CİHAZDAN bağımsız piksel (DIP) boyutunu döndürür|
|[CD2DBitmap::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap::CommonInit](#commoninit)|Nesneyi başlatır|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap::operator ID2D1Bitmap *](#operator_id2d1bitmap_star)|Döndürür ID2D1Bitmap arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DBitmap::m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|M_hBmpSrc yok TRUE; Aksi durumda FALSE.|
|[CD2DBitmap::m_hBmpSrc](#m_hbmpsrc)|Kaynak bit eşlem tanıtıcısı.|
|[CD2DBitmap::m_lpszType](#m_lpsztype)|Kaynak türü.|
|[CD2DBitmap::m_pBitmap](#m_pbitmap)|ID2D1Bitmap nesneye bir işaretçi depolar.|
|[CD2DBitmap::m_sizeDest](#m_sizedest)|Hedef boyut bit eşlem.|
|[CD2DBitmap::m_strPath](#m_strpath)|Botmap dosya yolu.|
|[CD2DBitmap::m_uiResID](#m_uiresid)|Bit eşlem kaynak kimliği|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DBitmap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dbitmap"></a>  CD2DBitmap:: ~ CD2DBitmap

Yıkıcı. D2D bitmap nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DBitmap();
```

##  <a name="attach"></a>  CD2DBitmap::Attach

Var olan kaynak arabirimi nesnesine ekler.

```
void Attach(ID2D1Bitmap* pResource);
```

### <a name="parameters"></a>Parametreler

*pResource*<br/>
Mevcut kaynak arabirimi. NULL olamaz.

##  <a name="cd2dbitmap"></a>  CD2DBitmap::CD2DBitmap

Kaynaktan CD2DBitmap bir nesne oluşturur.

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
İşleme hedefi için bir işaretçi.

*uiResID*<br/>
Kaynak Kimliği kaynak sayısı.

*lpszType*<br/>
Kaynak türü içeren null ile sonlandırılmış bir dize işaretçisi.

*sizeDest*<br/>
Bit eşlem hedef boyutu.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

*lpszPath*<br/>
Dosya adını içeren null ile sonlandırılmış bir dize işaretçisi.

*hbmpSrc*<br/>
Bit eşleme işleyin.

##  <a name="commoninit"></a>  CD2DBitmap::CommonInit

Nesnesini başlatır.

```
void CommonInit();
```

##  <a name="copyfrombitmap"></a>  CD2DBitmap::CopyFromBitmap

Belirtilen bölge belirtilen bit eşlem geçerli bit eşleme kopyalar.

```
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pBitmap*<br/>
Kopyalamak için bit eşlem.

*destPoint*<br/>
Geçerli bit eşlem içinde olduğu bölgeye srcRect tarafından belirtilen alanın sol üst köşesine kopyalanır.

*srcRect*<br/>
Bit eşlem kopyalamak için alanı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="copyfrommemory"></a>  CD2DBitmap::CopyFromMemory

Belirtilen bölge bellekten geçerli bit eşleme kopyalar.

```
HRESULT CopyFromMemory(
    const void* srcData,
    UINT32 pitch,
    const CD2DRectU* destRect = NULL);
```

### <a name="parameters"></a>Parametreler

*srcData*<br/>
Kopyalanacak verileri.

*Aralık*<br/>
STRIDE veya aralığını srcData içinde depolanan kaynak bit eşlemi. STRIDE (piksel cinsinden bellek bir satır) bir tarama satırı bayt sayısıdır. STRIDE aşağıdaki formülünden hesaplanan değer: piksel genişliği \* piksel + bellek doldurma başına bayt sayısı.

*destRect*<br/>
Geçerli bit eşlem içinde olduğu bölgeye srcRect tarafından belirtilen alanın sol üst köşesine kopyalanır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="copyfromrendertarget"></a>  CD2DBitmap::CopyFromRenderTarget

Kopya belirtilen bölge belirtilen hedef geçerli bit eşleme işleyin.

```
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
Kopyalamak için bölge içeren işleme hedefi.

*destPoint*<br/>
Geçerli bit eşlem içinde olduğu bölgeye srcRect tarafından belirtilen alanın sol üst köşesine kopyalanır.

*srcRect*<br/>
İşlem hedefi kopyalamak için alanı.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="create"></a>  CD2DBitmap::Create

Bir CD2DBitmap oluşturur.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametreler

*pRenderTarget*<br/>
İşleme hedefi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="destroy"></a>  CD2DBitmap::Destroy

CD2DBitmap nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DBitmap::detach

Kaynak arabirimi nesneden çıkarır.

```
ID2D1Bitmap* Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış kaynak arabirim işaretçisi.

##  <a name="get"></a>  CD2DBitmap::get

ID2D1Bitmap arabirimi döndürür.

```
ID2D1Bitmap* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1Bitmap arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="getdpi"></a>  CD2DBitmap::GetDPI

Nokta / inç (DPI) bit eşlemin döndürür.

```
CD2DSizeF GetDPI() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlem yatay ve dikey DPI.

##  <a name="getpixelformat"></a>  CD2DBitmap::GetPixelFormat

Bit eşlemin piksel biçimi ve alfa modunu alır.

```
D2D1_PIXEL_FORMAT GetPixelFormat() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlemin piksel biçimi ve alfa modu.

##  <a name="getpixelsize"></a>  CD2DBitmap::GetPixelSize

Bit eşlemin cihaza bağlı birimler (piksel) boyutunu döndürür.

```
CD2DSizeU GetPixelSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlemin piksel cinsinden boyutu...

##  <a name="getsize"></a>  CD2DBitmap::GetSize

CİHAZDAN bağımsız piksel (DIP) boyutu, bit eşlemin döndürür.

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlemin bir Dıps boyutu.

##  <a name="isvalid"></a>  CD2DBitmap::IsValid

Kaynak geçerlilik denetler.

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerli ise TRUE; Aksi durumda FALSE.

##  <a name="m_bautodestroyhbmp"></a>  CD2DBitmap::m_bAutoDestroyHBMP

M_hBmpSrc yok TRUE; Aksi durumda FALSE.

```
BOOL m_bAutoDestroyHBMP;
```

##  <a name="m_hbmpsrc"></a>  CD2DBitmap::m_hBmpSrc

Kaynak bit eşlem tanıtıcısı.

```
HBITMAP m_hBmpSrc;
```

##  <a name="m_lpsztype"></a>  CD2DBitmap::m_lpszType

Kaynak türü.

```
LPCTSTR m_lpszType;
```

##  <a name="m_pbitmap"></a>  CD2DBitmap::m_pBitmap

ID2D1Bitmap nesneye bir işaretçi depolar.

```
ID2D1Bitmap* m_pBitmap;
```

##  <a name="m_sizedest"></a>  CD2DBitmap::m_sizeDest

Hedef boyut bit eşlem.

```
CD2DSizeU m_sizeDest;
```

##  <a name="m_strpath"></a>  CD2DBitmap::m_strPath

Botmap dosya yolu.

```
CString m_strPath;
```

##  <a name="m_uiresid"></a>  CD2DBitmap::m_uiResID

Bit eşlem kaynak kimliği

```
UINT m_uiResID;
```

##  <a name="operator_id2d1bitmap_star"></a>  CD2DBitmap::operator ID2D1Bitmap *

Döndürür ID2D1Bitmap arabirimi

```
operator ID2D1Bitmap*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ID2D1Bitmap arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
