---
title: CMFCToolBarFontComboBox Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::GetFontDesc
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::SetFont
helpviewer_keywords:
- CMFCToolBarFontComboBox [MFC], CMFCToolBarFontComboBox
- CMFCToolBarFontComboBox [MFC], GetFontDesc
- CMFCToolBarFontComboBox [MFC], SetFont
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
ms.openlocfilehash: 7b31f4b725a6983171162d9805d08224ad787808
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360462"
---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox Sınıfı

Kullanıcının sistem yazı tipleri listesinden yazı tipi ni seçmesini sağlayan açılan kutu denetimi içeren araç çubuğu düğmesi.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|Bir `CMFCToolBarFontComboBox` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|Açılan kutuda `CMFCFontInfo` belirtilen bir dizin için nesneye bir işaretçi döndürür.|
|[CMFCToolBarFontComboBox::SetFont](#setfont)|Yazı tipi nin adına veya yazı tipinin öneki ve karakter kümesine göre yazı tipi açılan kutusunda bir yazı tipi seçer.|

### <a name="data-members"></a>Veri Üyeleri

[CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)<br/>
Yazı tipi açılan kutusundaki karakterlerin yüksekliği.

## <a name="remarks"></a>Açıklamalar

Araç çubuğuna yazı tipi açılan kutusu düğmesi eklemek için aşağıdaki adımları izleyin:

1. Ana araç çubuğu kaynağındaki düğme için sahte bir kaynak kimliği ayırın.

1. Bir `CMFCToolBarFontComboBox` nesne oluştur.

1. AFX_WM_RESETTOOLBAR iletiyi işleyen ileti işleyicisinde, CMFCToolBar kullanarak orijinal düğmeyi yeni açılan kutu düğmesiyle [değiştirin::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

1. [CMFCToolBarFontComboBox::SetFont](#setfont) yöntemini kullanarak belgedeki yazı tipiyle açılan kutuda seçilen yazı tipini eşitleyin.

Belgenin yazı tipini açılan kutuda seçilen yazı tipiyle eşitlemek için [CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc) yöntemini kullanarak seçili yazı tipinin özniteliklerini alın ve [cfont sınıfı](../../mfc/reference/cfont-class.md) nesnesi oluşturmak için bu öznitelikleri kullanın.

Font açılan kutusu düğmesi, sistemin kullanabileceği ekran ve yazıcı yazı tiplerini belirlemek için Win32 işlevini [EnumFontFamiliesEx](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesexw) olarak arar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[Cmfctoolbarcomboboxbutton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbarfontcombobox.h

## <a name="cmfctoolbarfontcomboboxcmfctoolbarfontcombobox"></a><a name="cmfctoolbarfontcombobox"></a>CMFCToolBarFontComboBox::CMFCToolBarFontComboBox

[CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md) nesnesi oluşturuyor.

```
public:
CMFCToolBarFontComboBox(
    UINT uiID,
    int iImage,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    DWORD dwStyle = CBS_DROPDOWN,
    int iWidth = 0,
    BYTE nPitchAndFamily = DEFAULT_PITCH);

protected:
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,
    int nFontType,
    BYTE nCharSet,
    BYTE nPitchAndFamily);

CMFCToolBarFontComboBox();
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[içinde] Açılan kutunun komut kimliği.

*ıımage*<br/>
[içinde] Araç çubuğu görüntüsünün sıfır tabanlı dizini. Görüntü [CMFCToolBarClass](../../mfc/reference/cmfctoolbarimages-class.md) sınıfının koruduğu [CMFCToolBarImages](../../mfc/reference/cmfctoolbar-class.md) Sınıfı nesnesinde bulunur.

*nFontType*<br/>
[içinde] Açılan kutunun içerdiği yazı tipleri. Bu parametre aşağıdaki değerlerin bir kombinasyonu (boolean OR) olabilir:

DEVICE_FONTTYPE

RASTER_FONTTYPE

TRUETYPE_FONTTYPE

*nCharSet*<br/>
[içinde] DEFAULT_CHARSET olarak ayarlanmışsa, açılan kutu tüm karakter kümelerinde benzersiz adlandırılmış yazı tiplerini içerir. (Aynı ada sahip iki yazı tipi varsa, açılan kutu bunlardan birini içerir.) Geçerli bir karakter kümesi değerine ayarlanırsa, açılan kutu yalnızca belirtilen karakter kümesindeki yazı tiplerini içerir. Olası karakter kümelerinin listesi için [LOGFONT'a](/windows/win32/api/wingdi/ns-wingdi-logfontw) bakın.

*Dwstyle*<br/>
[içinde] Açılan kutunun stili. (bkz. [Combo-Box Stilleri)](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)

*iGenişlik*<br/>
[içinde] Denetimin piksellerinde genişlik.

*nPitchAndFamily*<br/>
[içinde] DEFAULT_PITCH olarak ayarlanmışsa, açılan kutu, perdeden bağımsız olarak yazı tipleri içerir. FIXED_PITCH veya VARIABLE_PITCH olarak ayarlanmışsa, açılan kutu yalnızca bu adım türüne sahip yazı tiplerini içerir. Yazı tipi ailesine göre filtreleme şu anda desteklenmez.

*pLstFontsExternal*<br/>
[çıkış] Kullanılabilir yazı tiplerini depolayan bir [CObList Sınıfı](../../mfc/reference/coblist-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Genellikle, `CMFCToolBarFontComboBox` nesneler kullanılabilir yazı tiplerinin listesini paylaşılan `CObList` tek bir nesnede saklar. Oluşturucunun ikinci aşırı yükünü kullanır ve *pLstFontsExternal*için geçerli `CMFCToolBarFontComboBox` bir işaretçi `CObList` sağlarsanız, bu nesne bunun yerine kullanılabilir yazı tipleri ile bu *pLstFontsExternal* noktaları dolduracaktır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCToolBarFontComboBox` nesnenin nasıl inşa edilebildiğini gösterir. Bu kod parçacığı Word Pad [örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]

## <a name="cmfctoolbarfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>CMFCToolBarFontComboBox::GetFontDesc

Açılan kutuda `CMFCFontInfo` belirtilen bir dizin için nesneye bir işaretçi döndürür.

```
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;
```

### <a name="parameters"></a>Parametreler

*ıındex*<br/>
[içinde] Açılan kutu öğesinin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir `CMFCFontInfo` nesneye işaretçi. *iIndex* geçerli bir madde dizini belirtmezse, iade değeri NULL'dur.

## <a name="cmfctoolbarfontcomboboxm_nfontheight"></a><a name="m_nfontheight"></a>CMFCToolBarFontComboBox::m_nFontHeight

Açılan kutusahibi çizim stili varsa, yazı tipi açılan kutusundaki karakterlerin yüksekliğini, pikselolarak belirtir.

```
static int m_nFontHeight
```

### <a name="remarks"></a>Açıklamalar

`m_nFontHeight` Değişken 0 ise, yükseklik açılan kutunun varsayılan yazı tipine göre otomatik olarak hesaplanır. Yükseklik, hem taban çizgisinin üzerindeki karakterlerin yükselişini hem de taban çizgisinin altındaki karakterlerin inişini içerir.

## <a name="cmfctoolbarfontcomboboxsetfont"></a><a name="setfont"></a>CMFCToolBarFontComboBox::SetFont

Font açılan kutusundaki yazı tipini parametrelerde belirtilen yazı tipi adı ve karakter kümesine göre seçer.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET,
    BOOL bExact=FALSE);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
[içinde] Yazı tipi adını veya önekini belirtir.

*nCharSet*<br/>
[içinde] Karakter kümesini belirtir.

*bTam*<br/>
[içinde] *lpszName'nin* yazı tipi adını mı yoksa yazı tipi önekini mi içerdiğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi başarıyla seçilirse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*bExact* TRUE ise, bu yöntem *lpszName*olarak belirttiğiniz adla tam olarak eşleşen bir yazı tipi seçer. *bExact* FALSE ise, bu yöntem *lpszName* olarak belirtilen metinle başlayan ve *nCharSet*olarak belirttiğiniz karakter kümesini kullanan bir yazı tipi seçer. *nCharSet* DEFAULT_CHARSET ayarlanırsa, karakter kümesi yoksayılır ve bir yazı tipi seçmek için yalnızca *lpszName* kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton Sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton Sınıfı](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo Sınıfı](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
