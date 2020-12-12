---
description: 'Daha fazla bilgi edinin: CMFCCaptionBar sınıfı'
title: CMFCCaptionBar sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
helpviewer_keywords:
- CMFCCaptionBar [MFC], Create
- CMFCCaptionBar [MFC], DoesAllowDynInsertBefore
- CMFCCaptionBar [MFC], EnableButton
- CMFCCaptionBar [MFC], GetAlignment
- CMFCCaptionBar [MFC], GetBorderSize
- CMFCCaptionBar [MFC], GetButtonRect
- CMFCCaptionBar [MFC], GetMargin
- CMFCCaptionBar [MFC], IsMessageBarMode
- CMFCCaptionBar [MFC], RemoveBitmap
- CMFCCaptionBar [MFC], RemoveButton
- CMFCCaptionBar [MFC], RemoveIcon
- CMFCCaptionBar [MFC], RemoveText
- CMFCCaptionBar [MFC], SetBitmap
- CMFCCaptionBar [MFC], SetBorderSize
- CMFCCaptionBar [MFC], SetButton
- CMFCCaptionBar [MFC], SetButtonPressed
- CMFCCaptionBar [MFC], SetButtonToolTip
- CMFCCaptionBar [MFC], SetFlatBorder
- CMFCCaptionBar [MFC], SetIcon
- CMFCCaptionBar [MFC], SetImageToolTip
- CMFCCaptionBar [MFC], SetMargin
- CMFCCaptionBar [MFC], SetText
- CMFCCaptionBar [MFC], OnDrawBackground
- CMFCCaptionBar [MFC], OnDrawBorder
- CMFCCaptionBar [MFC], OnDrawButton
- CMFCCaptionBar [MFC], OnDrawImage
- CMFCCaptionBar [MFC], OnDrawText
- CMFCCaptionBar [MFC], m_clrBarBackground
- CMFCCaptionBar [MFC], m_clrBarBorder
- CMFCCaptionBar [MFC], m_clrBarText
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
ms.openlocfilehash: a5dd5f968c52268935b6176115e8723a9d82e8a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327741"
---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar sınıfı

Bir `CMFCCaptionBar` nesne, üç öğe görüntüleyebilen bir denetim çubuğudur: düğme, metin etiketi ve bit eşlem. Tek seferde her bir türden yalnızca bir öğe görüntüleyebilir. Her öğeyi denetimin sol veya sağ kenarlarına veya merkezine hizalayabilirsiniz. Ayrıca, başlık çubuğunun üst ve alt kenarlıklarına düz veya 3B bir stil uygulayabilirsiniz.

## <a name="syntax"></a>Syntax

```
class CMFCCaptionBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCCaptionBar:: Create](#create)|Başlık çubuğu denetimini oluşturur ve `CMFCCaptionBar` nesneye ekler.|
|[CMFCCaptionBar::D Oesallowdynınsertbefore](#doesallowdyninsertbefore)|Başlık çubuğu ve onun üst çerçevesi arasında dinamik olarak bir bölme eklenip eklenmeyeceğini gösterir. ( [CBasePane::D Oesallowdynınsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore)geçersiz kılar.)|
|[CMFCCaptionBar:: EnableButton](#enablebutton)|Başlık çubuğundaki düğmeyi etkinleştirilir veya devre dışı bırakır.|
|[CMFCCaptionBar:: Gethizalaması](#getalignment)|Belirtilen öğenin hizalamasını döndürür.|
|[CMFCCaptionBar:: GetBorderSize](#getbordersize)|Başlık çubuğunun kenarlık boyutunu döndürür.|
|[CMFCCaptionBar:: GetButtonRect](#getbuttonrect)|Başlık çubuğundaki düğmenin sınırlayıcı dikdörtgenini alır.|
|[CMFCCaptionBar:: GetMargin](#getmargin)|Başlık çubuğu öğelerinin kenarı ve başlık çubuğu denetiminin kenarı arasındaki mesafeyi döndürür.|
|[CMFCCaptionBar:: ısmessagebarmode](#ismessagebarmode)|Başlık çubuğunun ileti çubuğu modunda olup olmadığını belirtir.|
|[CMFCCaptionBar:: Removebit eşlem](#removebitmap)|Resim yazısı çubuğundan bit eşlem resmini kaldırır.|
|[CMFCCaptionBar:: RemoveButton](#removebutton)|Düğmeyi başlık çubuğundan kaldırır.|
|[CMFCCaptionBar:: RemoveIcon](#removeicon)|Başlık çubuğundan simgeyi kaldırır.|
|[CMFCCaptionBar:: RemoveText](#removetext)|Başlık çubuğundan metin etiketini kaldırır.|
|[CMFCCaptionBar:: SetBit eşlem](#setbitmap)|Başlık çubuğu için bit eşlem resmini ayarlar.|
|[CMFCCaptionBar:: SetBorderSize](#setbordersize)|Başlık çubuğunun kenarlık boyutunu ayarlar.|
|[CMFCCaptionBar:: SetButton](#setbutton)|Başlık çubuğu için düğmeyi ayarlar.|
|[CMFCCaptionBar:: Setbuttonbasıldı](#setbuttonpressed)|Düğmenin basılı kalmasını belirtir.|
|[CMFCCaptionBar:: SetButtonToolTip](#setbuttontooltip)|Düğme için araç ipucunu ayarlar.|
|[CMFCCaptionBar:: Setyatayborder](#setflatborder)|Başlık çubuğunun kenarlık stilini ayarlar.|
|[CMFCCaptionBar:: SetIcon](#seticon)|Bir başlık çubuğunun simgesini ayarlar.|
|[CMFCCaptionBar:: Setımagetooltip](#setimagetooltip)|Başlık çubuğu için görüntünün araç ipucunu ayarlar.|
|[CMFCCaptionBar:: SetMargin](#setmargin)|Başlık çubuğu öğesinin kenarı ve başlık çubuğu denetiminin kenarı arasındaki mesafeyi ayarlar.|
|[CMFCCaptionBar:: SetText](#settext)|Başlık çubuğu için metin etiketini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCCaptionBar:: OnDrawBackground](#ondrawbackground)|Başlık çubuğunun arka planını dolduracak şekilde Framework tarafından çağırılır.|
|[CMFCCaptionBar:: OnDrawBorder](#ondrawborder)|Başlık çubuğunun kenarlığını çizmek için Framework tarafından çağırılır.|
|[CMFCCaptionBar:: OnDrawButton](#ondrawbutton)|Başlık çubuğu düğmesini çizmek için Framework tarafından çağırılır.|
|[CMFCCaptionBar:: OnDrawImage](#ondrawimage)|Başlık çubuğu görüntüsünü çizmek için Framework tarafından çağırılır.|
|[CMFCCaptionBar:: OnDrawText](#ondrawtext)|Başlık çubuğu metnini çizmek için Framework tarafından çağırılır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCCaptionBar:: m_clrBarBackground](#m_clrbarbackground)|Başlık çubuğunun arka plan rengi.|
|[CMFCCaptionBar:: m_clrBarBorder](#m_clrbarborder)|Başlık çubuğunun kenarlığının rengi.|
|[CMFCCaptionBar:: m_clrBarText](#m_clrbartext)|Başlık çubuğu metninin rengi.|

## <a name="remarks"></a>Açıklamalar

Bir başlık çubuğu oluşturmak için aşağıdaki adımları izleyin:

1. Nesnesini oluşturun `CMFCCaptionBar` . Genellikle, resim yazısı çubuğunu bir çerçeve pencere sınıfına eklersiniz.

1. Başlık çubuğu denetimini oluşturmak ve nesneye iliştirmek için [CMFCCaptionBar:: Create](#create) metodunu çağırın `CMFCCaptionBar` .

1. Başlık çubuğu öğelerini ayarlamak için [CMFCCaptionBar:: SetButton](#setbutton), CMFCCaptionBar:: [SetText](#settext), [CMFCCaptionBar:: SetIcon](#seticon)ve [CMFCCaptionBar:: SetBitmap](#setbitmap) çağırın.

Düğme öğesini ayarladığınızda, düğmeye bir komut KIMLIĞI atamanız gerekir. Kullanıcı düğmeye tıkladığında, başlık çubuğu bu KIMLIĞE sahip WM_COMMAND iletilerini üst çerçeve penceresine yönlendirir.

Başlık çubuğu, Microsoft Office 2007 uygulamalarında görüntülenen ileti çubuğuna öykünen ileti çubuğu modunda da çalışabilir. İleti çubuğu modunda, başlık çubuğu bir bit eşlem, bir ileti ve bir düğme (genellikle bir iletişim kutusu açar.) görüntüler. Bit eşleme bir araç ipucu atayabilirsiniz.

İleti çubuğu modunu etkinleştirmek için [CMFCCaptionBar:: Create](#create) ve dördüncü parametreyi (Bımessagebarmode) true olarak ayarlayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCCaptionBar` . Örnek, açıklamalı alt yazı çubuğu denetiminin nasıl oluşturulduğunu gösterir, başlık çubuğunun bir 3B kenarlığını ayarlama, kenar başlığı çubuğu öğelerinin kenarı ve başlık çubuğu çubuğunun kenarı arasındaki uzaklığı piksel olarak ayarlama, başlık çubuğu için düğmeyi ayarlama, düğme için araç ipucunu ayarlama, başlık çubuğu için metin etiketini ayarlama, başlık çubuğu için bit eşlem resmini ayarlama ve başlık çubuğundaki görüntünün araç ipucunu ayarlayın. Bu kod parçacığı, [MS Office 2007 demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcaptionbar. h

## <a name="cmfccaptionbarcreate"></a><a name="create"></a> CMFCCaptionBar:: Create

Başlık çubuğu denetimini oluşturur ve `CMFCCaptionBar` nesneye ekler.

```
BOOL Create(
    DWORD dwStyle,
    CWnd* pParentWnd,
    UINT uID,
    int nHeight=-1,
    BOOL bIsMessageBarMode=FALSE);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Başlık çubuğu stillerinin mantıksal veya birleşimi.

*pParentWnd*<br/>
Başlık çubuğu denetiminin üst penceresi.

*'Sini*<br/>
Başlık çubuğu denetiminin KIMLIĞI.

*nHeight*<br/>
Başlık çubuğu denetiminin piksel cinsinden yüksekliği. -1 ise, yükseklik simgenin yüksekliğine, metne ve başlık çubuğu denetiminin görüntülediği düğmeye göre hesaplanır.

*Bımessagebarmode*<br/>
Başlık çubuğu, ileti çubuğu modundaysa doğru; Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Başlık çubuğu denetimi başarıyla oluşturulursa doğru; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

`CMFCCaptionBar`İki adımda bir nesne oluşturursunuz. İlk olarak oluşturucuyu çağırın ve sonra `Create` Windows denetimini oluşturan ve bunu nesnesine ekleyen yöntemi çağırın `CMFCCaptionBar` .

## <a name="cmfccaptionbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCCaptionBar::D Oesallowdynınsertbefore

Başlık çubuğu ve onun üst çerçevesi arasında dinamik olarak bir bölme eklenip eklenmeyeceğini gösterir.

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçersiz kılınmadığı takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccaptionbarenablebutton"></a><a name="enablebutton"></a> CMFCCaptionBar:: EnableButton

Başlık çubuğundaki düğmeyi etkinleştirilir veya devre dışı bırakır.

```cpp
void EnableButton(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Düğmeyi etkinleştirmek için TRUE, düğmeyi devre dışı bırakmak için FALSE.

## <a name="cmfccaptionbargetalignment"></a><a name="getalignment"></a> CMFCCaptionBar:: Gethizalaması

Belirtilen öğenin hizalamasını döndürür.

```
BarElementAlignment GetAlignment(BarElement elem);
```

### <a name="parameters"></a>Parametreler

*elem*<br/>
'ndaki Hizalamasının alınacağı bir başlık çubuğu öğesi.

### <a name="return-value"></a>Dönüş Değeri

Bir düğme, bir bit eşlem, metin veya simge gibi bir öğenin hizalaması.

### <a name="remarks"></a>Açıklamalar

Öğesinin hizalaması aşağıdaki değerlerden biri olabilir:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbargetbordersize"></a><a name="getbordersize"></a> CMFCCaptionBar:: GetBorderSize

Başlık çubuğunun kenarlık boyutunu döndürür.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kenarlığın piksel cinsinden boyutu.

## <a name="cmfccaptionbargetbuttonrect"></a><a name="getbuttonrect"></a> CMFCCaptionBar:: GetButtonRect

Başlık çubuğundaki düğmenin sınırlayıcı dikdörtgenini alır.

```
CRect GetButtonRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CRect`Başlık çubuğundaki düğmenin sınırlayıcı dikdörtgeninin koordinatlarını içeren nesne.

## <a name="cmfccaptionbargetmargin"></a><a name="getmargin"></a> CMFCCaptionBar:: GetMargin

Başlık çubuğu öğelerinin kenarı ve başlık çubuğu denetiminin kenarı arasındaki mesafeyi döndürür.

```
int GetMargin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başlık çubuğu öğelerinin kenarı ve başlık çubuğu denetiminin kenarı arasındaki uzaklık (piksel cinsinden).

## <a name="cmfccaptionbarismessagebarmode"></a><a name="ismessagebarmode"></a> CMFCCaptionBar:: ısmessagebarmode

Başlık çubuğunun ileti çubuğu modunda olup olmadığını belirtir.

```
BOOL IsMessageBarMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başlık çubuğu, ileti çubuğu modundaysa doğru; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

İleti çubuğu modunda, başlık çubuğu bir araç ipucu, ileti metni ve bir düğme içeren bir görüntü görüntüler.

## <a name="cmfccaptionbarm_clrbarbackground"></a><a name="m_clrbarbackground"></a> CMFCCaptionBar:: m_clrBarBackground

Başlık çubuğunun arka plan rengi.

```
COLORREF m_clrBarBackground
```

## <a name="cmfccaptionbarm_clrbarborder"></a><a name="m_clrbarborder"></a> CMFCCaptionBar:: m_clrBarBorder

Başlık çubuğunun kenarlığının rengi.

```
COLORREF m_clrBarBorder
```

## <a name="cmfccaptionbarm_clrbartext"></a><a name="m_clrbartext"></a> CMFCCaptionBar:: m_clrBarText

Başlık çubuğu metninin rengi.

```
COLORREF m_clrBarText
```

## <a name="cmfccaptionbarondrawbackground"></a><a name="ondrawbackground"></a> CMFCCaptionBar:: OnDrawBackground

Başlık çubuğunun arka planını dolduracak şekilde Framework tarafından çağırılır.

```
virtual void OnDrawBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Başlık çubuğunun cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Doldurulacak sınırlayıcı dikdörtgen.

### <a name="remarks"></a>Açıklamalar

`OnDrawBackground`Başlık çubuğunun arka planının doldurulmak üzereyken yöntemi çağrılır. Varsayılan uygulama, [CMFCCaptionBar:: m_clrBarBackground](#m_clrbarbackground) rengini kullanarak arka planı doldurur.

`CMFCCaptionBar`Başlık çubuğunun görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccaptionbarondrawborder"></a><a name="ondrawborder"></a> CMFCCaptionBar:: OnDrawBorder

Başlık çubuğunun kenarlığını çizmek için Framework tarafından çağırılır.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Kenarlıkları göstermek için kullanılan bir cihaz bağlamı.

*Rect*<br/>
'ndaki Sınırlayıcı dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, kenarlıkların düz stili vardır.

`CMFCCaptionBar`Başlık çubuğu kenarlıklarının görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccaptionbarondrawbutton"></a><a name="ondrawbutton"></a> CMFCCaptionBar:: OnDrawButton

Başlık çubuğu düğmesini çizmek için Framework tarafından çağırılır.

```
virtual void OnDrawButton(
    CDC* pDC,
    CRect rect,
    const CString& strButton,
    BOOL bEnabled);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Düğmeyi göstermek için kullanılan cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Düğmenin sınırlayıcı dikdörtgeni.

*strButton*<br/>
'ndaki Düğmenin metin etiketi.

*bEnabled*<br/>
'ndaki Düğme etkinse doğru; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

`CMFCCaptionBar`Başlık çubuğunun düğmesinin görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccaptionbarondrawimage"></a><a name="ondrawimage"></a> CMFCCaptionBar:: OnDrawImage

Başlık çubuğu görüntüsünü çizmek için Framework tarafından çağırılır.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Görüntüyü göstermek için kullanılan cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Görüntünün sınırlayıcı dikdörtgenini belirtir.

### <a name="remarks"></a>Açıklamalar

`CMFCCaptionBar`Görüntü görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccaptionbarondrawtext"></a><a name="ondrawtext"></a> CMFCCaptionBar:: OnDrawText

Başlık çubuğu metnini çizmek için Framework tarafından çağırılır.

```
virtual void OnDrawText(
    CDC* pDC,
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Düğmeyi göstermek için kullanılan cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Metnin sınırlayıcı dikdörtgeni.

*strText*<br/>
'ndaki Görüntülenecek metin dizesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, `CDC::DrawText` ve [CMFCCaptionBar:: m_clrBarText](#m_clrbartext) Color kullanarak metni görüntüler.

`CMFCCaptionBar`Başlık çubuğu metninin görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccaptionbarremovebitmap"></a><a name="removebitmap"></a> CMFCCaptionBar:: Removebit eşlem

Resim yazısı çubuğundan bit eşlem resmini kaldırır.

```cpp
void RemoveBitmap();
```

## <a name="cmfccaptionbarremovebutton"></a><a name="removebutton"></a> CMFCCaptionBar:: RemoveButton

Düğmeyi başlık çubuğundan kaldırır.

```cpp
void RemoveButton();
```

### <a name="remarks"></a>Açıklamalar

Başlık çubuğu öğelerinin düzeni otomatik olarak ayarlanır.

## <a name="cmfccaptionbarremoveicon"></a><a name="removeicon"></a> CMFCCaptionBar:: RemoveIcon

Başlık çubuğundan simgeyi kaldırır.

```cpp
void RemoveIcon();
```

## <a name="cmfccaptionbarremovetext"></a><a name="removetext"></a> CMFCCaptionBar:: RemoveText

Başlık çubuğundan metin etiketini kaldırır.

```cpp
void RemoveText();
```

## <a name="cmfccaptionbarsetbitmap"></a><a name="setbitmap"></a> CMFCCaptionBar:: SetBit eşlem

Başlık çubuğu için bit eşlem resmini ayarlar.

```cpp
void SetBitmap(
    HBITMAP hBitmap,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

void SetBitmap(
    UINT uiBmpResID,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Parametreler

*HBITMAP*<br/>
'ndaki Ayarlanacak bit eşlemin tutamacı.

*clrTransparent*<br/>
'ndaki Bit eşlemin saydam rengini belirten bir RGB değeri.

*Besnetme*<br/>
'ndaki TRUE ise, görüntü sınırlayıcı dikdörtgenine uymuyorsa bit eşlem uzatılır. Aksi halde bit eşlem uzatılmamıştır.

*Bmphizalaması*<br/>
'ndaki Bit eşlemin hizalaması.

### <a name="remarks"></a>Açıklamalar

Bir resim yazısı çubuğunda bir bit eşlem ayarlamak için bu yöntemi kullanın.

Önceki bit eşlem otomatik olarak yok edilir. [CMFCCaptionBar:: SetIcon](#seticon) yöntemini çağırdığınız için başlık çubuğunda bir simge görüntüleniyorsa, [CMFCCaptionBar:: RemoveIcon](#removeicon)öğesini çağırarak simgeyi kaldırmadığınız takdirde bit eşlem görüntülenmez.

Bit eşlem *Bmphizalaması* parametresi tarafından belirtilen şekilde hizalanır.  Bu parametre aşağıdaki değerlerden biri olabilir `BarElementAlignment` :

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetbordersize"></a><a name="setbordersize"></a> CMFCCaptionBar:: SetBorderSize

Başlık çubuğunun kenarlık boyutunu ayarlar.

```cpp
void SetBorderSize(int nSize);
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
'ndaki Başlık çubuğu kenarlığının piksel cinsinden yeni boyutu.

## <a name="cmfccaptionbarsetbutton"></a><a name="setbutton"></a> CMFCCaptionBar:: SetButton

Başlık çubuğu için düğmeyi ayarlar.

```cpp
void SetButton(
    LPCTSTR lpszLabel,
    UINT uiCmdUI,
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,
    BOOL bHasDropDownArrow=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
Düğmenin komut etiketi.

*Uıımduı*<br/>
Düğmenin komut KIMLIĞI.

*btnAlignmnet*<br/>
Düğmenin hizalaması.

*Bhasdropdownok*<br/>
Düğme aşağı açılan bir ok görüntülüyorsa TRUE, aksi durumda FALSE.

## <a name="cmfccaptionbarsetbuttonpressed"></a><a name="setbuttonpressed"></a> CMFCCaptionBar:: Setbuttonbasıldı

Düğmenin basılı kalmasını belirtir.

```cpp
void SetButtonPressed(BOOL bPresed=TRUE);
```

### <a name="parameters"></a>Parametreler

*bPresed*<br/>
Düğme basılı durumunu koruduğunda TRUE, aksi takdirde FALSE.

## <a name="cmfccaptionbarsetbuttontooltip"></a><a name="setbuttontooltip"></a> CMFCCaptionBar:: SetButtonToolTip

Düğme için araç ipucunu ayarlar.

```cpp
void SetButtonToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszToolTip*<br/>
'ndaki Araç ipucu başlığı.

*lpszDescription*<br/>
'ndaki Araç ipucu açıklaması.

## <a name="cmfccaptionbarsetflatborder"></a><a name="setflatborder"></a> CMFCCaptionBar:: Setyatayborder

Başlık çubuğunun kenarlık stilini ayarlar.

```cpp
void SetFlatBorder(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>Parametreler

*bFlat*<br/>
'ndaki Başlık çubuğunun kenarlığı düz ise TRUE. Kenarlık 3B ise FALSE.

## <a name="cmfccaptionbarseticon"></a><a name="seticon"></a> CMFCCaptionBar:: SetIcon

Bir başlık çubuğunun simgesini ayarlar.

```cpp
void SetIcon(
    HICON hIcon,
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Parametreler

*HICON*<br/>
'ndaki Ayarlanacak simgenin tutamacı.

*Iconhizalaması*<br/>
'ndaki Simgenin hizalaması.

### <a name="remarks"></a>Açıklamalar

Başlık çubukları simgeler veya bit eşlemler gösterebilir. Bit eşlemin nasıl görüntüleneceğini öğrenmek için bkz. [CMFCCaptionBar:: SetBit eşlem](#setbitmap) . Hem bir simge hem de bit eşlem ayarlarsanız, simge her zaman görüntülenir. Bir simgeyi başlık çubuğundan kaldırmak için [CMFCCaptionBar:: RemoveIcon](#removeicon) öğesini çağırın.

Simge, *Iconhizalaması* parametresine göre hizalanır. Aşağıdaki değerlerden biri olabilir `BarElementAlignment` :

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetimagetooltip"></a><a name="setimagetooltip"></a> CMFCCaptionBar:: Setımagetooltip

Başlık çubuğundaki görüntünün araç ipucunu ayarlar.

```cpp
void SetImageToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszToolTip*<br/>
'ndaki Araç ipucunun metni.

*lpszDescription*<br/>
'ndaki Araç ipucu açıklaması.

## <a name="cmfccaptionbarsetmargin"></a><a name="setmargin"></a> CMFCCaptionBar:: SetMargin

Başlık çubuğu öğesinin kenarı ve başlık çubuğu denetiminin kenarı arasındaki mesafeyi ayarlar.

```cpp
void SetMargin(int nMargin);
```

### <a name="parameters"></a>Parametreler

*nMargin*<br/>
'ndaki Başlık çubuğu öğelerinin kenarı ve başlık çubuğu denetiminin kenarı arasındaki uzaklık (piksel cinsinden).

## <a name="cmfccaptionbarsettext"></a><a name="settext"></a> CMFCCaptionBar:: SetText

Başlık çubuğu için metin etiketini ayarlar.

```cpp
void SetText(
    const CString& strText,
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Parametreler

*strText*<br/>
'ndaki Ayarlanacak metin dizesi.

*textAlignment*<br/>
'ndaki Metin hizalaması.

### <a name="remarks"></a>Açıklamalar

Metin etiketi *TextAlignment* parametresi tarafından belirtilen şekilde hizalanır. Aşağıdaki değerlerden biri olabilir `BarElementAlignment` :

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
