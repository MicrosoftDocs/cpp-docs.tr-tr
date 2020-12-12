---
description: 'Daha fazla bilgi edinin: CMFCRibbonLinkCtrl sınıfı'
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
ms.openlocfilehash: 19b10643fa1af25dae4a5dc888f61d1c9ecaaee7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321794"
---
# <a name="cmfcribbonlinkctrl-class"></a>CMFCRibbonLinkCtrl sınıfı

Şeritte konumlandırılmış bir köprü uygular. Köprü, tıkladığınızda bir Web sayfası açar.
Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonLinkCtrl : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonLinkCtrl:: CMFCRibbonLinkCtrl](#cmfcribbonlinkctrl)|Bir nesnesi oluşturur ve başlatır `CMFCRibbonLinkCtrl` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonLinkCtrl:: CopyFrom](#copyfrom)|(Geçersiz kılmalar `CMFCRibbonButton::CopyFrom` .)|
|[CMFCRibbonLinkCtrl:: GetCompactSize](#getcompactsize)|( [CMFCRibbonButton:: GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).) öğesini geçersiz kılar|
|[CMFCRibbonLinkCtrl:: GetLink](#getlink)|Köprünün değerini döndürür.|
|[CMFCRibbonLinkCtrl:: GetRegularSize](#getregularsize)|( [CMFCRibbonButton:: GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).) öğesini geçersiz kılar|
|[CMFCRibbonLinkCtrl:: GetToolTipText](#gettooltiptext)|( [CMFCRibbonButton:: GetToolTipText](../../mfc/reference/cmfcribbonbutton-class.md#gettooltiptext)geçersiz kılar.)|
|[CMFCRibbonLinkCtrl:: IsDrawTooltipImage](#isdrawtooltipimage)|(Geçersiz kılmalar `CMFCRibbonButton::IsDrawTooltipImage` .)|
|[CMFCRibbonLinkCtrl:: OnDraw](#ondraw)|( [CMFCRibbonButton:: OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw)geçersiz kılar.)|
|[CMFCRibbonLinkCtrl:: OnDrawMenuImage](#ondrawmenuimage)|( [CMFCRibbonBaseElement:: OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage)geçersiz kılar.)|
|[CMFCRibbonLinkCtrl:: OnMouseMove](#onmousemove)|(Geçersiz kılmalar `CMFCRibbonButton::OnMouseMove` .)|
|[CMFCRibbonLinkCtrl:: OnSetIcon](#onseticon)||
|[CMFCRibbonLinkCtrl:: OpenLink](#openlink)|Köprüde belirtilen Web sayfasını açar.|
|[CMFCRibbonLinkCtrl:: SetLink](#setlink)|Köprünün değerini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Köprü oluşturduktan sonra [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)yöntemini çağırarak bir panele ekleyin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)\
└ &nbsp; [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [Cmfcribbondüğmesi](../../mfc/reference/cmfcribbonbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonlinkctrl. h

## <a name="cmfcribbonlinkctrlcmfcribbonlinkctrl"></a><a name="cmfcribbonlinkctrl"></a> CMFCRibbonLinkCtrl:: CMFCRibbonLinkCtrl

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

Aşağıdaki örnek, sınıfının oluşturucusunun nasıl kullanılacağını göstermektedir `CMFCRibbonLinkCtrl` . Bu kod parçacığı, [Şerit araçları örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_RibbonGadgets#1](../../mfc/reference/codesnippet/cpp/cmfcribbonlinkctrl-class_1.cpp)]

## <a name="cmfcribbonlinkctrlcopyfrom"></a><a name="copyfrom"></a> CMFCRibbonLinkCtrl:: CopyFrom

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parametreler

'ndaki *src*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlgetcompactsize"></a><a name="getcompactsize"></a> CMFCRibbonLinkCtrl:: GetCompactSize

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlgetlink"></a><a name="getlink"></a> CMFCRibbonLinkCtrl:: GetLink

Köprünün değerini döndürür.

```
LPCTSTR GetLink() const;
```

### <a name="return-value"></a>Dönüş Değeri

Köprünün geçerli değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlgetregularsize"></a><a name="getregularsize"></a> CMFCRibbonLinkCtrl:: GetRegularSize

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlgettooltiptext"></a><a name="gettooltiptext"></a> CMFCRibbonLinkCtrl:: GetToolTipText

```
virtual CString GetToolTipText() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlondrawmenuimage"></a><a name="ondrawmenuimage"></a> CMFCRibbonLinkCtrl:: OnDrawMenuImage

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>Parametreler

'ndaki *CDC&#42;*<br/>
'ndaki *CRect*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a> CMFCRibbonLinkCtrl:: IsDrawTooltipImage

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlondraw"></a><a name="ondraw"></a> CMFCRibbonLinkCtrl:: OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlonmousemove"></a><a name="onmousemove"></a> CMFCRibbonLinkCtrl:: OnMouseMove

```
virtual void OnMouseMove(CPoint point);
```

### <a name="parameters"></a>Parametreler

'ndaki *nokta*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlonseticon"></a><a name="onseticon"></a> CMFCRibbonLinkCtrl:: OnSetIcon

```
virtual void OnSetIcon();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonlinkctrlopenlink"></a><a name="openlink"></a> CMFCRibbonLinkCtrl:: OpenLink

Köprüde belirtilen Web sayfasını açar.

```
BOOL OpenLink();
```

### <a name="return-value"></a>Dönüş Değeri

İlişkili Web sayfası başarıyla açıldıysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Nesneyle ilişkili köprüyü kullanarak bir Web sayfasını açar `CMFCRibbonLinkCtrl` .

## <a name="cmfcribbonlinkctrlsetlink"></a><a name="setlink"></a> CMFCRibbonLinkCtrl:: SetLink

Köprünün değerini ayarlar.

```cpp
void SetLink(LPCTSTR lpszLink);
```

### <a name="parameters"></a>Parametreler

*lpszLink*<br/>
'ndaki Köprü metnini belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)
