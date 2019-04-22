---
title: CMFCToolBarFontComboBox sınıfı
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
ms.openlocfilehash: 89767a3ed6880703c3c754700ea5669c0cc183e5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58779202"
---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox sınıfı

Sistem yazı tiplerini listesinden bir yazı tipi seçmek kullanıcının sağlayan bir birleşik giriş kutusu denetimi içeren bir araç çubuğu düğmesi.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|Oluşturur bir `CMFCToolBarFontComboBox` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|Bir işaretçi döndürür `CMFCFontInfo` birleşik giriş kutusunda belirtilen dizin için nesne.|
|[CMFCToolBarFontComboBox::SetFont](#setfont)|Yazı tipinin adını ya da yazı tipini öneki ve karakter kümesini yazı tipi birleşik giriş kutusundaki göre ya da bir yazıtipi seçer.|

### <a name="data-members"></a>Veri üyeleri

[CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)<br/>
Yazı tipi birleşik giriş kutusundaki karakterler yüksekliği.

## <a name="remarks"></a>Açıklamalar

Bir yazı tipi birleşik giriş kutusu düğmesi için araç çubuğu eklemek için bu adımları izleyin:

1. Üst araç çubuğunda kaynağında düğme için bir işlevsiz kaynak kimliği saklı tutarız.

1. Oluşturmak bir `CMFCToolBarFontComboBox` nesne.

1. Yeni bir birleşik giriş kutusu düğmesi ile özgün düğmesini kullanarak AFX_WM_RESETTOOLBAR iletiyi işleyen ileti işleyicisi değiştirin [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

1. Yazı tipi birleşik giriş kutusuna belgenin yazı tipi ile kullanarak seçili eşitleme [CMFCToolBarFontComboBox::SetFont](#setfont) yöntemi.

Belgenin yazı tipi birleşik giriş kutusunda seçili yazı tipi ile eşitlemek için kullanın [CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc) seçili yazı tipinin öznitelikleri almak ve oluşturmak için öznitelikleri kullanmak için yöntemi bir [ CFont sınıfı](../../mfc/reference/cfont-class.md) nesne.

Yazı tipi birleşik giriş kutusu düğmesi Win32 işlevini çağırır [EnumFontFamiliesEx](/windows/desktop/api/wingdi/nf-wingdi-enumfontfamiliesexa) ekran ve yazıcı yazı sistemi için kullanılabilir belirlemek için.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtoolbarfontcombobox.h

##  <a name="cmfctoolbarfontcombobox"></a>  CMFCToolBarFontComboBox::CMFCToolBarFontComboBox

Oluşturur bir [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md) nesne.

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
[in] Birleşik giriş kutusu komut kimliği.

*iImage*<br/>
[in] Bir araç çubuğu görüntüsü sıfır tabanlı dizini. Görüntüsü bulunan [Cmfctoolbarımages sınıfı](../../mfc/reference/cmfctoolbarimages-class.md) nesnesinin [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md) sınıfı tutar.

*nFontType*<br/>
[in] Birleşik giriş kutusu içeren yazı tipleri türleri. Bu parametre aşağıdaki değerlerden (mantıksal veya) birleşimi olabilir:

DEVICE_FONTTYPE

RASTER_FONTTYPE

TRUETYPE_FONTTYPE

*nCharSet*<br/>
[in] Tüm karakter kümelerindeki tüm benzersiz adlı yazı DEFAULT_CHARSET, birleşik giriş kutusu kümesine içeriyorsa. (Varsa aynı ada sahip iki yazı tipi birleşik giriş kutusu bunlardan biri içeriyor.) Yalnızca belirtilen karakter kümesini yazı tipi birleşik giriş kutusu bir geçersiz karakter kümesi değere ayarlanmış içeriyorsa. Bkz: [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) olası karakter bir listesi için ayarlar.

*dwStyle*<br/>
[in] Birleşik giriş kutusunun stili. (bkz [birleşik giriş kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles))

*iWidth*<br/>
[in] Düzenleme denetiminin piksel cinsinden genişliği.

*nPitchAndFamily*<br/>
[in] Küme DEFAULT_PITCH, birleşik giriş kutusu için yazı tiplerini aralık bakılmaksızın içeriyorsa. FIXED_PITCH veya VARIABLE_PITCH ayarlayın, birleşik giriş kutusu yalnızca bu aralık türü yazı tiplerini içeriyorsa. Yazı tipi ailesini temel alan filtre şu anda desteklenmiyor.

*pLstFontsExternal*<br/>
[out] İşaretçi bir [CObList sınıfı](../../mfc/reference/coblist-class.md) yazı tiplerini depolayan bir nesne.

### <a name="remarks"></a>Açıklamalar

Genellikle, `CMFCToolBarFontComboBox` nesneleri depolamak kullanılabilir yazı tiplerinin bir listesini tek bir paylaşılan `CObList` nesne. İkinci oluşturucu aşırı yüklemesini kullanın ve geçerli işaretçi sağlayan *pLstFontsExternal*, o `CMFCToolBarFontComboBox` nesne yerine doldurur `CObList` , *pLstFontsExternal* kullanılabilir yazı tipleri ile işaret eder.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCToolBarFontComboBox` nesne. Bu kod parçacığı parçasıdır [Word paneli örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]

##  <a name="getfontdesc"></a>  CMFCToolBarFontComboBox::GetFontDesc

Bir işaretçi döndürür `CMFCFontInfo` birleşik giriş kutusunda belirtilen dizin için nesne.

```
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;
```

### <a name="parameters"></a>Parametreler

*İIndex*<br/>
[in] Bir birleşik giriş kutusu öğesinin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `CMFCFontInfo` nesne. Varsa *İIndex* bir geçerli öğe dizini belirtmiyor döndürülen değer NULL olur.

##  <a name="m_nfontheight"></a>  CMFCToolBarFontComboBox::m_nFontHeight

Sahip çizim stili açılan kutusu varsa, yazı tipi birleşik giriş kutusundaki karakterler piksel cinsinden yüksekliğini belirtir.

```
static int m_nFontHeight
```

### <a name="remarks"></a>Açıklamalar

Varsa `m_nFontHeight` değişkeni 0 ise, yüksekliğini otomatik olarak varsayılan yazı tipi birleşik giriş kutusunun göre hesaplanır. Yüksekliği, taban çizgisinin karakter ascent hem iniş altında temel karakter içerir.

##  <a name="setfont"></a>  CMFCToolBarFontComboBox::SetFont

Yazı tipini yazı tipi birleşik giriş kutusunda yazı tipi adı ve karakter göre kümesi seçer parametrelerinde belirtilir.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET,
    BOOL bExact=FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
[in] Yazı tipi adı veya ön ekini belirtir.

*nCharSet*<br/>
[in] Karakter kümesini belirtir.

*bExact*<br/>
[in] Belirtir olup olmadığını *lpszName* yazı tipi adı veya yazı tipi ön ek içeriyor.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi başarıyla seçildiyse sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsa *bExact* doğru ise, bu yöntem, tam olarak belirtilen adla eşleşen bir yazı tipi seçer *lpszName*. Varsa *bExact* yanlış, metni ile başlayıp bir yazı tipi olarak belirtilen bu yöntemin seçer *lpszName* olarak belirtilen karakter kümesini kullanan ve *nCharSet*. Varsa *nCharSet* ayarlanır DEFAULT_CHARSET için yok sayıldı ve yalnızca karakter kümesi olacak *lpszName* bir yazı tipi seçmek için kullanılacak.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton Sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton Sınıfı](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo Sınıfı](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[İzlenecek yol: Araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
