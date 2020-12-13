---
description: 'Daha fazla bilgi edinin: CMFCToolBarFontComboBox sınıfı'
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
ms.openlocfilehash: 900da03bab8fdc95d93a9c92a14932d7a5bdd9ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331764"
---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox sınıfı

Kullanıcının bir sistem yazı listesi listesinden yazı tipi seçmesini sağlayan bir açılan kutu denetimi içeren bir araç çubuğu düğmesi.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontComboBox:: CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|Bir `CMFCToolBarFontComboBox` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolBarFontComboBox:: GetFontDesc](#getfontdesc)|`CMFCFontInfo`Birleşik giriş kutusundaki belirtilen dizin için nesneye bir işaretçi döndürür.|
|[CMFCToolBarFontComboBox:: SetFont](#setfont)|Yazı tipinin adına veya yazı tipinin önek ve karakter kümesine göre yazı tipi Birleşik giriş kutusunda bir yazı tipi seçer.|

### <a name="data-members"></a>Veri üyeleri

[CMFCToolBarFontComboBox:: m_nFontHeight](#m_nfontheight)<br/>
Yazı tipi Birleşik giriş kutusundaki karakterlerin yüksekliği.

## <a name="remarks"></a>Açıklamalar

Bir araç çubuğuna bir yazı tipi açılan kutusu düğmesi eklemek için aşağıdaki adımları izleyin:

1. Ana araç çubuğu kaynağında düğme için bir kukla kaynak KIMLIĞI ayırın.

1. Bir `CMFCToolBarFontComboBox` nesne oluşturun.

1. AFX_WM_RESETTOOLBAR iletisini işleyen ileti işleyicisinde, [CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)öğesini kullanarak özgün düğmesini Yeni Birleşik giriş kutusu düğmesiyle değiştirin.

1. Açılan kutuda seçilen yazı tipini, [CMFCToolBarFontComboBox:: SetFont](#setfont) yöntemini kullanarak belgedeki yazı tipiyle eşitler.

Belgenin yazı tipini Birleşik giriş kutusunda seçilen yazı tipiyle eşleştirmek için, [CMFCToolBarFontComboBox:: GetFontDesc](#getfontdesc) metodunu kullanarak seçilen yazı tipinin özniteliklerini alın ve bu öznitelikleri bir [CFont sınıfı](../../mfc/reference/cfont-class.md) nesnesi oluşturmak için kullanın.

Yazı tipi açılan kutusu düğmesi, sistem tarafından kullanılabilen ekran ve yazıcı yazı tiplerini öğrenmek için [EnumFontFamiliesEx](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesexw) Win32 işlevini çağırır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbarfontcombobox. h

## <a name="cmfctoolbarfontcomboboxcmfctoolbarfontcombobox"></a><a name="cmfctoolbarfontcombobox"></a> CMFCToolBarFontComboBox:: CMFCToolBarFontComboBox

[CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md) nesnesi oluşturur.

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

*Uııd*<br/>
'ndaki Birleşik giriş kutusunun komut KIMLIĞI.

*IImage*<br/>
'ndaki Bir araç çubuğu görüntüsünün sıfır tabanlı dizini. Resim, [CMFCToolBar sınıf](../../mfc/reference/cmfctoolbar-class.md) sınıfının tuttuğu [CMFCToolBarImages sınıfı](../../mfc/reference/cmfctoolbarimages-class.md) nesnesinde bulunur.

*nFontType*<br/>
'ndaki Birleşik giriş kutusunun içerdiği yazı tipi türleri. Bu parametre aşağıdaki değerlerden oluşan bir bileşim (Boolean veya) olabilir:

DEVICE_FONTTYPE

RASTER_FONTTYPE

TRUETYPE_FONTTYPE

*nCharSet*<br/>
'ndaki DEFAULT_CHARSET olarak ayarlanırsa, Birleşik giriş kutusu tüm karakter kümelerinde benzersiz olarak adlandırılan tüm yazı tiplerini içerir. (Aynı ada sahip iki yazı tipi varsa, Birleşik giriş kutusu bunlardan birini içerir.) Geçerli bir karakter kümesi değeri olarak ayarlanırsa, Birleşik giriş kutusu yalnızca belirtilen karakter kümesindeki yazı tiplerini içerir. Olası karakter kümelerinin listesi için bkz. [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) .

*dwStyle*<br/>
'ndaki Birleşik giriş kutusunun stili. (bkz. [Birleşik giriş kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles))

*ıwidth*<br/>
'ndaki Düzenleme denetiminin piksel cinsinden genişliği.

*Nstachandfamily*<br/>
'ndaki DEFAULT_PITCH olarak ayarlanırsa, Birleşik giriş kutusu, sıklıktaki bağımsız yazı tiplerini içerir. FIXED_PITCH veya VARIABLE_PITCH olarak ayarlanırsa, Birleşik giriş kutusu yalnızca bu Aralık türündeki yazı tiplerini içerir. Yazı tipi ailesini temel alan filtreleme şu anda desteklenmiyor.

*pLstFontsExternal*<br/>
dışı Kullanılabilir yazı tiplerini depolayan bir [CObList sınıfı](../../mfc/reference/coblist-class.md) nesnesine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Genellikle `CMFCToolBarFontComboBox` nesneler, kullanılabilir yazı tiplerinin listesini tek bir paylaşılan `CObList` nesnede depolar. Oluşturucunun ikinci aşırı yüklemesini kullanırsanız ve *pLstFontsExternal* için geçerli bir işaretçi sağlarsanız, bu `CMFCToolBarFontComboBox` nesne bunun yerine `CObList` Bu *pLstFontsExternal* noktalarını kullanılabilir yazı tipleriyle dolduracaktır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu gösterir `CMFCToolBarFontComboBox` . Bu kod parçacığı, [sözcük paneli örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]

## <a name="cmfctoolbarfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a> CMFCToolBarFontComboBox:: GetFontDesc

`CMFCFontInfo`Birleşik giriş kutusundaki belirtilen dizin için nesneye bir işaretçi döndürür.

```
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;
```

### <a name="parameters"></a>Parametreler

*IIndex*<br/>
'ndaki Birleşik giriş kutusu öğesinin sıfır tabanlı dizinini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir `CMFCFontInfo` nesne işaretçisi. *IIndex* geçerli bir öğe dizini belirtmezse, dönüş değeri null olur.

## <a name="cmfctoolbarfontcomboboxm_nfontheight"></a><a name="m_nfontheight"></a> CMFCToolBarFontComboBox:: m_nFontHeight

Birleşik giriş kutusunun sahip çizim stili varsa, yazı tipi Birleşik giriş kutusunda bulunan karakterlerin piksel cinsinden yüksekliğini belirtir.

```
static int m_nFontHeight
```

### <a name="remarks"></a>Açıklamalar

`m_nFontHeight`Değişken 0 ise, yükseklik Birleşik giriş kutusunun varsayılan yazı tipine göre otomatik olarak hesaplanır. Yükseklik, taban çizgisinin üzerindeki karakterlerin yokunu ve taban çizgisinin altındaki karakterlerin uzunluğunu içerir.

## <a name="cmfctoolbarfontcomboboxsetfont"></a><a name="setfont"></a> CMFCToolBarFontComboBox:: SetFont

Yazı tipi Birleşik giriş kutusundaki yazı tipini, parametrelerde belirtilen yazı tipi adına ve karakter kümesine göre seçer.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET,
    BOOL bExact=FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
'ndaki Yazı tipi adını veya önekini belirtir.

*nCharSet*<br/>
'ndaki Karakter kümesini belirtir.

*bTam*<br/>
'ndaki *LpszName* 'in yazı tipi adını mı yoksa yazı tipi önekini mı içerdiğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi başarıyla seçildiyse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*BTAM* doğru ise, bu yöntem *lpszName* olarak belirttiğiniz adla tam olarak eşleşen bir yazı tipi seçer. *BTam* değeri false ise, bu yöntem *lpszName* olarak belirtilen metinle başlayan ve *nCharSet* olarak belirttiğiniz karakter kümesini kullanan bir yazı tipi seçer. *NCharSet* DEFAULT_CHARSET olarak ayarlandıysa, karakter kümesi yok sayılır ve yalnızca *lpszName* bir yazı tipi seçmek için kullanılacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton sınıfı](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo sınıfı](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[İzlenecek yol: araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
