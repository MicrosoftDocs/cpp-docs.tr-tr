---
title: CMFCFontInfo Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
helpviewer_keywords:
- CMFCFontInfo [MFC], GetFullName
- CMFCFontInfo [MFC], m_nCharSet
- CMFCFontInfo [MFC], m_nPitchAndFamily
- CMFCFontInfo [MFC], m_nType
- CMFCFontInfo [MFC], m_strName
- CMFCFontInfo [MFC], m_strScript
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
ms.openlocfilehash: 6e87971e2afefc9cf1574abe951920c254dcd2ae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367478"
---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo Sınıfı

Sınıf, `CMFCFontInfo` bir yazı tipinin adını ve diğer özniteliklerini açıklar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCFontInfo : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCFontInfo`|Bir `CMFCFontInfo` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCFontInfo::GetFullName](#getfullname)|Bir yazı tipinin ve karakter kümesinin (komut dosyası) concatenated adlarını alır.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|Yazı tipiile ilişkili karakter kümesini (komut dosyası) belirten bir değer.|
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|Yazı tipinin adımını ve ailesini belirten bir değer.|
|[CMFCFontInfo::m_nType](#m_ntype)|Yazı tipinin türünü belirten bir değer.|
|[CMFCFontInfo::m_strName](#m_strname)|Yazı tipinin adı; örneğin, **Arial**.|
|[CMFCFontInfo::m_strScript](#m_strscript)|Yazı tipi ile ilişkili bir karakter kümesi (komut dosyası) adı.|

## <a name="remarks"></a>Açıklamalar

`CMFCFontInfo` [CMFCToolBarFontComboBox Sınıfı'nın](../../mfc/reference/cmfctoolbarfontcombobox-class.md) bir öğesine bir nesne ekleyebilirsiniz. Bir `CMFCFontInfo` nesneye işaretçi almak için [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) yöntemini arayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın çeşitli üyelerinin nasıl `CMFCFontInfo` kullanılacağını göstermektedir. Örnek, bir `CMFCFontInfo` nesnenin bir 'den `CMFCRibbonFontComboBox`nasıl alınıldığını ve yerel değişkenlerine nasıl erişileni gösterir. Bu örnek, [MSOffice 2007 Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbarfontcombobox.h

## <a name="cmfcfontinfocmfcfontinfo"></a><a name="cmfcfontinfo"></a>CMFCFontInfo::CMFCFontInfo

Bir `CMFCFontInfo` nesne inşa eder.

```
CMFCFontInfo(
    LPCTSTR lpszName,
    LPCTSTR lpszScript,
    BYTE nCharSet,
    BYTE nPitchAndFamily,
    int nType);

CMFCFontInfo(const CMFCFontInfo& src);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
[içinde] Yazı tipinin adı. Daha fazla bilgi `lfFaceName` için [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyesine bakın.

*lpszScript*<br/>
[içinde] Yazı tipinin komut dosyasının adı (karakter kümesi).

*nCharSet*<br/>
[içinde] Yazı tipinin karakter kümesini (komut dosyası) belirten bir değer. Daha fazla bilgi `lfCharSet` için [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyesine bakın.

*nPitchAndFamily*<br/>
[içinde] Yazı tipinin adımını ve ailesini belirten bir değer. Daha fazla bilgi `lfPitchAndFamily` için [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyesine bakın.

*nTipi*<br/>
[içinde] Yazı tipi türünü belirten bir değer. Bu parametre, DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE bitwise birleşimi (OR) olabilir.

*src*<br/>
[içinde] Üyeleri `CMFCFontInfo` bu `CMFCFontInfo` nesneyi oluşturmak için kullanılan varolan bir nesne.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bu dokümantasyon, *karakter kümesi* ve *komut dosyası* terimlerini birbirinin yerine kullanır. Yazı sistemi olarak da bilinen *komut dosyası,* bu karakterleri bir veya daha fazla dilde yazmak için karakter ve kurallar topluluğudur. Karakter koleksiyonu, bu komut dosyasında kullanılan alfabe ve noktalama işaretlerini içerir. Örneğin, Latin alfabesi Abd'de konuşulduğu gibi İngilizce için kullanılır ve alfabesi A'dan Z'ye karakterleri içerir. `lfCharSet` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyesi bir karakter kümesi belirtir. Örneğin, ANSI_CHARSET değeri, Latin alfabesinin alfabesini içeren ANSI karakter kümesini belirtir.

## <a name="cmfcfontinfogetfullname"></a><a name="getfullname"></a>CMFCFontInfo::GetFullName

Bir yazı tipinin ve karakter kümesinin (komut dosyası) concatenated adlarını alır.

```
CString GetFullName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi adı ve komut dosyası içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Yazı tipinin tam adını elde etmek için bu yöntemi kullanın. Örneğin, yazı tipi adı **Arial** ve yazı tipi komut dosyası **Kiril**ise, bu yöntem "Arial (Kiril)" döndürür.

## <a name="cmfcfontinfom_ncharset"></a><a name="m_ncharset"></a>CMFCFontInfo::m_nCharSet

Yazı tipiile ilişkili karakter kümesini (komut dosyası) belirten bir değer.

```
const BYTE m_nCharSet;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) oluşturucunun *nCharSet* parametresini görün.

## <a name="cmfcfontinfom_npitchandfamily"></a><a name="m_npitchandfamily"></a>CMFCFontInfo::m_nPitchAndFamily

Yazı tipinin perdesini (nokta boyutunu) ve ailesini (örneğin, serif, sans-serif ve monospace) belirten bir değer.

```
const BYTE m_nPitchAndFamily;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) oluşturucunun *nPitchAndFamily* parametresini incegörün.

## <a name="cmfcfontinfom_ntype"></a><a name="m_ntype"></a>CMFCFontInfo::m_nType

Yazı tipinin türünü belirten bir değer.

```
const int m_nType;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) oluşturucunun *nType* parametresine bakın.

## <a name="cmfcfontinfom_strname"></a><a name="m_strname"></a>CMFCFontInfo::m_strName

Yazı tipinin adı: örneğin, **Arial**.

```
const CString m_strName;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) *oluşturuculpszName* parametreye bakın.

## <a name="cmfcfontinfom_strscript"></a><a name="m_strscript"></a>CMFCFontInfo::m_strScript

Yazı tipi ile ilişkili bir karakter kümesi (komut dosyası) adı.

```
const CString m_strScript;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) *oluşturuculpszScript* parametreye bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox Sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCToolBarFontSizeComboBox Sınıfı](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
