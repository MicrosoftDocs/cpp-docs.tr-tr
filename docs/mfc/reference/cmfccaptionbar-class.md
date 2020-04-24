---
title: CMFCCaptionBar Sınıfı
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
ms.openlocfilehash: c42b1ccb51a3c290e0887717d900543b8d5b277a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752621"
---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar Sınıfı

Nesne, `CMFCCaptionBar` üç öğeyi görüntüleyebilen bir denetim çubuğudur: bir düğme, metin etiketi ve bit eşlemi. Aynı anda her türden yalnızca bir öğe görüntüleyebilir. Her öğeyi denetimin sol veya sağ kenarlarına veya merkeze hizalayabilirsiniz. Resim yazısı çubuğunun üst ve alt kenarlıklarına düz veya 3B stil de uygulayabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
class CMFCCaptionBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCCaptionBar::Oluştur](#create)|Resim yazısı çubuğu denetimini oluşturur `CMFCCaptionBar` ve nesneye bağlar.|
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Resim yazısı çubuğu ile üst çerçevesi arasına dinamik olarak başka bir bölme eklenip eklenemeyeceğini gösterir. [(Overrides CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCCaptionBar::EnableButton](#enablebutton)|Resim yazısı çubuğundaki düğmeyi etkinleştirer veya devre dışı kılabilir.|
|[CMFCCaptionBar::GetAlignment](#getalignment)|Belirtilen öğenin hizalanmasını döndürür.|
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|Resim yazısı çubuğunun kenarlık boyutunu döndürür.|
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|Resim yazısı çubuğundaki düğmenin sınırlayıcı dikdörtgenini alır.|
|[CMFCCaptionBar::GetMargin](#getmargin)|Resim yazısı çubuğu elemanlarının kenarı ile resim yazısı çubuğu denetiminin kenarı arasındaki mesafeyi döndürür.|
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|Resim yazısı çubuğunun ileti çubuğu modunda olup olmadığını belirtir.|
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|Bitmap görüntüsünü resim yazısı çubuğundan kaldırır.|
|[CMFCCaptionBar::RemoveButton](#removebutton)|Başlığı çubuğundan düğmeyi kaldırır.|
|[CMFCCaptionBar::RemoveIcon](#removeicon)|Simgeyi resim yazısı çubuğundan kaldırır.|
|[CMFCCaptionBar::RemoveText](#removetext)|Metin etiketini resim yazısı çubuğundan kaldırır.|
|[CMFCCaptionBar::SetBitmap](#setbitmap)|Resim yazısı çubuğuiçin bit eşlem görüntüsünü ayarlar.|
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|Resim yazısı çubuğunun kenarlık boyutunu ayarlar.|
|[CMFCCaptionBar::SetButton](#setbutton)|Resim yazısı çubuğu için düğmeyi ayarlar.|
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|Düğmeye basılı kalıp kalmayacağını belirtir.|
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|Düğme için araç ucunu ayarlar.|
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|Resim yazısı çubuğunun kenarlık stilini ayarlar.|
|[CMFCCaptionBar::Seticon](#seticon)|Resim yazısı çubuğu simgesini ayarlar.|
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|Resim yazısı çubuğu için araç ucunu ayarlar.|
|[CMFCCaptionBar::SetMargin](#setmargin)|Resim yazısı çubuğu öğesinin kenarı ile resim yazısı çubuğu denetiminin kenarı arasındaki mesafeyi ayarlar.|
|[CMFCCaptionBar::SetText](#settext)|Resim yazısı çubuğu için metin etiketini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|Resim yazısı çubuğunun arka planını doldurmak için çerçeve tarafından çağrılır.|
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|Başlık çubuğunun kenarlığı çizmek için çerçeve tarafından çağrıldı.|
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|Resim yazısı çubuğu düğmesini çizmek için çerçeve tarafından çağrılır.|
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|Resim yazısı çubuğu görüntüsünü çizmek için çerçeve tarafından çağrılır.|
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|Resim yazısı çubuğu metnini çizmek için çerçeve tarafından çağrılır.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|Resim yazısı çubuğunun arka plan rengi.|
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|Resim yazısı çubuğunun kenarlığı rengi.|
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|Resim yazısı çubuğu metninin rengi.|

## <a name="remarks"></a>Açıklamalar

Resim yazısı çubuğu oluşturmak için aşağıdaki adımları izleyin:

1. Nesneyi `CMFCCaptionBar` oluştur. Genellikle, resim yazısı çubuğunu çerçeve penceresi sınıfına eklersiniz.

1. [CMFCCaptionBar'ı arayın::Resim](#create) yazısı çubuğu denetimini oluşturmak `CMFCCaptionBar` ve nesneye takmak için yöntem oluşturun.

1. [CMFCCaptionBar'ı Arayın::SetButton,](#setbutton) [CMFCCaptionBar::SetText](#settext), [CMFCCaptionBar::SetIcon](#seticon)ve [CMFCCaptionBar::Başlık](#setbitmap) çubuğu öğelerini ayarlamak için SetBitmap.

Düğme öğesini ayarladığınızda, düğmeye bir komut kimliği atamanız gerekir. Kullanıcı düğmeyi tıklattığında, resim yazısı çubuğu bu kimliği olan WM_COMMAND iletileri ana çerçeve penceresine yönlendirir.

Resim yazısı çubuğu, Microsoft Office 2007 uygulamalarında görünen ileti çubuğunu taklit eden ileti çubuğu modunda da çalışabilir. İleti çubuğu modunda, resim yazısı çubuğu bir bit eşlemi, ileti ve bir düğme görüntüler (genellikle bir iletişim kutusu açılır.) Bitmap'e bir araç ucu atayabilirsiniz.

İleti çubuğu modunu etkinleştirmek için [CMFCCaptionBar'ı arayın::Dördüncü](#create) parametreyi (bIsMessageBarMode) TRUE'ya ayarlayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCCaptionBar` nasıl kullanılacağını göstermektedir. Resim yazısı çubuğu denetiminin nasıl oluşturulup, resim yazısı çubuğunun 3B kenarını nasıl ayarlanın, mesafeyi piksel olarak ayarlayın, resim yazısı çubuğu elemanlarının kenarı ile resim yazısı çubuğu denetiminin kenarı arasında, resim yazısı çubuğu için düğmeyi ayarlayın, düğme için araç ipucunu ayarlayın, resim yazısı çubuğu için metin etiketini ayarlayın, resim yazısı çubuğu için bit map görüntüsünü ayarlayın ve resim çubuğundaki resim için araç ucunu ayarlayın. Bu kod parçacığı MS Office [2007 Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcaptionbar.h

## <a name="cmfccaptionbarcreate"></a><a name="create"></a>CMFCCaptionBar::Oluştur

Resim yazısı çubuğu denetimini oluşturur `CMFCCaptionBar` ve nesneye bağlar.

```
BOOL Create(
    DWORD dwStyle,
    CWnd* pParentWnd,
    UINT uID,
    int nHeight=-1,
    BOOL bIsMessageBarMode=FALSE);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Resim yazısı çubuğu stillerinin mantıksal OR birleşimi.

*pParentWnd*<br/>
Resim yazısı çubuğu denetiminin ana penceresi.

*Uıd*<br/>
Resim yazısı çubuğu denetiminin kimliği.

*Nheight*<br/>
Resim yazısı çubuğu denetiminin yüksekliği, piksel olarak. -1 ise, yükseklik simgenin yüksekliğine, metinve resim yazısı çubuğu denetiminin görüntülenebilen düğmesine göre hesaplanır.

*bIsMessageBarMode*<br/>
Resim yazısı çubuğu ileti çubuğu modundaysa TRUE; YANLIŞ aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

Resim yazısı çubuğu denetimi başarıyla oluşturulursa DOĞRU; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CMFCCaptionBar` iki adımda inşa ee. Önce oluşturucuyu ararsınız, sonra `Create` da Windows denetimini oluşturan ve `CMFCCaptionBar` nesneye iliştiren yöntemi çağırırsınız.

## <a name="cmfccaptionbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CMFCCaptionBar::DoesAllowDynInsertBefore

Resim yazısı çubuğu ile üst çerçevesi arasına dinamik olarak başka bir bölme eklenip eklenemeyeceğini gösterir.

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçersiz kılınmadığı sürece FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccaptionbarenablebutton"></a><a name="enablebutton"></a>CMFCCaptionBar::EnableButton

Resim yazısı çubuğundaki düğmeyi etkinleştirer veya devre dışı kılabilir.

```cpp
void EnableButton(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] DOĞRU düğmeyi etkinleştirmek için, FALSE düğmesini devre dışı.

## <a name="cmfccaptionbargetalignment"></a><a name="getalignment"></a>CMFCCaptionBar::GetAlignment

Belirtilen öğenin hizalanmasını döndürür.

```
BarElementAlignment GetAlignment(BarElement elem);
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
[içinde] Hizalama almak için bir resim yazısı çubuğu öğesi.

### <a name="return-value"></a>Dönüş Değeri

Düğme, bitmap, metin veya simge gibi bir öğenin hizalanması.

### <a name="remarks"></a>Açıklamalar

Öğenin hizalanması aşağıdaki değerlerden biri olabilir:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbargetbordersize"></a><a name="getbordersize"></a>CMFCCaptionBar::GetBorderSize

Resim yazısı çubuğunun kenarlık boyutunu döndürür.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kenarlık boyutu, piksel olarak.

## <a name="cmfccaptionbargetbuttonrect"></a><a name="getbuttonrect"></a>CMFCCaptionBar::GetButtonRect

Resim yazısı çubuğundaki düğmenin sınırlayıcı dikdörtgenini alır.

```
CRect GetButtonRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başlık `CRect` çubuğundaki düğmenin sınırlayıcı dikdörtgeninin koordinatlarını içeren bir nesne.

## <a name="cmfccaptionbargetmargin"></a><a name="getmargin"></a>CMFCCaptionBar::GetMargin

Resim yazısı çubuğu elemanlarının kenarı ile resim yazısı çubuğu denetiminin kenarı arasındaki mesafeyi döndürür.

```
int GetMargin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Piksel olarak, resim yazısı çubuğu öğelerinin kenarı ile resim yazısı çubuğu denetiminin kenarı arasındaki mesafe.

## <a name="cmfccaptionbarismessagebarmode"></a><a name="ismessagebarmode"></a>CMFCCaptionBar::IsMessageBarMode

Resim yazısı çubuğunun ileti çubuğu modunda olup olmadığını belirtir.

```
BOOL IsMessageBarMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Resim yazısı çubuğu ileti çubuğu modundaysa TRUE; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

İleti çubuğu modunda, resim yazısı çubuğunda araç ucu, ileti metni ve düğme içeren bir resim görüntülenir.

## <a name="cmfccaptionbarm_clrbarbackground"></a><a name="m_clrbarbackground"></a>CMFCCaptionBar::m_clrBarBackground

Resim yazısı çubuğunun arka plan rengi.

```
COLORREF m_clrBarBackground
```

## <a name="cmfccaptionbarm_clrbarborder"></a><a name="m_clrbarborder"></a>CMFCCaptionBar::m_clrBarBorder

Resim yazısı çubuğunun kenarlığı rengi.

```
COLORREF m_clrBarBorder
```

## <a name="cmfccaptionbarm_clrbartext"></a><a name="m_clrbartext"></a>CMFCCaptionBar::m_clrBarText

Resim yazısı çubuğu metninin rengi.

```
COLORREF m_clrBarText
```

## <a name="cmfccaptionbarondrawbackground"></a><a name="ondrawbackground"></a>CMFCCaptionBar::OnDrawBackground

Resim yazısı çubuğunun arka planını doldurmak için çerçeve tarafından çağrılır.

```
virtual void OnDrawBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Resim yazısı çubuğunun aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Doldurulması gereken sınırlayıcı dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Resim `OnDrawBackground` yazısı çubuğunun arka planı doldurulmak üzereyken yöntem çağrılır. Varsayılan uygulama [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) renk kullanarak arka planı doldurur.

Resim yazısı çubuğunun `CMFCCaptionBar` görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccaptionbarondrawborder"></a><a name="ondrawborder"></a>CMFCCaptionBar::OnDrawBorder

Başlık çubuğunun kenarlığı çizmek için çerçeve tarafından çağrıldı.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Kenarlıkları görüntülemek için kullanılan bir aygıt bağlamı.

*Rect*<br/>
[içinde] Sınırlayıcı dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, kenarlıklar düz stili vardır.

Resim yazısı çubuğunun `CMFCCaptionBar` kenarlıklarının görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccaptionbarondrawbutton"></a><a name="ondrawbutton"></a>CMFCCaptionBar::OnDrawButton

Resim yazısı çubuğu düğmesini çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDrawButton(
    CDC* pDC,
    CRect rect,
    const CString& strButton,
    BOOL bEnabled);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Düğmeyi görüntülemek için kullanılan aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Düğmenin sınırlayıcı dikdörtgeni.

*strButton*<br/>
[içinde] Düğmenin metin etiketi.

*bEtkin*<br/>
[içinde] Düğme etkinse TRUE; YANLIŞ aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Resim yazısı çubuğudüğmesinin görünümünü özelleştirmek için türetilmiş bir `CMFCCaptionBar` sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccaptionbarondrawimage"></a><a name="ondrawimage"></a>CMFCCaptionBar::OnDrawImage

Resim yazısı çubuğu görüntüsünü çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Görüntüyü görüntülemek için kullanılan aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Görüntünün sınırlayıcı dikdörtgenini belirtir.

### <a name="remarks"></a>Açıklamalar

Görüntü görünümünü özelleştirmek `CMFCCaptionBar` için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccaptionbarondrawtext"></a><a name="ondrawtext"></a>CMFCCaptionBar::OnDrawText

Resim yazısı çubuğu metnini çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDrawText(
    CDC* pDC,
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Düğmeyi görüntülemek için kullanılan aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Metnin sınırlayıcı dikdörtgeni.

*strText*<br/>
[içinde] Görüntülenecek metin dizesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama kullanarak `CDC::DrawText` metni görüntüler ve [CMFCCaptionBar::m_clrBarText](#m_clrbartext) renk.

Resim yazısı çubuğunun `CMFCCaptionBar` metninin görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccaptionbarremovebitmap"></a><a name="removebitmap"></a>CMFCCaptionBar::RemoveBitmap

Bitmap görüntüsünü resim yazısı çubuğundan kaldırır.

```cpp
void RemoveBitmap();
```

## <a name="cmfccaptionbarremovebutton"></a><a name="removebutton"></a>CMFCCaptionBar::RemoveButton

Başlığı çubuğundan düğmeyi kaldırır.

```cpp
void RemoveButton();
```

### <a name="remarks"></a>Açıklamalar

Resim yazısı çubuğu öğelerinin düzeni otomatik olarak ayarlanır.

## <a name="cmfccaptionbarremoveicon"></a><a name="removeicon"></a>CMFCCaptionBar::RemoveIcon

Simgeyi resim yazısı çubuğundan kaldırır.

```cpp
void RemoveIcon();
```

## <a name="cmfccaptionbarremovetext"></a><a name="removetext"></a>CMFCCaptionBar::RemoveText

Metin etiketini resim yazısı çubuğundan kaldırır.

```cpp
void RemoveText();
```

## <a name="cmfccaptionbarsetbitmap"></a><a name="setbitmap"></a>CMFCCaptionBar::SetBitmap

Resim yazısı çubuğuiçin bit eşlem görüntüsünü ayarlar.

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

*Hbıtmap*<br/>
[içinde] Ayarlanan bit eşlemi için tutamaç.

*clrŞeffaf*<br/>
[içinde] Bit eşleminin saydam rengini belirten bir RGB değeri.

*bStretch*<br/>
[içinde] TRUE ise, bit eşlemi görüntü sınırlayan dikdörtgen sığmazsa gerilir. Aksi takdirde bit eşlemi gerilmiş değildir.

*bmpAlignment*<br/>
[içinde] Bit eşleminin hizalanması.

### <a name="remarks"></a>Açıklamalar

Resim yazısı çubuğuna bit eşlemi ayarlamak için bu yöntemi kullanın.

Önceki bit eşlemi otomatik olarak yok edilir. Resim yazısı [çubuğu, CMFCCaptionBar::SetIcon](#seticon) yöntemini aradığınız için bir simge görüntülerse, [CMFCCaptionBar::RemoveIcon'u](#removeicon)arayarak simgeyi kaldırmadığınız sürece bit eşlemi görüntülenmez.

Bitmap *bmpAlignment* parametresi tarafından belirtildiği gibi hizalanır.  Bu parametre aşağıdaki `BarElementAlignment` değerlerden biri olabilir:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetbordersize"></a><a name="setbordersize"></a>CMFCCaptionBar::SetBorderSize

Resim yazısı çubuğunun kenarlık boyutunu ayarlar.

```cpp
void SetBorderSize(int nSize);
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
[içinde] Başlık çubuğu kenarlığı piksel olarak yeni boyutu.

## <a name="cmfccaptionbarsetbutton"></a><a name="setbutton"></a>CMFCCaptionBar::SetButton

Resim yazısı çubuğu için düğmeyi ayarlar.

```cpp
void SetButton(
    LPCTSTR lpszLabel,
    UINT uiCmdUI,
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,
    BOOL bHasDropDownArrow=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
Düğmenin komut etiketi.

*uiCmdUI*<br/>
Düğmenin komut kimliği.

*btnAlignmnet*<br/>
Düğme hizaya.

*bHasDropDownArrow*<br/>
DOĞRU düğme bir açılan ok görüntülerse, FALSE aksi.

## <a name="cmfccaptionbarsetbuttonpressed"></a><a name="setbuttonpressed"></a>CMFCCaptionBar::SetButtonPressed

Düğmeye basılı kalıp kalmayacağını belirtir.

```cpp
void SetButtonPressed(BOOL bPresed=TRUE);
```

### <a name="parameters"></a>Parametreler

*bPresed*<br/>
DOĞRU düğme basılı durumunu tutarsa, FALSE aksi.

## <a name="cmfccaptionbarsetbuttontooltip"></a><a name="setbuttontooltip"></a>CMFCCaptionBar::SetButtonToolTip

Düğme için araç ucunu ayarlar.

```cpp
void SetButtonToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszToolTip*<br/>
[içinde] Araç ipucu başlığı.

*lpszAçıklama*<br/>
[içinde] Araç ipucu açıklaması.

## <a name="cmfccaptionbarsetflatborder"></a><a name="setflatborder"></a>CMFCCaptionBar::SetFlatBorder

Resim yazısı çubuğunun kenarlık stilini ayarlar.

```cpp
void SetFlatBorder(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>Parametreler

*bDüz*<br/>
[içinde] Resim yazısı çubuğunun kenarlığı düzse DOĞRU. Kenarlık 3D ise YANLIŞ.

## <a name="cmfccaptionbarseticon"></a><a name="seticon"></a>CMFCCaptionBar::Seticon

Resim yazısı çubuğu simgesini ayarlar.

```cpp
void SetIcon(
    HICON hIcon,
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Parametreler

*Hıcon*<br/>
[içinde] Ayarlanan simgenin tutamacı.

*iconHiza*<br/>
[içinde] Simgenin hizalanması.

### <a name="remarks"></a>Açıklamalar

Resim yazısı çubukları simgeleri veya bit eşlemleri görüntüleyebilir. Bir bit eşentinin nasıl görüntülenebildiğini öğrenmek için [CMFCCaptionBar::SetBitmap'e](#setbitmap) bakın. Hem simge hem de bit eşleme ayarlarsanız, simge her zaman görüntülenir. Resim yazısı çubuğundan bir simgeyi kaldırmak için [CMFCCaptionBar::RemoveIcon'u](#removeicon) arayın.

Simge *ikonHizalama* parametresine göre hizalanır. Aşağıdaki `BarElementAlignment` değerlerden biri olabilir:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetimagetooltip"></a><a name="setimagetooltip"></a>CMFCCaptionBar::SetImageToolTip

Resim yazısı çubuğundaki görüntünün araç ucunu ayarlar.

```cpp
void SetImageToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszToolTip*<br/>
[içinde] Araç ucunun metni.

*lpszAçıklama*<br/>
[içinde] Araç ipucu açıklaması.

## <a name="cmfccaptionbarsetmargin"></a><a name="setmargin"></a>CMFCCaptionBar::SetMargin

Resim yazısı çubuğu öğesinin kenarı ile resim yazısı çubuğu denetiminin kenarı arasındaki mesafeyi ayarlar.

```cpp
void SetMargin(int nMargin);
```

### <a name="parameters"></a>Parametreler

*nMargin*<br/>
[içinde] Piksel olarak, resim yazısı çubuğu öğelerinin kenarı ile resim yazısı çubuğu denetiminin kenarı arasındaki mesafe.

## <a name="cmfccaptionbarsettext"></a><a name="settext"></a>CMFCCaptionBar::SetText

Resim yazısı çubuğu için metin etiketini ayarlar.

```cpp
void SetText(
    const CString& strText,
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Parametreler

*strText*<br/>
[içinde] Ayarlanan metin dizesi.

*Textalignment*<br/>
[içinde] Metin hizalaması.

### <a name="remarks"></a>Açıklamalar

Metin etiketi *textAlignment* parametresi tarafından belirtildiği şekilde hizalanır. Aşağıdaki `BarElementAlignment` değerlerden biri olabilir:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
