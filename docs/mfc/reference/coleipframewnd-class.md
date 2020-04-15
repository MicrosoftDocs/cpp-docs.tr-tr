---
title: COleIPFrameWnd Sınıfı
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
ms.openlocfilehash: 01e259cf01c42add26088b0cbd2f6dab311eb9b1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374951"
---
# <a name="coleipframewnd-class"></a>COleIPFrameWnd Sınıfı

Uygulamanızın yerinde düzenleme penceresinin temeli.

## <a name="syntax"></a>Sözdizimi

```
class COleIPFrameWnd : public CFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Bir `COleIPFrameWnd` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Bir öğe yerinde düzenleme için etkinleştirildiğinde çerçeve tarafından çağrılır.|
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Yerinde düzenleme penceresini yeniden konumlandırmak için çerçeve tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, kapsayıcı uygulamanın belge penceresinde denetim çubukları oluşturur ve konumlandırAr. Ayrıca, kullanıcı yerinde düzenleme penceresini yeniden boyutlandırdığında katışılmış bir [COleResizeBar nesnesi](../../mfc/reference/coleresizebar-class.md) tarafından oluşturulan bildirimleri de işler.

Kullanma `COleIPFrameWnd`hakkında daha fazla bilgi için, [makaleetkinleştirme](../../mfc/activation-cpp.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="coleipframewndcoleipframewnd"></a><a name="coleipframewnd"></a>COleIPFrameWnd::COleIPFrameWnd

Bir `COleIPFrameWnd` nesne yi inşa eder ve oleinplaceFRAMEINFO türünde depolanan yerinde durum bilgilerini devreye amer.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [OLEINPLACEFRAMEINFO'ya](/windows/win32/api/oleidl/ns-oleidl-oleinplaceframeinfo) bakın.

## <a name="coleipframewndoncreatecontrolbars"></a><a name="oncreatecontrolbars"></a>COleIPFrameWnd::OnCreateControlBars

Bir öğe `OnCreateControlBars` yerinde düzenleme için etkinleştirildiğinde çerçeve işlevi çağırır.

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
Kapsayıcı uygulamanın çerçeve penceresine işaretçi.

*pWndDoc*<br/>
Kapsayıcının belge düzeyi penceresine işaretçi. Kapsayıcı bir SDI uygulamasıysa NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız başarı; aksi takdirde, 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz. Denetim çubukları oluşturulduğunda gereken özel işlemleri gerçekleştirmek için bu işlevi geçersiz kılın.

## <a name="coleipframewndrepositionframe"></a><a name="repositionframe"></a>COleIPFrameWnd::RepositionFrame

Çerçeve, denetim `RepositionFrame` çubuklarını düzenlemek ve yerinde düzenleme penceresini yeniden konumlandırmak için üye işlevi çağırır, böylece tümü görünür olur.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
Bir `RECT` yapıya veya `CRect` yerinde çerçeve penceresinin geçerli konum koordinatlarını içeren bir nesneye işaretçi, piksellerde, istemci alanına göre.

*lpClipRect*<br/>
Bir `RECT` yapıya veya `CRect` yerinde çerçeve penceresinin istemci alanına göre piksellerde geçerli kırpma dikdörtgeni koordinatlarını içeren bir nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı penceresindeki denetim çubuklarının düzeni, OLE olmayan bir çerçeve penceresi tarafından gerçekleştirilenden farklıdır. OLE olmayan çerçeve penceresi, CFrameWnd'e yapılan bir çağrıda olduğu gibi, denetim çubuklarının ve diğer nesnelerin konumlarını belirli bir çerçeve penceresi boyutundan [hesaplar::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). İstemci alanı, denetim çubukları ve diğer nesneler için alan alındıktan sonra kalan şeydir. Bir `COleIPFrameWnd` pencere, diğer taraftan, belirli bir istemci alanına göre araç çubukları konumlandırın. Başka bir `CFrameWnd::RecalcLayout` deyişle, "dışarıdan içeri" `COleIPFrameWnd::RepositionFrame` işler, "içten dışa" çalışır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)
