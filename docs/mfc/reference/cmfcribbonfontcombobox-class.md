---
title: CMFCRibbonFontComboBox Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::BuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetCharSet
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontDesc
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontType
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetPitchAndFamily
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::RebuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::SetFont
helpviewer_keywords:
- CMFCRibbonFontComboBox [MFC], CMFCRibbonFontComboBox
- CMFCRibbonFontComboBox [MFC], BuildFonts
- CMFCRibbonFontComboBox [MFC], GetCharSet
- CMFCRibbonFontComboBox [MFC], GetFontDesc
- CMFCRibbonFontComboBox [MFC], GetFontType
- CMFCRibbonFontComboBox [MFC], GetPitchAndFamily
- CMFCRibbonFontComboBox [MFC], RebuildFonts
- CMFCRibbonFontComboBox [MFC], SetFont
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
ms.openlocfilehash: 822f4f6fe76bb5b82b455daec54ed96568ea6ba7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375160"
---
# <a name="cmfcribbonfontcombobox-class"></a>CMFCRibbonFontComboBox Sınıfı

Yazı tiplerinin listesini içeren bir açılan kutu uygular. Açılan kutuyu bir şerit panele yerlikir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Yıkıcı.|

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|Bir `CMFCRibbonFontComboBox` nesne yi inşa eder ve başharfe ait hale raz.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|Şerit yazı tipi açılan kutusunu, belirtilen yazı tipi türü, karakter kümesi ve pitch ve aile yazı tipleri ile doldurur.|
|`CMFCRibbonFontComboBox::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|Belirtilen karakter kümesini döndürür.|
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|Açılan kutuda görüntülenecek yazı tipi türlerini döndürür. Geçerli seçenekler DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE veya bunların herhangi bir bitwise kombinasyonu vardır.|
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|Açılan kutuda görüntülenen yazı tiplerinin perdeyi ve ailesini döndürür.|
|`CMFCRibbonFontComboBox::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|Şerit yazı tipi açılan kutusunu, önceden belirtilen yazı tipi, karakter kümesi ve pitch ve aile yazı tipleri ile doldurur.|
|[CMFCRibbonFontComboBox::SetFont](#setfont)|Açılan kutuda belirtilen yazı tipini seçer.|

## <a name="remarks"></a>Açıklamalar

Bir `CMFCRibbonFontComboBox` nesne oluşturduktan sonra CMFCRibbonPanel'i arayarak şerit paneline [ekleyin::Ekle.](../../mfc/reference/cmfcribbonpanel-class.md#add)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[Cmfcribbonedit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

[CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonComboBox.h

## <a name="cmfcribbonfontcomboboxbuildfonts"></a><a name="buildfonts"></a>CMFCRibbonFontComboBox::BuildFonts

Şeritteki açılan kutuyu yazı tipleri ile doldurur.

```
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```

### <a name="parameters"></a>Parametreler

*nFontType*<br/>
[içinde] Eklenecek yazı tiplerinin yazı tipi türünü belirtir.

*nCharSet*<br/>
[içinde] Eklenecek yazı tiplerinin karakter kümesini belirtir.

*nPitchAndFamily*<br/>
[içinde] Eklenecek yazı tiplerinin perdesini ve ailesini belirtir.

## <a name="cmfcribbonfontcomboboxcmfcribbonfontcombobox"></a><a name="cmfcribbonfontcombobox"></a>CMFCRibbonFontComboBox::CMFCRibbonFontComboBox

[CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md) nesnesi inşa eder ve başharflerini çözer.

```
CMFCRibbonFontComboBox(
    UINT nID,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH,
    int nWidth = -1);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
[içinde] Kullanıcı açılan kutudan bir öğe seçtiğinde çalıştıran komutun komut kimliği.

*nFontType*<br/>
[içinde] Açılan kutuda hangi yazı tipi türlerinin görüntüleneğin görüntüleneğin belirtin. Geçerli seçenekler DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE veya bunların herhangi bir bitwise kombinasyonu vardır.

*nCharSet*<br/>
[içinde] Açılan kutudaki yazı tiplerini belirtilen karakter kümesine ait olanlara filtreler...

*nPitchAndFamily*<br/>
[içinde] Açılan kutuda görüntülenen yazı tiplerinin perdesini ve ailesini belirtir.

*Nwidth*<br/>
[içinde] Açılan kutunun genişliğini, piksel olarak belirtir.

### <a name="remarks"></a>Açıklamalar

Olası *nFontType* parametre değerleri hakkında daha fazla bilgi için Windows SDK belgelerinde [EnumFontFamProc'a](/previous-versions/dd162621\(v=vs.85\)) bakın.

*nCharSet'e*atanabilen geçerli karakter kümeleri ve *nPitchAndFamily'ye*atanabilen geçerli değerler hakkında daha fazla bilgi için Windows SDK belgelerinde [LOGFONT'a](/windows/win32/api/wingdi/ns-wingdi-logfontw) bakın.

## <a name="cmfcribbonfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>CMFCRibbonFontComboBox::GetFontDesc

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *iIndex*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonfontcomboboxrebuildfonts"></a><a name="rebuildfonts"></a>CMFCRibbonFontComboBox::RebuildFonts

Şeritteki açılan kutuyu daha önce belirtilen yazı tipi, karakter kümesi ve pitch ve aile yazı tipleri ile doldurur.

```
void RebuildFonts();
```

### <a name="remarks"></a>Açıklamalar

Yazı tipi türünü, karakter kümesini ve yazı tipinin ailesini ve yazı tipi ailesini bu sınıfın [oluşturucusundaki](#cmfcribbonfontcombobox) şerit yazı tipi açılan kutusuna eklemek üzere veya [CMFCRibbonFontComboBox::BuildFonts'](#buildfonts)u arayarak belirtebilirsiniz.

## <a name="cmfcribbonfontcomboboxsetfont"></a><a name="setfont"></a>CMFCRibbonFontComboBox::SetFont

Açılan kutuda belirtilen yazı tipini seçer.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet = DEFAULT_CHARSET,
    BOOL bExact = FALSE);
```

### <a name="parameters"></a>Parametreler

'lpszName* Seçilecek yazı tipinin adını belirtir.

*nCharSet*<br/>
Seçili yazı tipi için karakter kümesini belirtir.

*bTam*<br/>
Bir yazı tipi seçerken karakter kümesinin eşmesi gerektiğini belirtmek için TRUE; Bir yazı tipi seçerken karakter kümesinin yoksayılabilir belirtmek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen yazı tipi bulunurve seçilirse sıfırolmayan; aksi takdirde, sıfır.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonfontcomboboxgetcharset"></a><a name="getcharset"></a>CMFCRibbonFontComboBox::GetCharSet

Belirtilen karakter kümesini döndürür.

```
BYTE GetCharSet() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karakter kümesi (Windows SDK belgelerinde LOGFONT'a bakın).

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonfontcomboboxgetfonttype"></a><a name="getfonttype"></a>CMFCRibbonFontComboBox::GetFontType

Açılan kutuda görüntülenecek yazı tipi türlerini döndürür. Geçerli seçenekler DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE veya bunların herhangi bir bitwise kombinasyonu vardır.

```
int GetFontType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi türleri (Bkz. Windows SDK belgelerinde EnumFontFamProc).

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonfontcomboboxgetpitchandfamily"></a><a name="getpitchandfamily"></a>CMFCRibbonFontComboBox::GetPitchAndFamily

Açılan kutuda görüntülenen yazı tiplerinin perdeyi ve ailesini döndürür.

```
BYTE GetPitchAndFamily() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pitch ve ailesi (Windows SDK belgelerinde LOGFONT'a bakın).

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonComboBox Sınıfı](../../mfc/reference/cmfcribboncombobox-class.md)
