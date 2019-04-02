---
title: CMFCFontInfo Class
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
ms.openlocfilehash: 930aceb4514195f0e844c35d326b52d9cd8d31fa
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781334"
---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo Class

`CMFCFontInfo` Sınıfı adı ve diğer bir yazı tipi özniteliklerini açıklar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCFontInfo : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCFontInfo`|Oluşturur bir `CMFCFontInfo` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCFontInfo::GetFullName](#getfullname)|Alır, birleştirilmiş bir yazı tipi ve kendi karakter adlarını (betik) ayarlayın.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|Yazı tipi ile ilişkilendirilmiş bir karakter kümesi (betik) belirten bir değeri.|
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|Yazı tipi ailesi ve aralık belirten bir değeri.|
|[CMFCFontInfo::m_nType](#m_ntype)|Yazı tipi türünü belirten bir değeri.|
|[CMFCFontInfo::m_strName](#m_strname)|Yazı tipi adı; Örneğin, **Arial**.|
|[CMFCFontInfo::m_strScript](#m_strscript)|Yazı tipi ile ilişkilendirilmiş bir karakter kümesi (betik) adı.|

## <a name="remarks"></a>Açıklamalar

İliştirebilmek için bir `CMFCFontInfo` nesnesinin bir öğesini [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md) sınıfı. Çağrı [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) yönteminin bir işaretçiye almak için bir `CMFCFontInfo` nesne.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli üyelerine nasıl gösterir `CMFCFontInfo` sınıfı. Bu örnek nasıl alındığını anlatan bir `CMFCFontInfo` nesnesinden bir `CMFCRibbonFontComboBox`ve kendi yerel değişkenlere erişmek nasıl. Bu örneğin parçasıdır [MSOFFICE 2007 Tanıtımı örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtoolbarfontcombobox.h

##  <a name="cmfcfontinfo"></a>  CMFCFontInfo::CMFCFontInfo

Oluşturur bir `CMFCFontInfo` nesne.

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
[in] Yazı tipi adı. Daha fazla bilgi için `lfFaceName` üyesi [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) yapısı.

*lpszScript*<br/>
[in] Yazı tipinin betik (karakter kümesi) adı.

*nCharSet*<br/>
[in] Yazı tipinin karakter kümesi (betik) belirten bir değeri. Daha fazla bilgi için `lfCharSet` üyesi [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) yapısı.

*nPitchAndFamily*<br/>
[in] Yazı tipi ailesi ve aralık belirten bir değeri. Daha fazla bilgi için `lfPitchAndFamily` üyesi [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) yapısı.

*nTür*<br/>
[in] Yazı tipi belirten bir değeri. Bu parametre karşılaştırmaya (veya) DEVICE_FONTTYPE RASTER_FONTTYPE ve TRUETYPE_FONTTYPE olabilir.

*src*<br/>
[in] Mevcut bir `CMFCFontInfo` üyeleri bu oluşturmak için kullanılan nesne `CMFCFontInfo` nesne.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

Bu belgede koşulları kullanılır *karakter kümesi* ve *betik* birbirinin yerine. A *betik*, olarak da bilinen bir yazma sistemi olduğu, karakterleri ve bu karakterleri bir veya daha fazla dilde yazmak için kuralları koleksiyonudur. Bu betikte kullanılan noktalama işaretleri ve alfabetik karakter koleksiyonunu içerir. Örneğin, Latin betik Amerika Birleşik Devletleri'nde konuşmalar ve kendi alfabetik A ile Z arasındaki karakterleri içeren İngilizce için kullanılır. `lfCharSet` Üyesi [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) yapısı bir karakter kümesini belirtir. Örneğin, ' % s'değeri ANSI_CHARSET Latin betiğin alfabetik içerir ANSI karakter kümesini belirtir.

##  <a name="getfullname"></a>  CMFCFontInfo::GetFullName

Alır, birleştirilmiş bir yazı tipi ve kendi karakter adlarını (betik) ayarlayın.

```
CString GetFullName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Betik ve yazı tipi adı içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Yazı tipi tam adını almak için bu yöntemi kullanın. Örneğin, yazı tipi adı ise **Arial** ve yazı tipi **Kiril**, "Arial (Kiril)" Bu yöntemi döndürür.

##  <a name="m_ncharset"></a>  CMFCFontInfo::m_nCharSet

Yazı tipi ile ilişkilendirilmiş bir karakter kümesi (betik) belirten bir değeri.

```
const BYTE m_nCharSet;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *nCharSet* parametresinin [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Oluşturucusu.

##  <a name="m_npitchandfamily"></a>  CMFCFontInfo::m_nPitchAndFamily

Aralık (nokta boyutu) ve yazı tipi ailesi (örneğin, serif, sans-serif ve tek aralıklı) belirten bir değeri.

```
const BYTE m_nPitchAndFamily;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *nPitchAndFamily* parametresinin [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Oluşturucusu.

##  <a name="m_ntype"></a>  CMFCFontInfo::m_nType

Yazı tipi türünü belirten bir değeri.

```
const int m_nType;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *nTür* parametresinin [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Oluşturucusu.

##  <a name="m_strname"></a>  CMFCFontInfo::m_strName

Yazı tipinin adını: Örneğin, **Arial**.

```
const CString m_strName;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *lpszName* parametresinin [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Oluşturucusu.

##  <a name="m_strscript"></a>  CMFCFontInfo::m_strScript

Yazı tipi ile ilişkilendirilmiş bir karakter kümesi (betik) adı.

```
const CString m_strScript;
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *lpszScript* parametresinin [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) Oluşturucusu.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox Sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCToolBarFontSizeComboBox Sınıfı](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
