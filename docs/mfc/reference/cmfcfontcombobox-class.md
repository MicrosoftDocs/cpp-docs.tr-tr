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
ms.openlocfilehash: ccc4e545b2274d6dbb9989cfb9c047de819b8d32
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781308"
---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox sınıfı

`CMFCFontComboBox` Sınıfı yazı tiplerinin bir listesini içeren bir birleşik giriş kutusu denetimi oluşturur.

## <a name="syntax"></a>Sözdizimi

```
class CMFCFontComboBox : public CComboBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|Oluşturur bir `CMFCFontComboBox` nesne.|
|`CMFCFontComboBox::~CMFCFontComboBox`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCFontComboBox::CompareItem`|Geçerli yazı tipi birleşik giriş kutusu denetiminin sıralı liste kutusunda yeni bir öğe göreli konumunu belirlemek için framework tarafından çağırılır. (Geçersiz kılmaları [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|
|`CMFCFontComboBox::DrawItem`|Geçerli yazı tipi birleşik giriş kutusu denetiminde belirtilen öğeyi çizmek için framework tarafından çağırılır. (Geçersiz kılmaları [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|
|[CMFCFontComboBox::GetSelFont](#getselfont)|Şu anda seçili yazı hakkındaki bilgileri alır.|
|`CMFCFontComboBox::MeasureItem`|Geçerli yazı tipi birleşik giriş kutusu denetimi listede boyutların Windows bildirmek için framework tarafından çağırılır. (Geçersiz kılmaları [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|
|`CMFCFontComboBox::PreTranslateMessage`|Pencere iletileri için dağıtılmadan önce çevirir [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows işlevleri. (Geçersiz kılmaları [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCFontComboBox::SelectFont](#selectfont)|Yazı tipi birleşik giriş kutusu belirtilen ölçütlerle eşleşen bir yazıtipi seçer.|
|[CMFCFontComboBox::Setup](#setup)|Yazı tipi birleşik giriş kutusunun öğelerinin listesini başlatır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Framework öğesi etiketleri geçerli yazı tipi birleşik giriş kutusunda çizmek için kullanılacak yazı tipini belirtir.|

## <a name="remarks"></a>Açıklamalar

Kullanılacak bir `CMFCFontComboBox` nesne iletişim kutusunda, eklemek bir `CMFCFontComboBox` iletişim kutusu sınıfı için değişken. Ardından `OnInitDialog` yöntemi çağrısı iletişim kutusu sınıfının [CMFCFontComboBox::Setup](#setup) öğeleri Kombo kutusu denetiminin listesini başlatmak için yöntemi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxfontcombobox.h

##  <a name="cmfcfontcombobox"></a>  CMFCFontComboBox::CMFCFontComboBox

Oluşturur bir `CMFCFontComboBox` nesne.

```
CMFCFontComboBox();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getselfont"></a>  CMFCFontComboBox::GetSelFont

Şu anda seçili yazı hakkındaki bilgileri alır.

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi [Cmfcfontınfo sınıfı](../../mfc/reference/cmfcfontinfo-class.md) bir yazı tipi tanımlayan nesne. Yazı tipi birleşik giriş kutusunda seçili değilse, NULL olabilir.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_bdrawusingfont"></a>  CMFCFontComboBox::m_bDrawUsingFont

Framework öğesi etiketleri geçerli yazı tipi birleşik giriş kutusunda çizmek için kullanılacak yazı tipini belirtir.

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>Açıklamalar

Bu üye, her bir öğe etiketini çizmek için aynı yazı tipi kullanılacak framework yönlendirmek için TRUE olarak ayarlayın. Bu üye adı etiketi aynı olan yazı tipi ile her bir öğe etiketini çizilmesi gerektiğinde framework yönlendirmek için FALSE ayarlayın. Bu üyenin varsayılan değeri FALSE olduğunda.

##  <a name="selectfont"></a>  CMFCFontComboBox::SelectFont

Yazı tipi birleşik giriş kutusu belirtilen ölçütlerle eşleşen bir yazıtipi seçer.

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>Parametreler

*pDesc*<br/>
[in] Bir yazı tipi açıklama nesnesi işaret eder.

*lpszName*<br/>
[in] Bir yazı tipi adı belirtir.

*nCharSet*<br/>
[in] Bir karakter kümesini belirtir. DEFAULT_CHARSET varsayılan değerdir. Daha fazla bilgi için `lfCharSet` üyesi [LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi birleşik giriş kutusundan bir öğe belirtilen yazı tipi açıklama nesne veya yazı tipi adı ve charset eşleşmesi durumunda TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Seçin ve belirtilen yazı tipinin karşılık gelen yazı tipi birleşik giriş kutusu öğenin kaydırma yapmak için bu yöntemi kullanın.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `SelectFont` yönteminde `CMFCFontComboBox` sınıfı. Bu örneğin parçasıdır [yeni denetimler örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

##  <a name="setup"></a>  CMFCFontComboBox::Setup

Yazı tipi birleşik giriş kutusunun öğelerinin listesini başlatır.

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>Parametreler

*nFontType*<br/>
[in] Yazı tipini belirtir. Bit düzeyinde birleşimi (veya) DEVICE_FONTTYPE RASTER_FONTTYPE ve TRUETYPE_FONTTYPE varsayılan değerdir.

*nCharSet*<br/>
[in] Yazı tipi karakter kümesini belirtir. DEFAULT_CHARSET varsayılan değerdir.

*nPitchAndFamily*<br/>
[in] Aile ve yazı tipi sıklıktaki değişimi belirtir. DEFAULT_PITCH varsayılan değerdir.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi birleşik giriş kutusu başarıyla başlatıldığında TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen parametrelerle eşleşen yüklü yazı tiplerini numaralandırma ve yazı tipi birleşik giriş kutusunda Bu yazı tipi adları ekleme yazı tipi birleşik giriş kutusu başlatır.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `Setup` yönteminde `CMFCFontComboBox` sınıfı. Bu örneğin parçasıdır [yeni denetimler örnek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarFontComboBox Sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCFontInfo Sınıfı](../../mfc/reference/cmfcfontinfo-class.md)
