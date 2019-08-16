---
title: CMFCFontComboBox sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
ms.openlocfilehash: 69e8f81e7e01d0610f3cbf88ac1725a21d59838f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505293"
---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox sınıfı

Sınıfı `CMFCFontComboBox` , yazı tiplerinin bir listesini içeren bir Birleşik giriş kutusu denetimi oluşturur.

## <a name="syntax"></a>Sözdizimi

```
class CMFCFontComboBox : public CComboBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCFontComboBox:: CMFCFontComboBox](#cmfcfontcombobox)|Bir `CMFCFontComboBox` nesnesi oluşturur.|
|`CMFCFontComboBox::~CMFCFontComboBox`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCFontComboBox::CompareItem`|Geçerli yazı tipi Birleşik giriş kutusu denetiminin sıralanmış liste kutusunda yeni bir öğenin göreli konumunu öğrenmek için Framework tarafından çağırılır. ( [CComboBox:: CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).) öğesini geçersiz kılar|
|`CMFCFontComboBox::DrawItem`|Geçerli yazı tipi Birleşik giriş kutusu denetiminde belirtilen bir öğeyi çizmek için Framework tarafından çağırılır. ( [CComboBox geçersiz kılmaları::D rawitem](../../mfc/reference/ccombobox-class.md#drawitem).)|
|[CMFCFontComboBox:: GetSelFont](#getselfont)|Şu anda seçili olan yazı tipiyle ilgili bilgileri alır.|
|`CMFCFontComboBox::MeasureItem`|Geçerli yazı tipi Birleşik giriş kutusu denetimindeki liste kutusunun boyutlarını bilgilendirmek için Framework tarafından çağırılır. ( [CComboBox:: MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).) öğesini geçersiz kılar|
|`CMFCFontComboBox::PreTranslateMessage`|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini çevirir. ( [CWnd::P reTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)geçersiz kılar.)|
|[CMFCFontComboBox:: SelectFont](#selectfont)|Yazı tipi Birleşik giriş kutusundan belirtilen ölçütlerle eşleşen yazı tipini seçer.|
|[CMFCFontComboBox:: Kurulum](#setup)|Yazı tipi Birleşik giriş kutusundaki öğelerin listesini başlatır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCFontComboBox:: m_bDrawUsingFont](#m_bdrawusingfont)|Geçerli yazı tipi Birleşik giriş kutusunda öğe etiketlerini çizmek için kullanılacak yazı tipi çerçevesini gösterir.|

## <a name="remarks"></a>Açıklamalar

İletişim kutusunda bir `CMFCFontComboBox` nesne kullanmak için iletişim kutusu sınıfına bir `CMFCFontComboBox` değişken ekleyin. Ardından iletişim kutusu sınıfının yönteminde,BirleşikgirişkutusudenetimindekiöğelerinlistesinibaşlatmakiçinCMFCFontComboBox::Setupmetodunuçağırın.`OnInitDialog` [](#setup)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxfontcombobox. h

##  <a name="cmfcfontcombobox"></a>CMFCFontComboBox:: CMFCFontComboBox

Bir `CMFCFontComboBox` nesnesi oluşturur.

```
CMFCFontComboBox();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getselfont"></a>CMFCFontComboBox:: GetSelFont

Şu anda seçili olan yazı tipiyle ilgili bilgileri alır.

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yazı tipini açıklayan [CMFCFontInfo sınıfı](../../mfc/reference/cmfcfontinfo-class.md) nesnesine yönelik bir işaretçi. Birleşik giriş kutusunda hiçbir yazı tipi seçilmezse NULL olabilir.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_bdrawusingfont"></a>CMFCFontComboBox:: m_bDrawUsingFont

Geçerli yazı tipi Birleşik giriş kutusunda öğe etiketlerini çizmek için kullanılacak yazı tipi çerçevesini gösterir.

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>Açıklamalar

Çerçeveyi her öğe etiketini çizmek için aynı yazı tipini kullanmak üzere yönlendirmek için bu üyeyi TRUE olarak ayarlayın. Çerçeveyi her öğe etiketini, adı etiketle aynı olan yazı tipiyle çizilecek şekilde yönlendirmek için bu üyeyi FALSE olarak ayarlayın. Bu üyenin varsayılan değeri FALSE 'dur.

##  <a name="selectfont"></a>CMFCFontComboBox:: SelectFont

Yazı tipi Birleşik giriş kutusundan belirtilen ölçütlerle eşleşen yazı tipini seçer.

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>Parametreler

*pDesc*<br/>
'ndaki Yazı tipi açıklama nesnesine işaret eder.

*lpszName*<br/>
'ndaki Bir yazı tipi adı belirtir.

*nCharSet*<br/>
'ndaki Bir karakter kümesini belirtir. Varsayılan değer DEFAULT_CHARSET ' dir. Daha fazla bilgi için `lfCharSet` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi Birleşik giriş kutusundaki bir öğe belirtilen yazı tipi açıklama nesnesi veya yazı tipi adı ve karakter kümesi ile eşleşiyorsa TRUE. Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, belirtilen yazı tipine karşılık gelen yazı tipi Birleşik giriş kutusundaki öğeyi seçmek ve kaydırmak için kullanın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `SelectFont` `CMFCFontComboBox` sınıfında yönteminin nasıl kullanılacağını gösterir. Bu örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

##  <a name="setup"></a>CMFCFontComboBox:: Kurulum

Yazı tipi Birleşik giriş kutusundaki öğelerin listesini başlatır.

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>Parametreler

*nFontType*<br/>
'ndaki Yazı tipi türünü belirtir. Varsayılan değer, DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE bit düzeyinde birleşimidir (veya).

*nCharSet*<br/>
'ndaki Yazı tipi karakter kümesini belirtir. Varsayılan değer DEFAULT_CHARSET ' dir.

*Nstachandfamily*<br/>
'ndaki Yazı Tipi aralığını ve ailesini belirtir. Varsayılan değer DEFAULT_PITCH ' dir.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi Birleşik giriş kutusu başarıyla başlatılmışsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen parametrelerle eşleşen ve yazı tipi Birleşik giriş kutusuna bu yazı tipi adlarını ekleyerek yazı tipi Birleşik giriş kutusunu başlatır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `Setup` `CMFCFontComboBox` sınıfında yönteminin nasıl kullanılacağını gösterir. Bu örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox Sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCFontInfo Sınıfı](../../mfc/reference/cmfcfontinfo-class.md)
