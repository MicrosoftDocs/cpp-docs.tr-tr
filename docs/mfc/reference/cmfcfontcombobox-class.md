---
title: CMFCFontComboBox Sınıfı
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
ms.openlocfilehash: 60b4b7cdfdace2332de35dd93c43eacf592e99e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367499"
---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox Sınıfı

Sınıf, `CMFCFontComboBox` yazı tiplerinin listesini içeren bir açılan kutu denetimi oluşturur.

## <a name="syntax"></a>Sözdizimi

```
class CMFCFontComboBox : public CComboBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|Bir `CMFCFontComboBox` nesne inşa eder.|
|`CMFCFontComboBox::~CMFCFontComboBox`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CMFCFontComboBox::CompareItem`|Geçerli yazı tipi açılan kutusu denetiminin sıralanmış liste kutusunda yeni bir öğenin göreli konumunu belirlemek için çerçeve tarafından çağrılır. [(CComboBox geçersiz kılar::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|
|`CMFCFontComboBox::DrawItem`|Geçerli yazı tipi açılan kutusu denetiminde belirtilen bir öğeyi çizmek için çerçeve tarafından çağrılır. [(CComboBox geçersiz kılar::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|
|[CMFCFontComboBox::GetSelFont](#getselfont)|Şu anda seçili yazı tipi yle ilgili bilgileri alır.|
|`CMFCFontComboBox::MeasureItem`|Geçerli yazı tipi açılan kutusu denetiminde liste kutusunun boyutları Windows bilgilendirmek için çerçeve tarafından çağrılır. [(CComboBox geçersiz kılar::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|
|`CMFCFontComboBox::PreTranslateMessage`|Pencere iletilerini [Çeviri İletisi](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine gönderilmeden önce çevirir. [(CWnd geçersiz kılar::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCFontComboBox::SelectFont](#selectfont)|Yazı tipi açılan kutusundan belirtilen ölçütlerle eşleşen yazı tipini seçer.|
|[CMFCFontComboBox::Kurulum](#setup)|Yazı tipi açılan kutusundaki öğelerin listesini başolarak yanıtlar.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Geçerli yazı tipi açılan kutusunda madde etiketleri çizmek için hangi yazı tipi kullanmak için çerçeve gösterir.|

## <a name="remarks"></a>Açıklamalar

İletişim kutusundaki bir `CMFCFontComboBox` nesneyi kullanmak `CMFCFontComboBox` için iletişim kutusu sınıfına bir değişken ekleyin. Daha sonra `OnInitDialog` iletişim kutusu sınıfının yönteminde [CMFCFontComboBox'ı arayın::Açılan](#setup) kutu denetimindeki öğelerin listesini başlatma yöntemini başlatma yöntemini.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Ccombobox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxfontcombobox.h

## <a name="cmfcfontcomboboxcmfcfontcombobox"></a><a name="cmfcfontcombobox"></a>CMFCFontComboBox::CMFCFontComboBox

Bir `CMFCFontComboBox` nesne inşa eder.

```
CMFCFontComboBox();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfontcomboboxgetselfont"></a><a name="getselfont"></a>CMFCFontComboBox::GetSelFont

Şu anda seçili yazı tipi yle ilgili bilgileri alır.

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yazı tipini açıklayan [CMFCFontInfo Sınıfı](../../mfc/reference/cmfcfontinfo-class.md) nesnesine işaretçi. Açılan kutuda yazı tipi seçili değilse NULL olabilir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcfontcomboboxm_bdrawusingfont"></a><a name="m_bdrawusingfont"></a>CMFCFontComboBox::m_bDrawUsingFont

Geçerli yazı tipi açılan kutusunda madde etiketleri çizmek için hangi yazı tipi kullanmak için çerçeve gösterir.

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>Açıklamalar

Her madde etiketini çizmek için aynı yazı tipini kullanmak için çerçeveyi yönlendirmek için bu üyeyi TRUE olarak ayarlayın. Her madde etiketini, adı etiketle aynı olan yazı tipiyle çizmek için çerçeveyi yönlendirmek için bu üyeyi FALSE olarak ayarlayın. Bu üyenin varsayılan değeri FALSE'dur.

## <a name="cmfcfontcomboboxselectfont"></a><a name="selectfont"></a>CMFCFontComboBox::SelectFont

Yazı tipi açılan kutusundan belirtilen ölçütlerle eşleşen yazı tipini seçer.

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>Parametreler

*pDesc*<br/>
[içinde] Yazı tipi açıklaması nesnesine işaret edin.

*Lpszname*<br/>
[içinde] Bir yazı tipi adı belirtir.

*nCharSet*<br/>
[içinde] Bir karakter kümesi belirtir. Varsayılan değer DEFAULT_CHARSET. Daha fazla bilgi `lfCharSet` için [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) yapısının üyesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi açılan kutusundaki bir öğe belirtilen yazı tipi açıklaması nesnesi veya yazı tipi adı ve charset eşleşirse TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Belirtilen yazı tipine karşılık gelen yazı tipi açılan kutusundaöğe seçmek ve kaydırmak için bu yöntemi kullanın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemin sınıfta `SelectFont` nasıl `CMFCFontComboBox` kullanılacağını göstermektedir. Bu örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

## <a name="cmfcfontcomboboxsetup"></a><a name="setup"></a>CMFCFontComboBox::Kurulum

Yazı tipi açılan kutusundaki öğelerin listesini başolarak yanıtlar.

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>Parametreler

*nFontType*<br/>
[içinde] Yazı tipi türünü belirtir. Varsayılan değer, DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE bityönünde birleşimidir..

*nCharSet*<br/>
[içinde] Yazı tipi karakter kümesini belirtir. Varsayılan değer DEFAULT_CHARSET.

*nPitchAndFamily*<br/>
[içinde] Yazı tipi adımını ve ailesini belirtir. Varsayılan değer DEFAULT_PITCH.

### <a name="return-value"></a>Dönüş Değeri

Font açılan kutusu başarıyla başharfe basıldıysa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen parametrelerle eşleşen şu anda yüklü olan yazı tiplerini listeleyerek ve bu yazı tipi adlarını yazı tipi açılan kutusuna ekleyerek yazı tipi açılan kutusunu niçin başlattı.

### <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemin sınıfta `Setup` nasıl `CMFCFontComboBox` kullanılacağını göstermektedir. Bu örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox Sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCFontInfo Sınıfı](../../mfc/reference/cmfcfontinfo-class.md)
