---
title: CMFCRibbonLinkCtrl Sınıfı
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
ms.openlocfilehash: 5d00c17b2ede654b9bdd214a8649f1237b9d9fdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375113"
---
# <a name="cmfcribbonlinkctrl-class"></a>CMFCRibbonLinkCtrl Sınıfı

Şerit üzerinde konumlandırılmış bir köprü uygular. Köprü, tıklattığınızda bir Web sayfası açar.
Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonLinkCtrl : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl](#cmfcribbonlinkctrl)|Bir `CMFCRibbonLinkCtrl` nesne yi inşa eder ve başharfe ait hale raz.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonLinkCtrl::CopyFrom](#copyfrom)|(Geçersiz `CMFCRibbonButton::CopyFrom`kılar .)|
|[CMFCRibbonLinkCtrl::GetCompactSize](#getcompactsize)|[(CMFCRibbonButton geçersiz kılar::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[CMFCRibbonLinkCtrl::GetLink](#getlink)|Köprü değerini verir.|
|[CMFCRibbonLinkCtrl::GetRegularSize](#getregularsize)|[(CMFCRibbonButton geçersiz kılar::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[CMFCRibbonLinkCtrl::GetToolTipText](#gettooltiptext)|[(CMFCRibbonButton geçersiz kılar::GetToolTipText](../../mfc/reference/cmfcribbonbutton-class.md#gettooltiptext).)|
|[CMFCRibbonLinkCtrl::IsDrawTooltipImage](#isdrawtooltipimage)|(Geçersiz `CMFCRibbonButton::IsDrawTooltipImage`kılar .)|
|[CMFCRibbonLinkCtrl::OnDraw](#ondraw)|[(CMFCRibbonButton geçersiz kılar::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[CMFCRibbonLinkCtrl::OnDrawMenuImage](#ondrawmenuimage)|[(CMFCRibbonBaseElement geçersiz kılar::OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|
|[CMFCRibbonLinkCtrl::OnMouseMove](#onmousemove)|(Geçersiz `CMFCRibbonButton::OnMouseMove`kılar .)|
|[CMFCRibbonLinkCtrl::OnSetIcon](#onseticon)||
|[CMFCRibbonLinkCtrl::OpenLink](#openlink)|Köprüde belirtilen Web sayfasını açar.|
|[CMFCRibbonLinkCtrl::SetLink](#setlink)|Köprüdeğerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir köprü oluşturduktan sonra CMFCRibbonPanel'i arayarak bir panele [ekleyin::Ekle.](../../mfc/reference/cmfcribbonpanel-class.md#add)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)\
•&nbsp;[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonLinkCtrl.h

## <a name="cmfcribbonlinkctrlcmfcribbonlinkctrl"></a><a name="cmfcribbonlinkctrl"></a>CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl

[CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md) nesnesi inşa eder ve başharflerini.

```
CMFCRibbonLinkCtrl(
    UINT nID,
    LPCTSTR lpszText,
    LPCTSTR lpszLink);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
[içinde] Bağlantı denetimi tıklatıldığında çalıştıran komutun komut kimliğini belirtir.

*lpszMetin*<br/>
[içinde] Bağlantı denetiminde görüntülenecek etiketi belirtir.

*lpszLink*<br/>
[içinde] Bağlantı denetimiyle ilişkili köprünün belirtinir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın oluşturucusu nasıl `CMFCRibbonLinkCtrl` kullanılacağını gösterir. Bu kod parçacığı [Şerit Gadget'lar örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_RibbonGadgets#1](../../mfc/reference/codesnippet/cpp/cmfcribbonlinkctrl-class_1.cpp)]

## <a name="cmfcribbonlinkctrlcopyfrom"></a><a name="copyfrom"></a>CMFCRibbonLinkCtrl::CopyFrom

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parametreler

[içinde] *src*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlgetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonLinkCtrl::GetCompactSize

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlgetlink"></a><a name="getlink"></a>CMFCRibbonLinkCtrl::GetLink

Köprü değerini verir.

```
LPCTSTR GetLink() const;
```

### <a name="return-value"></a>Dönüş Değeri

Köprünün geçerli değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonLinkCtrl::GetRegularSize

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlgettooltiptext"></a><a name="gettooltiptext"></a>CMFCRibbonLinkCtrl::GetToolTipText

```
virtual CString GetToolTipText() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlondrawmenuimage"></a><a name="ondrawmenuimage"></a>CMFCRibbonLinkCtrl::OnDrawMenuImage

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>Parametreler

[içinde] *CDC&#42;*<br/>
[içinde] *CRect*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a>CMFCRibbonLinkCtrl::IsDrawTooltipImage

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlondraw"></a><a name="ondraw"></a>CMFCRibbonLinkCtrl::OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDC*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlonmousemove"></a><a name="onmousemove"></a>CMFCRibbonLinkCtrl::OnMouseMove

```
virtual void OnMouseMove(CPoint point);
```

### <a name="parameters"></a>Parametreler

[içinde] *nokta*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlonseticon"></a><a name="onseticon"></a>CMFCRibbonLinkCtrl::OnSetIcon

```
virtual void OnSetIcon();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlopenlink"></a><a name="openlink"></a>CMFCRibbonLinkCtrl::OpenLink

Köprüde belirtilen Web sayfasını açar.

```
BOOL OpenLink();
```

### <a name="return-value"></a>Dönüş Değeri

İlişkili web sayfası başarıyla açıldıysa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

`CMFCRibbonLinkCtrl` Nesneyle ilişkili köprükullanarak bir web sayfası açar.

## <a name="cmfcribbonlinkctrlsetlink"></a><a name="setlink"></a>CMFCRibbonLinkCtrl::SetLink

Köprüdeğerini ayarlar.

```
void SetLink(LPCTSTR lpszLink);
```

### <a name="parameters"></a>Parametreler

*lpszLink*<br/>
[içinde] Köprü metnini belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
