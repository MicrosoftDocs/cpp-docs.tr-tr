---
title: CMFCLinkCtrl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
ms.openlocfilehash: bc43dcaf077bc97e3ff589a12bee6a8eac6aeed1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608591"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl sınıfı

`CMFCLinkCtrl` Sınıfı bir düğmeyi köprü olarak görüntüler ve düğme tıklandığında bağlantı hedefini çağırır.

## <a name="syntax"></a>Sözdizimi

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCLinkCtrl::SetURL](#seturl)|Belirtilen URL düğme metnini görüntüler.|
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|Örtük Protokolü ayarlar (örneğin, "http:") URL'si.|
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Düğme metni ya da bit eşlem içerecek şekilde düğmeyi yeniden boyutlandırır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Düğme odak dikdörtgenini çizilmeden önce framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Türetilen bir düğmeye tıkladığınızda `CMFCLinkCtrl` sınıfı framework geçirir düğmenin URL parametresi olarak `ShellExecute` yöntemi. Ardından `ShellExecute` yöntemi URL hedefi açılır.

## <a name="example"></a>Örnek

Aşağıdaki örnek boyutunu ayarlama yapmayı gösteren bir `CMFCLinkCtrl` nesnesi ve bir url ve bir araç ipucunda nasıl ayarlanacağını bir `CMFCLinkCtrl` nesne. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxlinkctrl.h

##  <a name="ondrawfocusrect"></a>  CMFCLinkCtrl::OnDrawFocusRect

Düğme odak dikdörtgenini çizilmeden önce framework tarafından çağırılır.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*rectClient*<br/>
[in] Bağlantı denetimi sınırların bir dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Düğme odak dikdörtgenini çizmek için kendi kodunuzu kullanmak istediğinizde bu yöntemi yok sayın.

##  <a name="seturl"></a>  CMFCLinkCtrl::SetURL

Belirtilen URL düğme metnini görüntüler.

```
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Parametreler

*lpszURL*<br/>
[in] Görüntülenecek düğme metni.

### <a name="remarks"></a>Açıklamalar

##  <a name="seturlprefix"></a>  CMFCLinkCtrl::SetURLPrefix

Örtük Protokolü ayarlar (örneğin, "http:") URL'si.

```
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>Parametreler

*lpszPrefix*<br/>
[in] URL protokolü öneki.

### <a name="remarks"></a>Açıklamalar

URL öneki ayarlamak için bu yöntemi kullanın. Önek düğmenin yüzüne görüntülenmez, ancak URL'nin hedefine Gözat yardımcı olması için kullanın.

##  <a name="sizetocontent"></a>  CMFCLinkCtrl::SizeToContent

Düğme metni ya da bit eşlem içerecek şekilde düğmeyi yeniden boyutlandırır.

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>Parametreler

*bVCenter*<br/>
[in] Düğme metni ve dikey olarak üst ve alt bağlantı denetimi arasındaki bit eşlem merkezi için TRUE; Aksi takdirde FALSE. Varsayılan değer FALSE olur.

*bHCenter*<br/>
[in] Düğme metni ve bit eşlem ve bağlantı denetimin sol tarafında arasındaki yatay olarak ortalamak için TRUE; Aksi takdirde FALSE. Varsayılan değer FALSE olur.

### <a name="return-value"></a>Dönüş Değeri

A [CSize](../../atl-mfc-shared/reference/csize-class.md) yeni bağlantı denetiminin boyutunu içeren nesne.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CLinkCtrl Sınıfı](../../mfc/reference/clinkctrl-class.md)<br/>
[CMFCButton Sınıfı](../../mfc/reference/cmfcbutton-class.md)
