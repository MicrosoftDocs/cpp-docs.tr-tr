---
title: Cotaipframewnd sınıfı
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
ms.openlocfilehash: 8eab2ddfc778900b53d77105f1d8215a2c095e9f
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741568"
---
# <a name="coleipframewnd-class"></a>Cotaipframewnd sınıfı

Uygulamanızın yerinde düzenlemesi penceresi için temel.

## <a name="syntax"></a>Sözdizimi

```
class COleIPFrameWnd : public CFrameWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copaipframewnd:: Cotaipframewnd](#coleipframewnd)|Bir `COleIPFrameWnd` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotaipframewnd:: Oncreatecontrolçubuklar](#oncreatecontrolbars)|Yerinde düzenlenmek için bir öğe etkinleştirildiğinde Framework tarafından çağırılır.|
|[Cotaipframewnd:: Depotionframe](#repositionframe)|Yerinde düzenleyen pencerenin yeniden konumlandırılabilmesi için Framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, kapsayıcı uygulamasının belge penceresi içinde denetim çubukları oluşturur ve konumlandırır. Ayrıca, Kullanıcı yerinde Düzenle penceresini yeniden boyutlandırdığında gömülü bir [COleResizeBar](../../mfc/reference/coleresizebar-class.md) nesnesi tarafından oluşturulan bildirimleri de işler.

Kullanma `COleIPFrameWnd`hakkında daha fazla bilgi için bkz. [etkinleştirme](../../mfc/activation-cpp.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

##  <a name="coleipframewnd"></a>Copaipframewnd:: Cotaipframewnd

Bir `COleIPFrameWnd` nesnesi oluşturur ve OLEINPLACEFRAMEINFO türünde bir yapıda saklanan yerinde durum bilgilerini başlatır.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK için bkz. [OLEINPLACEFRAMEINFO](/windows/win32/api/oleidl/ns-oleidl-oleinplaceframeinfo) .

##  <a name="oncreatecontrolbars"></a>Cotaipframewnd:: Oncreatecontrolçubuklar

Çerçeve, bir öğe `OnCreateControlBars` yerinde düzenlenmek üzere etkinleştirildiğinde işlevi çağırır.

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
Kapsayıcı uygulamasının çerçeve penceresine yönelik işaretçi.

*pWndDoc*<br/>
Kapsayıcının belge düzeyi penceresine yönelik işaretçi. Kapsayıcı bir SDI uygulaması ise NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırdan farklı, başarılı olma; Aksi takdirde, 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama hiçbir şey yapmaz. Denetim çubukları oluşturulduğunda gereken özel işlemleri gerçekleştirmek için bu işlevi geçersiz kılın.

##  <a name="repositionframe"></a>Cotaipframewnd:: Depotionframe

Çerçeve, denetim çubuklarını `RepositionFrame` düzenlemek ve yerinde düzenleme penceresini tüm görünür hale gelecek şekilde yeniden konumlandırmak için üye işlevini çağırır.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
Bir `RECT` yapıya`CRect` veya yerinde çerçeve penceresinin geçerli konum koordinatlarını, istemci alanına göre piksel cinsinden içeren bir nesne işaretçisi.

*lpClipRect*<br/>
Bir `RECT` yapıya veya yerinde çerçeve penceresinin `CRect` geçerli kırpmasını içeren bir nesneye işaretçi, istemci alanına göre piksel cinsinden.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı penceresindeki denetim çubuklarının düzeni, OLE olmayan bir çerçeve penceresi tarafından gerçekleştirilen eyleminden farklıdır. OLE dışı çerçeve olmayan pencere, bir [CFrameWnd:: RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout)çağrısında olduğu gibi, belirli bir çerçeve pencere boyutundan denetim çubuklarının ve diğer nesnelerin konumlarını hesaplar. İstemci alanı, denetim çubukları ve diğer nesnelerin çıkarılmasıyla sonra kalmaya devam eder. Diğer `COleIPFrameWnd` yandan bir pencere, araç çubuklarını belirli bir istemci alanına uygun olarak konumlandırır. Diğer bir deyişle `CFrameWnd::RecalcLayout` , "dışarıdan `COleIPFrameWnd::RepositionFrame` " içinden "," içinde "çalışarak"

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)
