---
description: 'Daha fazla bilgi edinin: CD2DTextLayout Class'
title: CD2DTextLayout sınıfı
ms.date: 03/27/2019
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
helpviewer_keywords:
- CD2DTextLayout [MFC], CD2DTextLayout
- CD2DTextLayout [MFC], Create
- CD2DTextLayout [MFC], Destroy
- CD2DTextLayout [MFC], Get
- CD2DTextLayout [MFC], GetFontFamilyName
- CD2DTextLayout [MFC], GetLocaleName
- CD2DTextLayout [MFC], IsValid
- CD2DTextLayout [MFC], ReCreate
- CD2DTextLayout [MFC], SetFontFamilyName
- CD2DTextLayout [MFC], SetLocaleName
- CD2DTextLayout [MFC], m_pTextLayout
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
ms.openlocfilehash: 164c8ed5561be6e8f9ee59b07d0aecaced5f7c81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240552"
---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout sınıfı

IDWriteTextLayout için sarmalayıcı.

## <a name="syntax"></a>Syntax

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|Bir CD2DTextLayout nesnesi oluşturur.|
|[CD2DTextLayout:: ~ CD2DTextLayout](#_dtorcd2dtextlayout)|Yok edicisi. D2D metin düzeni nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextLayout:: Create](#create)|Bir CD2DTextLayout oluşturur. (Geçersiz kılmalar [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextLayout::D estroy](#destroy)|Bir CD2DTextLayout nesnesini yok eder. (Geçersiz kılmalar [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextLayout:: Get](#get)|IDWriteTextLayout arabirimini döndürür|
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|Metnin yazı tipi aile adını belirtilen konuma kopyalar.|
|[CD2DTextLayout:: GetLocaleName](#getlocalename)|Belirtilen konumdaki metnin yerel ayar adını alır.|
|[CD2DTextLayout:: IsValid](#isvalid)|Kaynak geçerliliğini denetler (geçersiz kılmalar [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextLayout:: yeniden oluştur](#recreate)|Bir CD2DTextLayout yeniden oluşturur. ( [CD2DResource:: yeniden oluştur](../../mfc/reference/cd2dresource-class.md#recreate)geçersiz kılar.)|
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|Belirtilen metin aralığı içindeki metin için null ile sonlandırılmış yazı tipi aile adını ayarlar|
|[CD2DTextLayout:: SetLocaleName](#setlocalename)|Belirtilen metin aralığı içindeki metnin yerel ayar adını ayarlar|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextLayout:: operator IDWriteTextLayout *](#operator_idwritetextlayout_star)|IDWriteTextLayout arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextLayout:: m_pTextLayout](#m_ptextlayout)|IDWriteTextLayout işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget. h

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="_dtorcd2dtextlayout"></a> CD2DTextLayout:: ~ CD2DTextLayout

Yok edicisi. D2D metin düzeni nesnesi yok edildiğinde çağırılır.

```
virtual ~CD2DTextLayout();
```

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="cd2dtextlayout"></a> CD2DTextLayout::CD2DTextLayout

Bir CD2DTextLayout nesnesi oluşturur.

```
CD2DTextLayout(
    CRenderTarget* pParentTarget,
    const CString& strText,
    CD2DTextFormat& textFormat,
    const CD2DSizeF& sizeMax,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*pParentTarget*<br/>
İşleme hedefi işaretçisi.

*strText*<br/>
Öğesinden yeni bir CD2DTextLayout nesnesi oluşturmak için dizeyi içeren bir CString nesnesi.

*textFormat*<br/>
Dizeye uygulanacak biçimi içeren bir CString nesnesi.

*Maksimum boyut*<br/>
Düzen kutusunun boyutu.

*bAutoDestroy*<br/>
Nesnenin sahip tarafından (pParentTarget) yok edileceği anlamına gelir.

## <a name="cd2dtextlayoutcreate"></a><a name="create"></a> CD2DTextLayout:: Create

Bir CD2DTextLayout oluşturur.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dtextlayoutdestroy"></a><a name="destroy"></a> CD2DTextLayout::D estroy

Bir CD2DTextLayout nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dtextlayoutget"></a><a name="get"></a> CD2DTextLayout:: Get

IDWriteTextLayout arabirimini döndürür

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Iwritetextlayout arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dtextlayoutgetfontfamilyname"></a><a name="getfontfamilyname"></a> CD2DTextLayout::GetFontFamilyName

Metnin yazı tipi aile adını belirtilen konuma kopyalar.

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Parametreler

*currentPosition*<br/>
İnceleyecek metnin konumu.

*textRange*<br/>
CurrentPosition tarafından belirtilen konumdaki metinle aynı biçimlendirmeye sahip metin aralığı. Bu, çalıştırmanın, yazı tipi aile adıyla sınırlı olmamak üzere, belirtilen konum için tam biçimlendirmeye sahip olduğu anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli yazı tipi aile adını içeren CString nesnesi.

## <a name="cd2dtextlayoutgetlocalename"></a><a name="getlocalename"></a> CD2DTextLayout:: GetLocaleName

Belirtilen konumdaki metnin yerel ayar adını alır.

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Parametreler

*currentPosition*<br/>
İncelenecek metnin konumu.

*textRange*<br/>
CurrentPosition tarafından belirtilen konumdaki metinle aynı biçimlendirmeye sahip metin aralığı. Bu, çalıştırmanın, yerel ayar adıyla sınırlı olmamak üzere, belirtilen konum için tam biçimlendirmeye sahip olduğu anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli yerel ayar adını içeren CString nesnesi.

## <a name="cd2dtextlayoutisvalid"></a><a name="isvalid"></a> CD2DTextLayout:: IsValid

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse doğru; Aksi halde yanlış.

## <a name="cd2dtextlayoutm_ptextlayout"></a><a name="m_ptextlayout"></a> CD2DTextLayout:: m_pTextLayout

IDWriteTextLayout işaretçisi.

```
IDWriteTextLayout* m_pTextLayout;
```

## <a name="cd2dtextlayoutoperator-idwritetextlayout"></a><a name="operator_idwritetextlayout_star"></a> CD2DTextLayout:: operator IDWriteTextLayout *

IDWriteTextLayout arabirimini döndürür

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>Dönüş Değeri

Iwritetextlayout arabirimine yönelik işaretçi veya nesne henüz başlatılamıyorsa NULL.

## <a name="cd2dtextlayoutrecreate"></a><a name="recreate"></a> CD2DTextLayout:: yeniden oluştur

Bir CD2DTextLayout yeniden oluşturur.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dtextlayoutsetfontfamilyname"></a><a name="setfontfamilyname"></a> CD2DTextLayout::SetFontFamilyName

Belirtilen metin aralığı içindeki metin için null ile sonlandırılmış yazı tipi aile adını ayarlar

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Parametreler

*pwzFontFamilyName*<br/>
TextRange tarafından belirtilen aralıktaki bütün metin dizesinin tamamına uygulanan yazı tipi aile adı

*textRange*<br/>
Bu değişikliğin uygulandığı metin aralığı

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür

## <a name="cd2dtextlayoutsetlocalename"></a><a name="setlocalename"></a> CD2DTextLayout:: SetLocaleName

Belirtilen metin aralığı içindeki metnin yerel ayar adını ayarlar

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Parametreler

*pwzLocaleName*<br/>
Null ile sonlandırılmış yerel ayar adı dizesi

*textRange*<br/>
Bu değişikliğin uygulandığı metin aralığı

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
