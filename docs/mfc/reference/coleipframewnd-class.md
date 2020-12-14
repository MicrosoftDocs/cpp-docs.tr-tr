---
description: 'Daha fazla bilgi edinin: Cotaipframewnd sınıfı'
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
ms.openlocfilehash: d89cfa9b3f6d610276c3c972ee48c943f753e36a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227019"
---
# <a name="coleipframewnd-class"></a>Cotaipframewnd sınıfı

Uygulamanızın yerinde düzenlemesi penceresi için temel.

## <a name="syntax"></a>Syntax

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

Kullanma hakkında daha fazla bilgi için `COleIPFrameWnd` bkz. [etkinleştirme](../../mfc/activation-cpp.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="coleipframewndcoleipframewnd"></a><a name="coleipframewnd"></a> Copaipframewnd:: Cotaipframewnd

Bir `COleIPFrameWnd` nesnesi oluşturur ve OLEıNPLACEFRAMEıNFO türünde bir yapıda saklanan yerinde durum bilgilerini başlatır.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK için bkz. [OLEINPLACEFRAMEINFO](/windows/win32/api/oleidl/ns-oleidl-oleinplaceframeinfo) .

## <a name="coleipframewndoncreatecontrolbars"></a><a name="oncreatecontrolbars"></a> Cotaipframewnd:: Oncreatecontrolçubuklar

Çerçeve, `OnCreateControlBars` bir öğe yerinde düzenlenmek üzere etkinleştirildiğinde işlevi çağırır.

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

## <a name="coleipframewndrepositionframe"></a><a name="repositionframe"></a> Cotaipframewnd:: Depotionframe

Çerçeve, `RepositionFrame` Denetim çubuklarını düzenlemek ve yerinde düzenleme penceresini tüm görünür hale gelecek şekilde yeniden konumlandırmak için üye işlevini çağırır.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Parametreler

*lpPosRect*<br/>
Bir `RECT` yapıya veya `CRect` yerinde çerçeve penceresinin geçerli konum koordinatlarını, istemci alanına göre piksel cinsinden içeren bir nesne işaretçisi.

*lpClipRect*<br/>
Bir `RECT` yapıya veya `CRect` yerinde çerçeve penceresinin geçerli kırpmasını içeren bir nesneye işaretçi, istemci alanına göre piksel cinsinden.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı penceresindeki denetim çubuklarının düzeni, OLE olmayan bir çerçeve penceresi tarafından gerçekleştirilen eyleminden farklıdır. OLE dışı çerçeve olmayan pencere, bir [CFrameWnd:: RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout)çağrısında olduğu gibi, belirli bir çerçeve pencere boyutundan denetim çubuklarının ve diğer nesnelerin konumlarını hesaplar. İstemci alanı, denetim çubukları ve diğer nesnelerin çıkarılmasıyla sonra kalmaya devam eder. `COleIPFrameWnd`Diğer yandan bir pencere, araç çubuklarını belirli bir istemci alanına uygun olarak konumlandırır. Diğer bir deyişle, "dışarıdan" içinden "," içinde "çalışarak" `CFrameWnd::RecalcLayout` `COleIPFrameWnd::RepositionFrame`

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)
