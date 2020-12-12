---
description: 'Daha fazla bilgi edinin: CD2DTextFormat Class'
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
ms.openlocfilehash: fc87aec6acb0e1eae0211555f1bdc943079081f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338327"
---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat sınıfı

IDWriteTextFormat için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DTextFormat : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|Bir CD2DTextFormat nesnesi oluşturur.|
|[CD2DTextFormat:: ~ CD2DTextFormat](#_dtorcd2dtextformat)|Yok edicisi. D2D metin biçimi nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextFormat:: Create](#create)|Bir CD2DTextFormat oluşturur. (Geçersiz kılmalar [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextFormat::D estroy](#destroy)|Bir CD2DTextFormat nesnesini yok eder. (Geçersiz kılmalar [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextFormat:: Get](#get)|IDWriteTextFormat arabirimini döndürür|
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|Yazı tipi aile adının bir kopyasını alır.|
|[CD2DTextFormat:: GetLocaleName](#getlocalename)|Yerel ayar adının bir kopyasını alır.|
|[CD2DTextFormat:: IsValid](#isvalid)|Kaynak geçerliliğini denetler (geçersiz kılmalar [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextFormat:: yeniden oluştur](#recreate)|Bir CD2DTextFormat yeniden oluşturur. ( [CD2DResource:: yeniden oluştur](../../mfc/reference/cd2dresource-class.md#recreate)geçersiz kılar.)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextFormat:: operator IDWriteTextFormat *](#operator_idwritetextformat_star)|IDWriteTextFormat arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextFormat:: m_pTextFormat](#m_ptextformat)|IDWriteTextFormat için bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dtextformatcd2dtextformat"></a><a name="_dtorcd2dtextformat"></a> CD2DTextFormat:: ~ CD2DTextFormat

Yok edicisi. D2D metin biçimi nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DTextFormat();
```

## <a name="cd2dtextformatcd2dtextformat"></a><a name="cd2dtextformat"></a> CD2DTextFormat::CD2DTextFormat

Bir CD2DTextFormat nesnesi oluşturur.

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
İşleme hedefi işaretçisi.

*strFontFamilyName*<br/>
Yazı tipi ailesinin adını içeren bir CString nesnesi.

*fontSize*<br/>
DIP ("cihazdan bağımsız piksel") birimlerindeki yazı tipinin mantıksal boyutu. Bir dı(eşittir 1/96 inç.

*fontWeight*<br/>
Metin nesnesinin yazı tipi kalınlığını gösteren bir değer.

*fontStyle*<br/>
Metin nesnesinin yazı tipi stilini gösteren bir değer.

*Fontesnetme*<br/>
Metin nesnesi için yazı tipi uzatıldığını belirten bir değer.

*strFontLocale*<br/>
Yerel ayar adını içeren bir CString nesnesi.

*pFontCollection*<br/>
Yazı tipi koleksiyonu nesnesine yönelik bir işaretçi. Bu NULL olduğunda, sistem yazı tipi koleksiyonunu gösterir.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

## <a name="cd2dtextformatcreate"></a><a name="create"></a> CD2DTextFormat:: Create

Bir CD2DTextFormat oluşturur.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dtextformatdestroy"></a><a name="destroy"></a> CD2DTextFormat::D estroy

Bir CD2DTextFormat nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dtextformatget"></a><a name="get"></a> CD2DTextFormat:: Get

IDWriteTextFormat arabirimini döndürür

```
IDWriteTextFormat* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir IDWriteTextFormat arabirimine yönelik işaretçi veya nesne henüz başlatılmamış ise NULL.

## <a name="cd2dtextformatgetfontfamilyname"></a><a name="getfontfamilyname"></a> CD2DTextFormat::GetFontFamilyName

Yazı tipi aile adının bir kopyasını alır.

```
CString GetFontFamilyName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yazı tipi aile adını içeren CString nesnesi.

## <a name="cd2dtextformatgetlocalename"></a><a name="getlocalename"></a> CD2DTextFormat:: GetLocaleName

Yerel ayar adının bir kopyasını alır.

```
CString GetLocaleName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli yerel ayar adını içeren CString nesnesi.

## <a name="cd2dtextformatisvalid"></a><a name="isvalid"></a> CD2DTextFormat:: IsValid

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse doğru; Aksi halde yanlış.

## <a name="cd2dtextformatm_ptextformat"></a><a name="m_ptextformat"></a> CD2DTextFormat:: m_pTextFormat

IDWriteTextFormat için bir işaretçi.

```
IDWriteTextFormat* m_pTextFormat;
```

## <a name="cd2dtextformatoperator-idwritetextformat"></a><a name="operator_idwritetextformat_star"></a> CD2DTextFormat:: operator IDWriteTextFormat *

IDWriteTextFormat arabirimini döndürür

```
operator IDWriteTextFormat*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir IDWriteTextFormat arabirimine yönelik işaretçi veya nesne henüz başlatılmamış ise NULL.

## <a name="cd2dtextformatrecreate"></a><a name="recreate"></a> CD2DTextFormat:: yeniden oluştur

Bir CD2DTextFormat yeniden oluşturur.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
