---
title: CD2DTextFormat Sınıfı
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
ms.openlocfilehash: f7310fd3ca2ac34df7cc1a99cd5527ea8ba709c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369043"
---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat Sınıfı

IDWriteTextFormat için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DTextFormat : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|CD2DTextFormat nesnesi oluşturuyor.|
|[CD2DTextFormat::~CD2DTextFormat](#_dtorcd2dtextformat)|Yıkıcı. D2D metin biçimi nesnesi yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DTextFormat::Oluştur](#create)|BIR CD2DTextFormat oluşturur. [(CD2DResource geçersiz kılar::Oluştur](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextFormat::Destroy](#destroy)|BIR CD2DTextFormat nesnesini yok eder. (GEÇERSIZ Kılar [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextFormat::Get](#get)|IDWriteTextFormat arabirimini döndürür|
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|Yazı tipi soyadının bir kopyasını alır.|
|[CD2DTextFormat::GetLocaleName](#getlocalename)|Yerel adın bir kopyasını alır.|
|[CD2DTextFormat::Geçersiz](#isvalid)|Kaynak geçerliliğini denetler [(CD2DResource geçersiz kılar::Geçerlidir](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextFormat::Yeniden Oluşturma](#recreate)|CD2DTextFormat'ı yeniden oluşturur. [(CD2DResource geçersiz kılar::Yeniden Oluşturun](../../mfc/reference/cd2dresource-class.md#recreate).)|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DTextFormat::operatör IDWriteTextFormat*](#operator_idwritetextformat_star)|IDWriteTextFormat arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DTextFormat::m_pTextFormat](#m_ptextformat)|IDWriteTextFormat için bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CD2DKaynak](../../mfc/reference/cd2dresource-class.md)

[CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dtextformatcd2dtextformat"></a><a name="_dtorcd2dtextformat"></a>CD2DTextFormat::~CD2DTextFormat

Yıkıcı. D2D metin biçimi nesnesi yok edilirken çağrılır.

```
virtual ~CD2DTextFormat();
```

## <a name="cd2dtextformatcd2dtextformat"></a><a name="cd2dtextformat"></a>CD2DTextFormat::CD2DTextFormat

CD2DTextFormat nesnesi oluşturuyor.

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
İşleme hedefine işaretçi.

*strFontFamilyName*<br/>
Yazı tipi ailesinin adını içeren bir CString nesnesi.

*Fontsize*<br/>
DIP ("aygıttan bağımsız piksel") birimlerindeki yazı tipinin mantıksal boyutu. Bir DIP eşittir 1/96 inç.

*Fontweight*<br/>
Metin nesnesinin yazı tipi ağırlığını gösteren bir değer.

*Fontstyle*<br/>
Metin nesnesinin yazı tipi stilini gösteren bir değer.

*Fontstretch*<br/>
Metin nesnesi için yazı tipi uzantısını gösteren bir değer.

*strFontLocale*<br/>
Yerel ad içeren bir CString nesnesi.

*pFontCollection*<br/>
Yazı tipi toplama nesnesine işaretçi. Bu NULL olduğunda, sistem yazı tipi koleksiyonunu gösterir.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

## <a name="cd2dtextformatcreate"></a><a name="create"></a>CD2DTextFormat::Oluştur

BIR CD2DTextFormat oluşturur.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dtextformatdestroy"></a><a name="destroy"></a>CD2DTextFormat::Destroy

BIR CD2DTextFormat nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dtextformatget"></a><a name="get"></a>CD2DTextFormat::Get

IDWriteTextFormat arabirimini döndürür

```
IDWriteTextFormat* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe yazılmazsa, IDWriteTextFormat arabirimini işaretçi veya NULL.

## <a name="cd2dtextformatgetfontfamilyname"></a><a name="getfontfamilyname"></a>CD2DTextFormat::GetFontFamilyName

Yazı tipi soyadının bir kopyasını alır.

```
CString GetFontFamilyName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yazı tipi aile adını içeren CString nesnesi.

## <a name="cd2dtextformatgetlocalename"></a><a name="getlocalename"></a>CD2DTextFormat::GetLocaleName

Yerel adın bir kopyasını alır.

```
CString GetLocaleName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yerel ad içeren CString nesnesi.

## <a name="cd2dtextformatisvalid"></a><a name="isvalid"></a>CD2DTextFormat::Geçersiz

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2dtextformatm_ptextformat"></a><a name="m_ptextformat"></a>CD2DTextFormat::m_pTextFormat

IDWriteTextFormat için bir işaretçi.

```
IDWriteTextFormat* m_pTextFormat;
```

## <a name="cd2dtextformatoperator-idwritetextformat"></a><a name="operator_idwritetextformat_star"></a>CD2DTextFormat::operatör IDWriteTextFormat*

IDWriteTextFormat arabirimini döndürür

```
operator IDWriteTextFormat*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe yazılmazsa, IDWriteTextFormat arabirimini işaretçi veya NULL.

## <a name="cd2dtextformatrecreate"></a><a name="recreate"></a>CD2DTextFormat::Yeniden Oluşturma

CD2DTextFormat'ı yeniden oluşturur.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
