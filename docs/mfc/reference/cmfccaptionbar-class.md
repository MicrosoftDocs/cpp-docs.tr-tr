---
title: CMFCCaptionBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a6379112de9b31de55b86cc4bc4e06a94863ac6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406829"
---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar sınıfı

A `CMFCCaptionBar` nesnedir üç öğe görüntüleyebilen denetim çubuğu: bir düğmeye bir metin etiketi ve bir bit eşlem. Her türden bir öğe aynı anda yalnızca görüntüleyebilir. Her bir öğeyi denetimin sol veya sağ kenarına ya da ortasına hizalayabilirsiniz. Ayrıca, başlık çubuğunun üst ve alt kenarlıklarına düz veya 3B stil uygulayabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
class CMFCCaptionBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCCaptionBar::Create](#create)|Başlık çubuğu denetimi oluşturur ve ona ekler `CMFCCaptionBar` nesne.|
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Başka bir bölmesinde dinamik olarak kendi üst çerçevenin başlık çubuğu arasında eklenip eklenemeyeceğini belirtir. (Geçersiz kılmaları [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCCaptionBar::EnableButton](#enablebutton)|Etkinleştirir veya başlık çubuğunda düğme devre dışı bırakır.|
|[CMFCCaptionBar::GetAlignment](#getalignment)|Belirtilen öğe hizalamasını döndürür.|
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|Başlık çubuğunun kenarlık boyutu döndürür.|
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|Başlık çubuğunda düğme sınırlayıcı dikdörtgenini alır.|
|[CMFCCaptionBar::GetMargin](#getmargin)|Başlık çubuğu öğeleri ile başlık çubuğu denetiminin kenarı arasındaki uzaklığı döndürür.|
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|Başlık çubuğu ileti çubuğu modunda olup olmadığını belirtir.|
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|Bit eşlem görüntüsüne Başlık Çubuğu'ndan kaldırır.|
|[CMFCCaptionBar::RemoveButton](#removebutton)|Düğme Başlık Çubuğu'ndan kaldırır.|
|[CMFCCaptionBar::RemoveIcon](#removeicon)|Simge Başlık Çubuğu'ndan kaldırır.|
|[CMFCCaptionBar::RemoveText](#removetext)|Metin etiketi Başlık Çubuğu'ndan kaldırır.|
|[CMFCCaptionBar::SetBitmap](#setbitmap)|Başlık çubuğu için bit eşlem görüntüsüne ayarlar.|
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|Başlık çubuğunun kenarlık boyutunu ayarlar.|
|[CMFCCaptionBar::SetButton](#setbutton)|Başlık çubuğu düğmesini ayarlar.|
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|Düğmeye basılan kalıp kalmayacağını belirtir.|
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|Düğmenin araç ipucu ayarlar.|
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|Başlık çubuğu kenarlık stilini ayarlar.|
|[CMFCCaptionBar::SetIcon](#seticon)|Başlık çubuğu simgesi ayarlar.|
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|Araç ipucu için başlık çubuğu görüntüsü için ayarlar.|
|[CMFCCaptionBar::SetMargin](#setmargin)|Başlık çubuğu öğesinin kenarı ile başlık çubuğu denetiminin arasındaki uzaklığı ayarlar.|
|[CMFCCaptionBar::SetText](#settext)|Başlık çubuğu metni etiketini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|Başlık çubuğunun arkaplanını doldurmak için framework tarafından çağırılır.|
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|Başlık çubuğunun kenarlık çizmek için framework tarafından çağırılır.|
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|Başlık çubuğu düğme çizmek için framework tarafından çağırılır.|
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|Başlık çubuğu resmi çizmek için framework tarafından çağırılır.|
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|Başlık çubuğu metni çizmek için framework tarafından çağırılır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|Başlık çubuğu arka plan rengi.|
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|Başlık çubuğunun kenarlık rengi.|
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|Başlık çubuğu metni rengi.|

## <a name="remarks"></a>Açıklamalar

Başlık çubuğu oluşturmak için aşağıdaki adımları izleyin:

1. Oluşturmak `CMFCCaptionBar` nesne. Genellikle, bir çerçeve penceresi sınıfı için başlık çubuğu eklersiniz.

1. Çağrı [CMFCCaptionBar::Create](#create) başlık çubuğu denetimi oluşturun ve buna eklemek için yöntem `CMFCCaptionBar` nesne.

1. Çağrı [CMFCCaptionBar::SetButton](#setbutton), [CMFCCaptionBar::SetText](#settext), [CMFCCaptionBar::SetIcon](#seticon), ve [CMFCCaptionBar::SetBitmap](#setbitmap)başlık çubuğu öğeleri ayarlamak için.

Button öğesi ayarladığınızda, düğmeyi komut kimliği atamanız gerekir. Başlık çubuğu, kullanıcı düğmeye tıkladığında bu Kimliğe sahip ana çerçeve penceresine WM_COMMAND iletileri yönlendirir.

Başlık çubuğu, Microsoft Office 2007 uygulamalarında görünen ileti çubuğu öykünür ileti çubuğu modunda da çalışabilir. İleti çubuğu modunda başlık çubuğu, (genellikle iletişim kutusu açılır.) bir düğme bir bit eşlem ve bir ileti görüntüler. Bir araç ipucu için bit eşlem atayabilirsiniz.

İleti çubuğu modunu etkinleştirmek için çağrı [CMFCCaptionBar::Create](#create) ve dördüncü parametresinin (bIsMessageBarMode) TRUE olarak ayarlayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCCaptionBar` sınıfı. Örnek, başlık çubuğu denetimi oluşturma, başlık çubuğunun 3D kenarlığı ayarlayın, başlık çubuğu öğeleri, edge ile başlık çubuğu denetiminin kenarı arasındaki piksel cinsinden uzaklığı ayarlayın, başlık çubuğu düğme kümesi gösterir. , düğmenin araç ipucu için başlık çubuğu metni etiketi ayarlamak, başlık çubuğu için bit eşlem resmi ayarlama ve görüntü için araç ipucu başlık çubuğunda ayarlayın. Bu kod parçacığı parçasıdır [MS Office 2007 Demo örnek](../../visual-cpp-samples.md).

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

**Başlık:** afxcaptionbar.h

##  <a name="create"></a>  CMFCCaptionBar::Create

Başlık çubuğu denetimi oluşturur ve ona ekler `CMFCCaptionBar` nesne.

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
Mantıksal OR kombinasyonudur başlık çubuğu stilleri.

*pParentWnd*<br/>
Başlık çubuğu denetiminin üst penceresine.

*Kullanıcı Kimliği*<br/>
Başlık çubuğu denetiminin kimliği.

*nHeight*<br/>
Başlık çubuğu denetiminin piksel cinsinden yüksekliği. Yüksekliği, -1 olması durumunda, simge, metin ve başlık çubuğu denetimi görüntüleyen düğmeyi yüksekliğini göre hesaplanır.

*bIsMessageBarMode*<br/>
Başlık çubuğu ileti çubuğu modunda ise TRUE; FALSE Aksi takdirde.

### <a name="return-value"></a>Dönüş Değeri

Başlık çubuğu denetimi başarıyla oluşturulursa TRUE; FALSE Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CMFCCaptionBar` iki adımda nesne. İlk Oluşturucu çağırmanız ve ardından çağırmanızı `Create` Windows denetimi oluşturur ve ona ekler yöntemi `CMFCCaptionBar` nesne.

##  <a name="doesallowdyninsertbefore"></a>  CMFCCaptionBar::DoesAllowDynInsertBefore

Başka bir bölmesinde dinamik olarak kendi üst çerçevenin başlık çubuğu arasında eklenip eklenemeyeceğini belirtir.

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçersiz kılınmadığı sürece false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="enablebutton"></a>  CMFCCaptionBar::EnableButton

Etkinleştirir veya başlık çubuğunda düğme devre dışı bırakır.

```
void EnableButton(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Düğmeyi devre dışı bırakmak için FALSE düğmesini etkinleştirmek için TRUE.

##  <a name="getalignment"></a>  CMFCCaptionBar::GetAlignment

Belirtilen öğe hizalamasını döndürür.

```
BarElementAlignment GetAlignment(BarElement elem);
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
[in] Hizalama almak istediğiniz bir başlık çubuğu öğesi.

### <a name="return-value"></a>Dönüş Değeri

Bir düğme, bir bit eşlem, metin veya simge gibi bir öğenin hizalaması.

### <a name="remarks"></a>Açıklamalar

Öğenin hizalaması aşağıdaki değerlerden biri olabilir:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

##  <a name="getbordersize"></a>  CMFCCaptionBar::GetBorderSize

Başlık çubuğunun kenarlık boyutu döndürür.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kenarlığın piksel cinsinden büyüklüğü.

##  <a name="getbuttonrect"></a>  CMFCCaptionBar::GetButtonRect

Başlık çubuğunda düğme sınırlayıcı dikdörtgenini alır.

```
CRect GetButtonRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `CRect` başlık çubuğunda düğme sınırlayıcı dikdörtgenini koordinatları içeren nesne.

##  <a name="getmargin"></a>  CMFCCaptionBar::GetMargin

Başlık çubuğu öğeleri ile başlık çubuğu denetiminin kenarı arasındaki uzaklığı döndürür.

```
int GetMargin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başlık çubuğu öğeleri ile başlık çubuğu denetiminin kenarı arasındaki piksel cinsinden uzaklığı.

##  <a name="ismessagebarmode"></a>  CMFCCaptionBar::IsMessageBarMode

Başlık çubuğu ileti çubuğu modunda olup olmadığını belirtir.

```
BOOL IsMessageBarMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başlık çubuğu ileti çubuğu modunda ise TRUE; FALSE Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

İleti çubuğu modunda başlık çubuğu bir araç ipucu, ileti metni ve bir düğmeyi bir resim görüntüler.

##  <a name="m_clrbarbackground"></a>  CMFCCaptionBar::m_clrBarBackground

Başlık çubuğu arka plan rengi.

```
COLORREF m_clrBarBackground
```

##  <a name="m_clrbarborder"></a>  CMFCCaptionBar::m_clrBarBorder

Başlık çubuğunun kenarlık rengi.

```
COLORREF m_clrBarBorder
```

##  <a name="m_clrbartext"></a>  CMFCCaptionBar::m_clrBarText

Başlık çubuğu metni rengi.

```
COLORREF m_clrBarText
```

##  <a name="ondrawbackground"></a>  CMFCCaptionBar::OnDrawBackground

Başlık çubuğunun arkaplanını doldurmak için framework tarafından çağırılır.

```
virtual void OnDrawBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Başlık çubuğunun cihaz bağlamı için bir işaretçi.

*Rect*<br/>
[in] Doldurmak için sınırlayıcı dikdörtgeni.

### <a name="remarks"></a>Açıklamalar

`OnDrawBackground` Yöntemi hakkında doldurulması için başlık çubuğunun arka plan olduğunda çağrılır. Varsayılan uygulama kullanarak arka plan doldurur [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) rengi.

Bu yöntemin bir `CMFCCaptionBar` türetilmiş sınıf başlık çubuğunun görünümünü özelleştirmek için.

##  <a name="ondrawborder"></a>  CMFCCaptionBar::OnDrawBorder

Başlık çubuğunun kenarlık çizmek için framework tarafından çağırılır.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Kenarlıklar görüntülemek için kullanılan bir cihaz bağlamı.

*Rect*<br/>
[in] Dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak kenarlıklar düz stili var.

Bu yöntemin bir `CMFCCaptionBar` türetilmiş sınıf başlık çubuğunun kenarlık görünümünü özelleştirmek için.

##  <a name="ondrawbutton"></a>  CMFCCaptionBar::OnDrawButton

Başlık çubuğu düğme çizmek için framework tarafından çağırılır.

```
virtual void OnDrawButton(
    CDC* pDC,
    CRect rect,
    const CString& strButton,
    BOOL bEnabled);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir düğme görüntülemek için kullanılan bir cihaz bağlamı için bir işaretçi.

*Rect*<br/>
[in] Dikdörtgen düğmesi.

*strButton*<br/>
[in] Düğmenin metin etiketi.

*bEtkin*<br/>
[in] Düğmesi etkinse TRUE; FALSE Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin bir `CMFCCaptionBar` türetilmiş sınıf başlık çubuğunun düğmenin görünümünü özelleştirmek için.

##  <a name="ondrawimage"></a>  CMFCCaptionBar::OnDrawImage

Başlık çubuğu resmi çizmek için framework tarafından çağırılır.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Görüntüyü görüntülemek için kullanılan bir cihaz bağlamı için bir işaretçi.

*Rect*<br/>
[in] Sınırlayıcı dikdörtgeni görüntünün belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin bir `CMFCCaptionBar` türetilmiş sınıf görüntü görünümünü özelleştirmek için.

##  <a name="ondrawtext"></a>  CMFCCaptionBar::OnDrawText

Başlık çubuğu metni çizmek için framework tarafından çağırılır.

```
virtual void OnDrawText(
    CDC* pDC,
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir düğme görüntülemek için kullanılan bir cihaz bağlamı için bir işaretçi.

*Rect*<br/>
[in] Dikdörtgen metin.

*strText*<br/>
[in] Görüntülenecek metin dizesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama kullanarak metni görüntüler `CDC::DrawText` ve [CMFCCaptionBar::m_clrBarText](#m_clrbartext) rengi.

Bu yöntemin bir `CMFCCaptionBar` türetilmiş sınıf başlık çubuğunun metin görünümünü özelleştirmek için.

##  <a name="removebitmap"></a>  CMFCCaptionBar::RemoveBitmap

Bit eşlem görüntüsüne Başlık Çubuğu'ndan kaldırır.

```
void RemoveBitmap();
```

##  <a name="removebutton"></a>  CMFCCaptionBar::RemoveButton

Düğme Başlık Çubuğu'ndan kaldırır.

```
void RemoveButton();
```

### <a name="remarks"></a>Açıklamalar

Başlık çubuğu öğeleri düzenini ayarlanmış otomatik olarak.

##  <a name="removeicon"></a>  CMFCCaptionBar::RemoveIcon

Simge Başlık Çubuğu'ndan kaldırır.

```
void RemoveIcon();
```

##  <a name="removetext"></a>  CMFCCaptionBar::RemoveText

Metin etiketi Başlık Çubuğu'ndan kaldırır.

```
void RemoveText();
```

##  <a name="setbitmap"></a>  CMFCCaptionBar::SetBitmap

Başlık çubuğu için bit eşlem görüntüsüne ayarlar.

```
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
[in] Ayarlamak için bit eşlem tanıtıcısını.

*clrTransparent*<br/>
[in] Bit eşlem saydam rengini belirten bir RGB değeri.

*bStretch*<br/>
[in] Sınırlayıcı dikdörtgeni görüntünün sığmazsa doğruysa, bit eşlem uzatılır. Aksi takdirde bit eşlem esnetilmiş değil.

*bmpAlignment*<br/>
[in] Bit eşlem hizalaması.

### <a name="remarks"></a>Açıklamalar

Başlık çubuğunda bir bit eşlem ayarlamak için bu yöntemi kullanın.

Önceki bit eşlem otomatik olarak yok. Başlık çubuğu denir, çünkü bir simge görüntüler [CMFCCaptionBar::SetIcon](#seticon) yöntemi çağırarak simgeyi Kaldır sürece bit eşlem görüntülenmez [CMFCCaptionBar::RemoveIcon](#removeicon).

Bit eşlem hizalanır belirtildiği gibi *bmpAlignment* parametresi.  Bu parametre aşağıdaki değerlerden biri olabilir `BarElementAlignment` değerleri:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

##  <a name="setbordersize"></a>  CMFCCaptionBar::SetBorderSize

Başlık çubuğunun kenarlık boyutunu ayarlar.

```
void SetBorderSize(int nSize);
```

### <a name="parameters"></a>Parametreler

*nSize*<br/>
[in] Başlık çubuğu kenarlığının piksel cinsinden yeni boyutu.

##  <a name="setbutton"></a>  CMFCCaptionBar::SetButton

Başlık çubuğu düğmesini ayarlar.

```
void SetButton(
    LPCTSTR lpszLabel,
    UINT uiCmdUI,
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,
    BOOL bHasDropDownArrow=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
Düğmenin komut etiketi.

*uiCmdUI*<br/>
Düğmenin komut kimliği.

*btnAlignmnet*<br/>
Düğmenin hizalaması.

*bHasDropDownArrow*<br/>
Düğme açılan bir oka, yanlış Aksi halde görüntüler TRUE.

##  <a name="setbuttonpressed"></a>  CMFCCaptionBar::SetButtonPressed

Düğmeye basılan kalıp kalmayacağını belirtir.

```
void SetButtonPressed(BOOL bPresed=TRUE);
```

### <a name="parameters"></a>Parametreler

*bPresed*<br/>
Düğmeye basılan durumunu, FALSE Aksi halde tutar TRUE.

##  <a name="setbuttontooltip"></a>  CMFCCaptionBar::SetButtonToolTip

Düğmenin araç ipucu ayarlar.

```
void SetButtonToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszToolTip*<br/>
[in] Araç ipucu başlığı.

*lpszDescription*<br/>
[in] Araç İpucu açıklaması.

##  <a name="setflatborder"></a>  CMFCCaptionBar::SetFlatBorder

Başlık çubuğu kenarlık stilini ayarlar.

```
void SetFlatBorder(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>Parametreler

*bFlat*<br/>
[in] Başlık çubuğu kenarlığı düz ise TRUE. 3B kenarlık ise FALSE.

##  <a name="seticon"></a>  CMFCCaptionBar::SetIcon

Başlık çubuğu simgesi ayarlar.

```
void SetIcon(
    HICON hIcon,
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Parametreler

*hIcon*<br/>
[in] Ayarlanacak simgesine tanıtıcısı.

*iconAlignment*<br/>
[in] Simge hizalaması.

### <a name="remarks"></a>Açıklamalar

Başlık çubukları, simge ya da bit eşlemler görüntüleyebilirsiniz. Bkz: [CMFCCaptionBar::SetBitmap](#setbitmap) bir bit eşlem görüntülemeyi öğrenin. Simge, hem simge hem de bit eşlem ayarlarsanız, her zaman görüntülenir. Çağrı [CMFCCaptionBar::RemoveIcon](#removeicon) başlık çubuğundaki bir simgeyi kaldırmak için.

Simge göre hizalı *iconAlignment* parametresi. Aşağıdakilerden biri olabilir `BarElementAlignment` değerleri:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

##  <a name="setimagetooltip"></a>  CMFCCaptionBar::SetImageToolTip

Araç ipucu için görüntü başlık çubuğunda ayarlar.

```
void SetImageToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Parametreler

*lpszToolTip*<br/>
[in] Araç İpucu metni.

*lpszDescription*<br/>
[in] Araç İpucu açıklaması.

##  <a name="setmargin"></a>  CMFCCaptionBar::SetMargin

Başlık çubuğu öğesinin kenarı ile başlık çubuğu denetiminin arasındaki uzaklığı ayarlar.

```
void SetMargin(int nMargin);
```

### <a name="parameters"></a>Parametreler

*nMargin*<br/>
[in] Başlık çubuğu öğeleri ile başlık çubuğu denetiminin kenarı arasındaki piksel cinsinden uzaklığı.

##  <a name="settext"></a>  CMFCCaptionBar::SetText

Başlık çubuğu metni etiketini ayarlar.

```
void SetText(
    const CString& strText,
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Parametreler

*strText*<br/>
[in] Ayarlanacak metin dizesi.

*textAlignment*<br/>
[in] Metin hizalama.

### <a name="remarks"></a>Açıklamalar

Metin etiketi hizalanır belirtildiği gibi *textAlignment* parametresi. Aşağıdakilerden biri olabilir `BarElementAlignment` değerleri:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
