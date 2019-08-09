---
title: CMFCRibbonLinkCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CopyFrom
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetCompactSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetRegularSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetToolTipText
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::IsDrawTooltipImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDraw
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDrawMenuImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnMouseMove
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnSetIcon
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OpenLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::SetLink
helpviewer_keywords:
- CMFCRibbonLinkCtrl [MFC], CMFCRibbonLinkCtrl
- CMFCRibbonLinkCtrl [MFC], CopyFrom
- CMFCRibbonLinkCtrl [MFC], GetCompactSize
- CMFCRibbonLinkCtrl [MFC], GetLink
- CMFCRibbonLinkCtrl [MFC], GetRegularSize
- CMFCRibbonLinkCtrl [MFC], GetToolTipText
- CMFCRibbonLinkCtrl [MFC], IsDrawTooltipImage
- CMFCRibbonLinkCtrl [MFC], OnDraw
- CMFCRibbonLinkCtrl [MFC], OnDrawMenuImage
- CMFCRibbonLinkCtrl [MFC], OnMouseMove
- CMFCRibbonLinkCtrl [MFC], OnSetIcon
- CMFCRibbonLinkCtrl [MFC], OpenLink
- CMFCRibbonLinkCtrl [MFC], SetLink
ms.assetid: 77ae1941-e0ab-4a9d-911e-1752d34c079b
ms.openlocfilehash: 12a83e45176f7fc6020da1f0d0ee5923ef0f466c
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866158"
---
# <a name="cmfcribbonlinkctrl-class"></a>CMFCRibbonLinkCtrl sınıfı

Şeritte konumlandırılmış bir köprü uygular. Köprü, tıkladığınızda bir Web sayfası açar.
Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC\\atlmfc\\\\src MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonLinkCtrl : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonLinkCtrl:: CMFCRibbonLinkCtrl](#cmfcribbonlinkctrl)|Bir `CMFCRibbonLinkCtrl` nesnesi oluşturur ve başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonLinkCtrl:: CopyFrom](#copyfrom)|(Geçersiz `CMFCRibbonButton::CopyFrom`kılmalar.)|
|[CMFCRibbonLinkCtrl:: GetCompactSize](#getcompactsize)|( [CMFCRibbonButton:: GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).) öğesini geçersiz kılar|
|[CMFCRibbonLinkCtrl:: GetLink](#getlink)|Köprünün değerini döndürür.|
|[CMFCRibbonLinkCtrl:: GetRegularSize](#getregularsize)|( [CMFCRibbonButton:: GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).) öğesini geçersiz kılar|
|[CMFCRibbonLinkCtrl:: GetToolTipText](#gettooltiptext)|( [CMFCRibbonButton:: GetToolTipText](../../mfc/reference/cmfcribbonbutton-class.md#gettooltiptext)geçersiz kılar.)|
|[CMFCRibbonLinkCtrl:: IsDrawTooltipImage](#isdrawtooltipimage)|(Geçersiz `CMFCRibbonButton::IsDrawTooltipImage`kılmalar.)|
|[CMFCRibbonLinkCtrl:: OnDraw](#ondraw)|( [CMFCRibbonButton:: OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw)geçersiz kılar.)|
|[CMFCRibbonLinkCtrl:: OnDrawMenuImage](#ondrawmenuimage)|( [CMFCRibbonBaseElement:: OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage)geçersiz kılar.)|
|[CMFCRibbonLinkCtrl:: OnMouseMove](#onmousemove)|(Geçersiz `CMFCRibbonButton::OnMouseMove`kılmalar.)|
|[CMFCRibbonLinkCtrl:: OnSetIcon](#onseticon)||
|[CMFCRibbonLinkCtrl:: OpenLink](#openlink)|Köprüde belirtilen Web sayfasını açar.|
|[CMFCRibbonLinkCtrl:: SetLink](#setlink)|Köprünün değerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Köprü oluşturduktan sonra [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)yöntemini çağırarak bir panele ekleyin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cmfcribbondüğmesi](../../mfc/reference/cmfcribbonbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonlinkctrl. h

##  <a name="cmfcribbonlinkctrl"></a>CMFCRibbonLinkCtrl:: CMFCRibbonLinkCtrl

Bir [CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md) nesnesi oluşturur ve başlatır.

```
CMFCRibbonLinkCtrl(
    UINT nID,
    LPCTSTR lpszText,
    LPCTSTR lpszLink);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
'ndaki Bağlantı denetimi tıklandığında yürütülen komutun komut KIMLIĞINI belirtir.

*lpszText*<br/>
'ndaki Bağlantı denetiminde görüntülenecek etiketi belirtir.

*lpszLink*<br/>
'ndaki Bağlantı denetimiyle ilişkili köprüyü belirtir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCRibbonLinkCtrl` sınıfının oluşturucusunun nasıl kullanılacağını göstermektedir. Bu kod parçacığı, [Şerit araçları örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_RibbonGadgets#1](../../mfc/reference/codesnippet/cpp/cmfcribbonlinkctrl-class_1.cpp)]

##  <a name="copyfrom"></a>CMFCRibbonLinkCtrl:: CopyFrom

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parametreler

'ndaki *src*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="getcompactsize"></a>CMFCRibbonLinkCtrl:: GetCompactSize

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getlink"></a>CMFCRibbonLinkCtrl:: GetLink

Köprünün değerini döndürür.

```
LPCTSTR GetLink() const;
```

### <a name="return-value"></a>Dönüş Değeri

Köprünün geçerli değeri.

### <a name="remarks"></a>Açıklamalar

##  <a name="getregularsize"></a>CMFCRibbonLinkCtrl:: GetRegularSize

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="gettooltiptext"></a>CMFCRibbonLinkCtrl:: GetToolTipText

```
virtual CString GetToolTipText() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="ondrawmenuimage"></a>CMFCRibbonLinkCtrl:: OnDrawMenuImage

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>Parametreler

'ndaki *CDC&#42;*<br/>
'ndaki *CRect*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="isdrawtooltipimage"></a>CMFCRibbonLinkCtrl:: IsDrawTooltipImage

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="ondraw"></a>CMFCRibbonLinkCtrl:: OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="onmousemove"></a>CMFCRibbonLinkCtrl:: OnMouseMove

```
virtual void OnMouseMove(CPoint point);
```

### <a name="parameters"></a>Parametreler

'ndaki *nokta*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="onseticon"></a>CMFCRibbonLinkCtrl:: OnSetIcon

```
virtual void OnSetIcon();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="openlink"></a>CMFCRibbonLinkCtrl:: OpenLink

Köprüde belirtilen Web sayfasını açar.

```
BOOL OpenLink();
```

### <a name="return-value"></a>Dönüş Değeri

İlişkili Web sayfası başarıyla açıldıysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

`CMFCRibbonLinkCtrl` Nesneyle ilişkili köprüyü kullanarak bir Web sayfasını açar.

##  <a name="setlink"></a>CMFCRibbonLinkCtrl:: SetLink

Köprünün değerini ayarlar.

```
void SetLink(LPCTSTR lpszLink);
```

### <a name="parameters"></a>Parametreler

*lpszLink*<br/>
'ndaki Köprü metnini belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
