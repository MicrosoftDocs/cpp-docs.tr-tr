---
title: CD2DTextFormat sınıfı
ms.date: 03/27/2019
f1_keywords:
- CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::Create
- AFXRENDERTARGET/CD2DTextFormat::Destroy
- AFXRENDERTARGET/CD2DTextFormat::Get
- AFXRENDERTARGET/CD2DTextFormat::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextFormat::GetLocaleName
- AFXRENDERTARGET/CD2DTextFormat::IsValid
- AFXRENDERTARGET/CD2DTextFormat::ReCreate
- AFXRENDERTARGET/CD2DTextFormat::m_pTextFormat
helpviewer_keywords:
- CD2DTextFormat [MFC], CD2DTextFormat
- CD2DTextFormat [MFC], Create
- CD2DTextFormat [MFC], Destroy
- CD2DTextFormat [MFC], Get
- CD2DTextFormat [MFC], GetFontFamilyName
- CD2DTextFormat [MFC], GetLocaleName
- CD2DTextFormat [MFC], IsValid
- CD2DTextFormat [MFC], ReCreate
- CD2DTextFormat [MFC], m_pTextFormat
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
ms.openlocfilehash: fa2f3b663cb5258c64ec0405abacf2e4eedeb987
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565327"
---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat sınıfı

IDWriteTextFormat için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DTextFormat : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|CD2DTextFormat bir nesne oluşturur.|
|[CD2DTextFormat::~CD2DTextFormat](#_dtorcd2dtextformat)|Yıkıcı. D2D metin biçimi nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextFormat::Create](#create)|Bir CD2DTextFormat oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextFormat::Destroy](#destroy)|CD2DTextFormat nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextFormat::get](#get)|Döndürür IDWriteTextFormat arabirimi|
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|Yazı tipi ailesinin adı bir kopyasını alır.|
|[CD2DTextFormat::GetLocaleName](#getlocalename)|Yerel ayar adına bir kopyasını alır.|
|[CD2DTextFormat::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextFormat::ReCreate](#recreate)|Bir CD2DTextFormat yeniden oluşturur. (Geçersiz kılmaları [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextFormat::operator IDWriteTextFormat *](#operator_idwritetextformat_star)|Döndürür IDWriteTextFormat arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextFormat::m_pTextFormat](#m_ptextformat)|Bir IDWriteTextFormat işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dtextformat"></a>  CD2DTextFormat:: ~ CD2DTextFormat

Yıkıcı. D2D metin biçimi nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DTextFormat();
```

##  <a name="cd2dtextformat"></a>  CD2DTextFormat::CD2DTextFormat

CD2DTextFormat bir nesne oluşturur.

```
CD2DTextFormat(
    CRenderTarget* pParentTarget,
    const CString& strFontFamilyName,
    FLOAT fontSize,
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,
    const CString& strFontLocale = _T(""),
    IDWriteFontCollection* pFontCollection = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi için bir işaretçi.

*strFontFamilyName*<br/>
Yazı tipi ailesinin adı içeren bir CString nesne.

*FontSize*<br/>
Yazı tipi DIP ("CİHAZDAN bağımsız piksel") birimi mantıksal boyutu. Bir DIPequals 1/96 inç.

*fontWeight*<br/>
Metin nesnesi için yazı tipi ağırlığı belirten bir değer.

*fontStyle*<br/>
Yazı tipi stili metin nesnesini gösteren bir değer.

*fontStretch*<br/>
Metin nesnesi için yazı tipi esnetme belirten bir değer.

*strFontLocale*<br/>
Yerel ayar adı içeren bir CString nesne.

*pFontCollection*<br/>
Yazı tipi koleksiyonu nesnesine bir işaretçi. Bu NULL olduğunda, sistem yazı tipi koleksiyonu belirtir.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

##  <a name="create"></a>  CD2DTextFormat::Create

Bir CD2DTextFormat oluşturur.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="destroy"></a>  CD2DTextFormat::Destroy

CD2DTextFormat nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="get"></a>  CD2DTextFormat::get

Döndürür IDWriteTextFormat arabirimi

```
IDWriteTextFormat* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir IDWriteTextFormat arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="getfontfamilyname"></a>  CD2DTextFormat::GetFontFamilyName

Yazı tipi ailesinin adı bir kopyasını alır.

```
CString GetFontFamilyName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yazı tipi ailesinin adı içeren CString nesne.

##  <a name="getlocalename"></a>  CD2DTextFormat::GetLocaleName

Yerel ayar adına bir kopyasını alır.

```
CString GetLocaleName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yerel ayar adını içeren CString nesne.

##  <a name="isvalid"></a>  CD2DTextFormat::IsValid

Kaynak geçerlilik denetimleri

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerli ise TRUE; Aksi durumda FALSE.

##  <a name="m_ptextformat"></a>  CD2DTextFormat::m_pTextFormat

Bir IDWriteTextFormat işaretçisi.

```
IDWriteTextFormat* m_pTextFormat;
```

##  <a name="operator_idwritetextformat_star"></a>  CD2DTextFormat::operator IDWriteTextFormat *

Döndürür IDWriteTextFormat arabirimi

```
operator IDWriteTextFormat*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir IDWriteTextFormat arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="recreate"></a>  CD2DTextFormat::ReCreate

Bir CD2DTextFormat yeniden oluşturur.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
