---
title: Coleıpframewnd sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
helpviewer_keywords:
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
ms.openlocfilehash: 34388e635ba89d732ae3993074a2c8268e2289a3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58779618"
---
# <a name="coleipframewnd-class"></a>Coleıpframewnd sınıfı

Uygulamanızın yerinde düzenleme penceresi için taban dizini.

## <a name="syntax"></a>Sözdizimi

```
class COleIPFrameWnd : public CFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Oluşturur bir `COleIPFrameWnd` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Yerinde düzenleme için bir öğe etkinleştirildiğinde framework tarafından çağırılır.|
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Yerinde düzenleme penceresi yeniden konumlandırmak için framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf oluşturur ve kapsayıcı uygulamasının belge penceresi içinde çubukları konumları denetleyin. Ayrıca katıştırılmış tarafından oluşturulan bildirimleri işleme [COleResizeBar](../../mfc/reference/coleresizebar-class.md) yerinde düzenleme penceresi kullanıcı yeniden boyutlandırdığında nesne.

Kullanma hakkında daha fazla bilgi için `COleIPFrameWnd`, makaleye göz atın [etkinleştirme](../../mfc/activation-cpp.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="coleipframewnd"></a>  COleIPFrameWnd::COleIPFrameWnd

Oluşturur bir `COleIPFrameWnd` nesnesi ve bir tür OLEINPLACEFRAMEINFO yapısı içinde depolanan yerinde durum bilgilerini, başlatır.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [OLEINPLACEFRAMEINFO](/windows/desktop/api/oleidl/ns-oleidl-tagoifi) Windows SDK.

##  <a name="oncreatecontrolbars"></a>  COleIPFrameWnd::OnCreateControlBars

Framework çağrıları `OnCreateControlBars` yerinde düzenleme için bir öğe etkinleştirildiğinde işlev.

```
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,
    CWnd* pWndDoc);

virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,
    CFrameWnd* pWndDoc);
```

### <a name="parameters"></a>Parametreler

*pWndFrame*<br/>
Kapsayıcı uygulamasının çerçeve işaretçisi.

*pWndDoc*<br/>
Kapsayıcının belge düzeyi pencere işaretçisi. Kapsayıcı bir SDI uygulaması ise NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, hiçbir şey yapmaz. Bu işlev, herhangi bir özel denetim çubukları oluştururken gerekli işlemi gerçekleştirmek için geçersiz kılın.

##  <a name="repositionframe"></a>  COleIPFrameWnd::RepositionFrame

Framework çağrıları `RepositionFrame` denetim çubukları düzenlemek ve tümünün görünür olmasını yerinde düzenleme penceresi yeniden konumlandırmak için üye işlevi.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
İşaretçi bir `RECT` yapısı veya `CRect` çerçeve pencerenin geçerli konumu koordinatları, piksel cinsinden istemci alanına göre yerinde içeren nesne.

*lpClipRect*<br/>
İşaretçi bir `RECT` yapısı veya `CRect` çerçeve pencerenin geçerli dikdörtgen kırpımını koordinatları piksel cinsinden istemci alanına göre yerinde içeren nesne.

### <a name="remarks"></a>Açıklamalar

Denetim çubukları kapsayıcı penceresinde düzenini farklıdır bir OLE dışı çerçeve penceresi tarafından gerçekleştirilen. OLE dışı çerçeve penceresi, Denetim çubuklarını ve belirtilen çerçeve pencere boyutu, bir çağrı olduğu gibi diğer nesnelerden konumlarını hesaplar [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Denetim çubukları ve diğer nesneler için boşluk çıkarılır sonra kalan istemci alanıdır. A `COleIPFrameWnd` penceresi, diğer taraftan, araç çubukları bir verilen istemci alanını uygun olarak yerleştirir. Diğer bir deyişle, `CFrameWnd::RecalcLayout` çalışır "dışarıdan," ise `COleIPFrameWnd::RepositionFrame` çalışır "Inside out."

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)
