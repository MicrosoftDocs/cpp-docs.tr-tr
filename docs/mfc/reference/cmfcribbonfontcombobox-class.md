---
description: 'Daha fazla bilgi edinin: CMFCRibbonFontComboBox sınıfı'
title: CMFCRibbonFontComboBox sınıfı
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
ms.openlocfilehash: 8a91f13f4e478512dfab3b9fcb942f96be0b9d9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333474"
---
# <a name="cmfcribbonfontcombobox-class"></a>CMFCRibbonFontComboBox sınıfı

Yazı tiplerinin bir listesini içeren bir Birleşik giriş kutusu uygular. Birleşik giriş kutusunu bir şerit paneline yerleştirebilirsiniz.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Yıkıcı.|

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonFontComboBox:: CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|Bir nesnesi oluşturur ve başlatır `CMFCRibbonFontComboBox` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonFontComboBox:: BuildFonts](#buildfonts)|Şerit yazı tipi Birleşik giriş kutusunu belirtilen yazı tipi türü, karakter kümesi ve Aralık ile aile yazı tipleriyle doldurur.|
|`CMFCRibbonFontComboBox::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|[CMFCRibbonFontComboBox:: GetCharSet](#getcharset)|Belirtilen karakter kümesini döndürür.|
|[CMFCRibbonFontComboBox:: GetFontDesc](#getfontdesc)||
|[CMFCRibbonFontComboBox:: GetFontType](#getfonttype)|Birleşik giriş kutusunda görüntülenecek yazı tipi türlerini döndürür. Geçerli seçenekler DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE ya da herhangi bir bit düzeyinde bileşimdir.|
|[CMFCRibbonFontComboBox:: Getstachandfamily](#getpitchandfamily)|Birleşik giriş kutusunda görüntülenen yazı tiplerinin aralığını ve ailesini döndürür.|
|`CMFCRibbonFontComboBox::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCRibbonFontComboBox:: RebuildFonts](#rebuildfonts)|Şerit yazı tipi Birleşik giriş kutusunu, daha önce belirtilen yazı tipi türü, karakter kümesi ve Aralık ile aile yazı tipleriyle doldurur.|
|[CMFCRibbonFontComboBox:: SetFont](#setfont)|Birleşik giriş kutusunda belirtilen yazı tipini seçer.|

## <a name="remarks"></a>Açıklamalar

Bir nesne oluşturduktan sonra `CMFCRibbonFontComboBox` , [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)öğesini çağırarak bir şerit paneline ekleyin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbondüğmesi](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

[CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribboncombobox. h

## <a name="cmfcribbonfontcomboboxbuildfonts"></a><a name="buildfonts"></a> CMFCRibbonFontComboBox:: BuildFonts

Şeritteki Birleşik giriş kutusunu yazı tipleriyle doldurur.

```cpp
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```

### <a name="parameters"></a>Parametreler

*nFontType*<br/>
'ndaki Eklenecek yazı tiplerinin yazı tipi türünü belirtir.

*nCharSet*<br/>
'ndaki Eklenecek yazı tiplerinin karakter kümesini belirtir.

*Nstachandfamily*<br/>
'ndaki Eklenecek yazı tiplerinin perdesini ve ailesini belirtir.

## <a name="cmfcribbonfontcomboboxcmfcribbonfontcombobox"></a><a name="cmfcribbonfontcombobox"></a> CMFCRibbonFontComboBox:: CMFCRibbonFontComboBox

Bir [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md) nesnesi oluşturur ve başlatır.

```
CMFCRibbonFontComboBox(
    UINT nID,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH,
    int nWidth = -1);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
'ndaki Kullanıcı açılan kutudan bir öğe seçtiğinde yürütülen komutun komut KIMLIĞI.

*nFontType*<br/>
'ndaki Birleşik giriş kutusunda hangi yazı tipi türlerinin gösterileceğini belirtir. Geçerli seçenekler DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE ya da herhangi bir bit düzeyinde bileşimdir.

*nCharSet*<br/>
'ndaki Birleşik giriş kutusundaki yazı tiplerini belirtilen karakter kümesine ait olanlarla filtreler.

*Nstachandfamily*<br/>
'ndaki Birleşik giriş kutusunda görüntülenen yazı tiplerinin perdesini ve ailesini belirtir.

*nWidth*<br/>
'ndaki Birleşik giriş kutusunun piksel cinsinden genişliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Olası *nFontType* parametre değerleri hakkında daha fazla bilgi için Windows SDK belgelerinde [EnumFontFamProc](/previous-versions/dd162621\(v=vs.85\)) bölümüne bakın.

*NCharSet*'e atanabilecek geçerli karakter kümeleri ve *Nstachandfamily*'e atanabilecek geçerli değerler hakkında daha fazla bilgi Için, Windows SDK belgelerindeki [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) bölümüne bakın.

## <a name="cmfcribbonfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a> CMFCRibbonFontComboBox:: GetFontDesc

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *IIndex*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonfontcomboboxrebuildfonts"></a><a name="rebuildfonts"></a> CMFCRibbonFontComboBox:: RebuildFonts

Şeritteki Birleşik giriş kutusunu, daha önce belirtilen bir yazı tipi türü, karakter kümesi ve Aralık ve aile yazı tipleriyle doldurur.

```cpp
void RebuildFonts();
```

### <a name="remarks"></a>Açıklamalar

Bu sınıfa ilişkin [kurucudaki](#cmfcribbonfontcombobox) Şerit yazı tipi Birleşik giriş kutusuna veya [CMFCRibbonFontComboBox:: BuildFonts](#buildfonts)' ı çağırarak yazı tiplerinin yazı tipi türünü, karakter kümesini ve perdesini ve türünü belirtebilirsiniz.

## <a name="cmfcribbonfontcomboboxsetfont"></a><a name="setfont"></a> CMFCRibbonFontComboBox:: SetFont

Birleşik giriş kutusunda belirtilen yazı tipini seçer.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet = DEFAULT_CHARSET,
    BOOL bExact = FALSE);
```

### <a name="parameters"></a>Parametreler

' lpszName * seçilecek yazı tipinin adını belirtir.

*nCharSet*<br/>
Seçilen yazı tipinin karakter kümesini belirtir.

*bTam*<br/>
Bir yazı tipi seçerken karakter kümesinin eşleşmesi gerektiğini belirtmek için TRUE; Bir yazı tipi seçerken karakter kümesinin yok sayılacağını belirtmek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen yazı tipi bulunursa ve seçiliyse sıfır dışı; Aksi takdirde, sıfır.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonfontcomboboxgetcharset"></a><a name="getcharset"></a> CMFCRibbonFontComboBox:: GetCharSet

Belirtilen karakter kümesini döndürür.

```
BYTE GetCharSet() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karakter kümesi (Windows SDK belgelerinde LOGFONT 'a bakın).

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonfontcomboboxgetfonttype"></a><a name="getfonttype"></a> CMFCRibbonFontComboBox:: GetFontType

Birleşik giriş kutusunda görüntülenecek yazı tipi türlerini döndürür. Geçerli seçenekler DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE ya da herhangi bir bit düzeyinde bileşimdir.

```
int GetFontType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi türleri (Windows SDK belgelerinde EnumFontFamProc bölümüne bakın).

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonfontcomboboxgetpitchandfamily"></a><a name="getpitchandfamily"></a> CMFCRibbonFontComboBox:: Getstachandfamily

Birleşik giriş kutusunda görüntülenen yazı tiplerinin aralığını ve ailesini döndürür.

```
BYTE GetPitchAndFamily() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıklık ve Aile (Windows SDK belgelerinde LOGFONT 'a bakın).

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonComboBox sınıfı](../../mfc/reference/cmfcribboncombobox-class.md)
