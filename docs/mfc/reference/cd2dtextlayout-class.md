---
title: CD2DTextLayout Sınıfı
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
ms.openlocfilehash: 9be4c1134e2f82ceb3af31cbeb1a7d55f4071777
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369035"
---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout Sınıfı

IDWriteTextLayout için bir sarmalayıcı.

## <a name="syntax"></a>Sözdizimi

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|CD2DTextLayout nesnesi oluşturuyor.|
|[CD2DTextLayout::~CD2DTextLayout](#_dtorcd2dtextlayout)|Yıkıcı. D2D metin düzeni nesnesi yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DTextLayout::Oluştur](#create)|CD2DTextLayout oluşturur. [(CD2DResource geçersiz kılar::Oluştur](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextLayout::Destroy](#destroy)|CD2DTextLayout nesnesini yok eder. (GEÇERSIZ Kılar [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextLayout::Get](#get)|IDWriteTextLayout arabirimini döndürür|
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|Belirtilen konumdaki metnin yazı tipi soyadını kopyalar.|
|[CD2DTextLayout::GetLocaleName](#getlocalename)|Belirtilen konumdametin yerel adını alır.|
|[CD2DTextLayout::Geçersiz](#isvalid)|Kaynak geçerliliğini denetler [(CD2DResource geçersiz kılar::Geçerlidir](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextLayout::Yeniden Oluşturma](#recreate)|CD2DTextLayout'ı yeniden oluşturur. [(CD2DResource geçersiz kılar::Yeniden Oluşturun](../../mfc/reference/cd2dresource-class.md#recreate).)|
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|Belirli bir metin aralığındaki metin için geçersiz sonlandırılmış yazı tipi aile adını ayarlar|
|[CD2DTextLayout::SetLocaleName](#setlocalename)|Belirli bir metin aralığındaki metnin yerel adını ayarlar|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CD2DTextLayout::operatör IDWriteTextLayout*](#operator_idwritetextlayout_star)|IDWriteTextLayout arabirimini döndürür|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CD2DTextLayout::m_pTextLayout](#m_ptextlayout)|IDWriteTextLayout için bir işaretçi.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CD2DKaynak](../../mfc/reference/cd2dresource-class.md)

[CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrendertarget.h

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="_dtorcd2dtextlayout"></a>CD2DTextLayout::~CD2DTextLayout

Yıkıcı. D2D metin düzeni nesnesi yok edilirken çağrılır.

```
virtual ~CD2DTextLayout();
```

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="cd2dtextlayout"></a>CD2DTextLayout::CD2DTextLayout

CD2DTextLayout nesnesi oluşturuyor.

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
İşleme hedefine işaretçi.

*strText*<br/>
Yeni bir CD2DTextLayout nesnesi oluşturmak için dize içeren bir CString nesnesi.

*Metinbiçimi*<br/>
Dize uygulanacak biçimi içeren bir CString nesnesi.

*boyutMax*<br/>
Düzen kutusunun boyutu.

*bAutoDestroy*<br/>
Nesnenin sahibi (pParentTarget) tarafından yok edileceğini gösterir.

## <a name="cd2dtextlayoutcreate"></a><a name="create"></a>CD2DTextLayout::Oluştur

CD2DTextLayout oluşturur.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dtextlayoutdestroy"></a><a name="destroy"></a>CD2DTextLayout::Destroy

CD2DTextLayout nesnesini yok eder.

```
virtual void Destroy();
```

## <a name="cd2dtextlayoutget"></a><a name="get"></a>CD2DTextLayout::Get

IDWriteTextLayout arabirimini döndürür

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe yazılmazsa, IDWriteTextLayout arabirimini işaretçiveya NULL.

## <a name="cd2dtextlayoutgetfontfamilyname"></a><a name="getfontfamilyname"></a>CD2DTextLayout::GetFontFamilyName

Belirtilen konumdaki metnin yazı tipi soyadını kopyalar.

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Parametreler

*Currentposition*<br/>
İncelecek metnin konumu.

*Textrange*<br/>
CurrentPosition tarafından belirtilen konumdaki metinle aynı biçimlendirmeye sahip metin aralığı. Bu, çalışma yazı tipi aile adı dahil ancak bunlarla sınırlı olmamak üzere belirtilen konum olarak tam biçimlendirmeye sahip olduğu anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli yazı tipi aile adını içeren CString nesnesi.

## <a name="cd2dtextlayoutgetlocalename"></a><a name="getlocalename"></a>CD2DTextLayout::GetLocaleName

Belirtilen konumdametin yerel adını alır.

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Parametreler

*Currentposition*<br/>
İncelenecek metnin konumu.

*Textrange*<br/>
CurrentPosition tarafından belirtilen konumdaki metinle aynı biçimlendirmeye sahip metin aralığı. Bu, çalıştırmanın yerel ad dahil ancak bunlarla sınırlı olmamak üzere belirtilen konum olarak tam biçimlendirmeye sahip olduğu anlamına gelir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli yerel ad içeren CString nesnesi.

## <a name="cd2dtextlayoutisvalid"></a><a name="isvalid"></a>CD2DTextLayout::Geçersiz

Kaynak geçerliliğini denetler

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak geçerliyse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cd2dtextlayoutm_ptextlayout"></a><a name="m_ptextlayout"></a>CD2DTextLayout::m_pTextLayout

IDWriteTextLayout için bir işaretçi.

```
IDWriteTextLayout* m_pTextLayout;
```

## <a name="cd2dtextlayoutoperator-idwritetextlayout"></a><a name="operator_idwritetextlayout_star"></a>CD2DTextLayout::operatör IDWriteTextLayout*

IDWriteTextLayout arabirimini döndürür

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne henüz başharfe yazılmazsa, IDWriteTextLayout arabirimini işaretçiveya NULL.

## <a name="cd2dtextlayoutrecreate"></a><a name="recreate"></a>CD2DTextLayout::Yeniden Oluşturma

CD2DTextLayout'ı yeniden oluşturur.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, S_OK döndürür. Aksi takdirde, bir HRESULT hata kodu döndürür.

## <a name="cd2dtextlayoutsetfontfamilyname"></a><a name="setfontfamilyname"></a>CD2DTextLayout::SetFontFamilyName

Belirli bir metin aralığındaki metin için geçersiz sonlandırılmış yazı tipi aile adını ayarlar

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Parametreler

*pwzFontFamilyName*<br/>
TextRange tarafından belirtilen aralıktaki tüm metin dizesi için geçerli olan yazı tipi aile adı

*Textrange*<br/>
Bu değişikliğin uygulandığı metin aralığı

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür

## <a name="cd2dtextlayoutsetlocalename"></a><a name="setlocalename"></a>CD2DTextLayout::SetLocaleName

Belirli bir metin aralığındaki metnin yerel adını ayarlar

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Parametreler

*pwzLocaleName*<br/>
Null-sonlandırılan yerel ad dizesi

*Textrange*<br/>
Bu değişikliğin uygulandığı metin aralığı

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, TRUE döndürür. Aksi takdirde, FALSE döndürür

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
