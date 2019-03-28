---
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
ms.openlocfilehash: ca89d12c6aeed33be740aa9f999e7c11d6c32056
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565275"
---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout sınıfı

IDWriteTextLayout için sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|CD2DTextLayout bir nesne oluşturur.|
|[CD2DTextLayout:: ~ CD2DTextLayout](#_dtorcd2dtextlayout)|Yıkıcı. D2D metin düzeni nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextLayout::Create](#create)|Bir CD2DTextLayout oluşturur. (Geçersiz kılmaları [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextLayout::Destroy](#destroy)|CD2DTextLayout nesnesini yok eder. (Geçersiz kılmaları [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextLayout::get](#get)|Döndürür IDWriteTextLayout arabirimi|
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|Belirtilen konumda metin yazı tipi ailesinin adı kopyalar.|
|[CD2DTextLayout::GetLocaleName](#getlocalename)|Belirtilen konumda metin yerel ayar adını alır.|
|[CD2DTextLayout::IsValid](#isvalid)|Kaynak geçerlilik denetler (geçersiz kılmaları [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextLayout::ReCreate](#recreate)|Bir CD2DTextLayout yeniden oluşturur. (Geçersiz kılmaları [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|Belirtilen metin aralığı içinde metin ayarlar null ile sonlandırılmış yazı tipi ailesi adı|
|[CD2DTextLayout::SetLocaleName](#setlocalename)|Belirtilen metin aralığı içinde metin için yerel ayar adına ayarlar|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextLayout::operator IDWriteTextLayout *](#operator_idwritetextlayout_star)|Döndürür IDWriteTextLayout arabirimi|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CD2DTextLayout::m_pTextLayout](#m_ptextlayout)|Bir IDWriteTextLayout işaretçisi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrendertarget.h

##  <a name="_dtorcd2dtextlayout"></a>  CD2DTextLayout:: ~ CD2DTextLayout

Yıkıcı. D2D metin düzeni nesnesi yok ediliyorken çağırılır.

```
virtual ~CD2DTextLayout();
```

##  <a name="cd2dtextlayout"></a>  CD2DTextLayout::CD2DTextLayout

CD2DTextLayout bir nesne oluşturur.

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
İşleme hedefi için bir işaretçi.

*strText*<br/>
Yeni bir CD2DTextLayout nesne oluşturmak için dizeyi içeren bir CString nesne.

*textFormat*<br/>
Dize geçerli biçimde içeren bir CString nesne.

*sizeMax*<br/>
Düzen kutusunun boyutu.

*bAutoDestroy*<br/>
Nesne sahibi tarafından (pParentTarget) edileceği gösterir.

##  <a name="create"></a>  CD2DTextLayout::Create

Bir CD2DTextLayout oluşturur.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="destroy"></a>  CD2DTextLayout::Destroy

CD2DTextLayout nesnesini yok eder.

```
virtual void Destroy();
```

##  <a name="get"></a>  CD2DTextLayout::get

Döndürür IDWriteTextLayout arabirimi

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Bir IDWriteTextLayout arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="getfontfamilyname"></a>  CD2DTextLayout::GetFontFamilyName

Belirtilen konumda metin yazı tipi ailesinin adı kopyalar.

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Parametreler

*currentPosition*<br/>
İncelemek için metin konumu.

*TextRange*<br/>
CurrentPosition tarafından belirtilen konumdaki metni olarak aynı metin aralığını biçimlendirme. Bu, çalışma konumu belirtildi, ancak bunlarla sınırlı olmamak yazı tipi ailesinin adı dahil olmak üzere tam biçimlendirme olduğu anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli yazı tipi ailesinin adı içeren CString nesne.

##  <a name="getlocalename"></a>  CD2DTextLayout::GetLocaleName

Belirtilen konumda metin yerel ayar adını alır.

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Parametreler

*currentPosition*<br/>
İncelemek için metin konumu.

*TextRange*<br/>
CurrentPosition tarafından belirtilen konumdaki metni olarak aynı metin aralığını biçimlendirme. Bu, çalışma konumu belirtildi, ancak bunlarla sınırlı olmamak yerel ayar adı dahil olmak üzere tam biçimlendirme olduğu anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli yerel ayar adını içeren CString nesne.

##  <a name="isvalid"></a>  CD2DTextLayout::IsValid

Kaynak geçerlilik denetimleri

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerli ise TRUE; Aksi durumda FALSE.

##  <a name="m_ptextlayout"></a>  CD2DTextLayout::m_pTextLayout

Bir IDWriteTextLayout işaretçisi.

```
IDWriteTextLayout* m_pTextLayout;
```

##  <a name="operator_idwritetextlayout_star"></a>  CD2DTextLayout::operator IDWriteTextLayout *

Döndürür IDWriteTextLayout arabirimi

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>Dönüş Değeri

Bir IDWriteTextLayout arabirimi veya nesne henüz başlatılmamışsa NULL işaretçisi.

##  <a name="recreate"></a>  CD2DTextLayout::ReCreate

Bir CD2DTextLayout yeniden oluşturur.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

##  <a name="setfontfamilyname"></a>  CD2DTextLayout::SetFontFamilyName

Belirtilen metin aralığı içinde metin ayarlar null ile sonlandırılmış yazı tipi ailesi adı

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Parametreler

*pwzFontFamilyName*<br/>
Metin dizesinin tamamı textRange tarafından belirtilen aralık içinde uygulandığı yazı tipi ailesi adı

*TextRange*<br/>
Bu değişiklik geçerli olduğu metin aralığı

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür

##  <a name="setlocalename"></a>  CD2DTextLayout::SetLocaleName

Belirtilen metin aralığı içinde metin için yerel ayar adına ayarlar

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Parametreler

*pwzLocaleName*<br/>
Bir yerel ayar null ile sonlandırılmış dize

*TextRange*<br/>
Bu değişiklik geçerli olduğu metin aralığı

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE döndürür. Aksi takdirde FALSE döndürür

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
