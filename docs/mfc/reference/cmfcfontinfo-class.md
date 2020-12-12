---
description: 'Daha fazla bilgi edinin: CMFCFontInfo sınıfı'
title: CMFCFontInfo sınıfı
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
ms.openlocfilehash: 0922e07f268509cd4b5552a6123d8d3465a426bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265421"
---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo sınıfı

`CMFCFontInfo`Sınıfı, bir yazı tipinin adını ve diğer özniteliklerini açıklar.

## <a name="syntax"></a>Syntax

```
class CMFCFontInfo : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCFontInfo`|Bir `CMFCFontInfo` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCFontInfo:: GetFullName](#getfullname)|Yazı tipinin ve karakter kümesinin (betik) birleştirilmiş adlarını alır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCFontInfo:: m_nCharSet](#m_ncharset)|Yazı tipiyle ilişkili karakter kümesini (betiği) belirten bir değer.|
|[CMFCFontInfo:: m_nPitchAndFamily](#m_npitchandfamily)|Yazı tipinin perdesini ve ailesini belirten bir değer.|
|[CMFCFontInfo:: m_nType](#m_ntype)|Yazı tipinin türünü belirten bir değer.|
|[CMFCFontInfo:: m_strName](#m_strname)|Yazı tipinin adı; Örneğin, **Arial**.|
|[CMFCFontInfo:: m_strScript](#m_strscript)|Yazı tipiyle ilişkili bir karakter kümesi (betik) adı.|

## <a name="remarks"></a>Açıklamalar

`CMFCFontInfo` [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md) sınıfının bir öğesine bir nesne ekleyebilirsiniz. Bir nesnenin işaretçisini almak için [CMFCToolBarFontComboBox:: GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) metodunu çağırın `CMFCFontInfo` .

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının çeşitli üyelerini nasıl kullanacağınızı gösterir `CMFCFontInfo` . Örnek `CMFCFontInfo` , bir öğesinden bir nesnesinin nasıl alınacağını `CMFCRibbonFontComboBox` ve yerel değişkenlerine nasıl erişebileceğinizi gösterir. Bu örnek, [MSOffice 2007 demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbarfontcombobox. h

## <a name="cmfcfontinfocmfcfontinfo"></a><a name="cmfcfontinfo"></a> CMFCFontInfo:: CMFCFontInfo

Bir `CMFCFontInfo` nesnesi oluşturur.

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

*lpszName*<br/>
'ndaki Yazı tipinin adı. Daha fazla bilgi için `lfFaceName` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyesine bakın.

*lpszScript*<br/>
'ndaki Yazı tipinin (karakter kümesi) betiğinin adı.

*nCharSet*<br/>
'ndaki Yazı tipinin karakter kümesini (betiği) belirten bir değer. Daha fazla bilgi için `lfCharSet` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyesine bakın.

*Nstachandfamily*<br/>
'ndaki Yazı tipinin perdesini ve ailesini belirten bir değer. Daha fazla bilgi için `lfPitchAndFamily` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyesine bakın.

*nTür*<br/>
'ndaki Yazı tipi türünü belirten bir değer. Bu parametre, DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE bit düzeyinde bir bileşim (veya) olabilir.

*src*<br/>
'ndaki `CMFCFontInfo` Üyeleri bu nesneyi oluşturmak için kullanılan varolan bir nesne `CMFCFontInfo` .

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bu belgede terimler *karakter kümesi* ve *betiği* birbirinin yerine kullanılmaktadır. Yazma sistemi olarak da bilinen bir *komut dosyası*, bir veya daha fazla dilde bu karakterleri yazmak için bir karakter ve kural koleksiyonudur. Karakter koleksiyonu, bu betikte kullanılan alfabeyi ve noktalama işaretlerini içerir. Örneğin Latin betiği, Birleşik Devletler konuşulan Ingilizce için kullanılır ve alfabede A ile Z arasındaki karakterleri içerir. `lfCharSet` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyesi bir karakter kümesi belirtir. Örneğin değer ANSI_CHARSET, Latin betiğinin alfabesini içeren ANSI karakter kümesini belirtir.

## <a name="cmfcfontinfogetfullname"></a><a name="getfullname"></a> CMFCFontInfo:: GetFullName

Yazı tipinin ve karakter kümesinin (betik) birleştirilmiş adlarını alır.

```
CString GetFullName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi adını ve betiği içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Yazı tipinin tam adını almak için bu yöntemi kullanın. Örneğin, yazı tipi adı **Arial** ise ve yazı tipi komut dosyası **Kiril** ise, bu yöntem "Arial (Kiril)" değerini döndürür.

## <a name="cmfcfontinfom_ncharset"></a><a name="m_ncharset"></a> CMFCFontInfo:: m_nCharSet

Yazı tipiyle ilişkili karakter kümesini (betiği) belirten bir değer.

```
const BYTE m_nCharSet;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [CMFCFontInfo:: CMFCFontInfo](#cmfcfontinfo) oluşturucusunun *nCharSet* parametresi.

## <a name="cmfcfontinfom_npitchandfamily"></a><a name="m_npitchandfamily"></a> CMFCFontInfo:: m_nPitchAndFamily

Yazı tipinin (örneğin, serif, sans-serif ve tek aralıklı) boyutunu belirten bir değer.

```
const BYTE m_nPitchAndFamily;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [CMFCFontInfo:: CMFCFontInfo](#cmfcfontinfo) oluşturucusunun *Nstachandfamily* parametresi.

## <a name="cmfcfontinfom_ntype"></a><a name="m_ntype"></a> CMFCFontInfo:: m_nType

Yazı tipinin türünü belirten bir değer.

```
const int m_nType;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [CMFCFontInfo:: CMFCFontInfo](#cmfcfontinfo) oluşturucusunun *nType* parametresi.

## <a name="cmfcfontinfom_strname"></a><a name="m_strname"></a> CMFCFontInfo:: m_strName

Yazı tipinin adı: Örneğin, **Arial**.

```
const CString m_strName;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için, bkz. [CMFCFontInfo:: CMFCFontInfo](#cmfcfontinfo) oluşturucusunun *lpszName* parametresi.

## <a name="cmfcfontinfom_strscript"></a><a name="m_strscript"></a> CMFCFontInfo:: m_strScript

Yazı tipiyle ilişkili bir karakter kümesi (betik) adı.

```
const CString m_strScript;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için, bkz. [CMFCFontInfo:: CMFCFontInfo](#cmfcfontinfo) oluşturucusunun *lpszScript* parametresi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCToolBarFontSizeComboBox sınıfı](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
