---
title: CSplitterWndEx Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: d7952e3082bf68cff7ad9ba218073081ee522320
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363917"
---
# <a name="csplitterwndex-class"></a>CSplitterWndEx Sınıfı

Özelleştirilmiş bir ayırıcı pencereyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CSplitterWndEx : public CSplitterWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CSplitterWndEx::CSplitterWndEx`|Varsayılan oluşturucu.|
|`CSplitterWndEx::~CSplitterWndEx`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Bir ayırıcı pencere çizmek için çerçeve tarafından çağrıldı. [(Overrides CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|

## <a name="remarks"></a>Açıklamalar

Ayırıcı `OnDrawSplitter` penceresinin grafik bileşenlerinin görünümünü özelleştirmek için yöntemi geçersiz kılın.

Sınıf, `CSplitterWndEx` Görsel bir yönetici tarafından uygulanan [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox)ve [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) yöntemleri ile birlikte kullanılır. Görsel bir yöneticinin uygulamanızda bir ayırıcı penceresi çizmesine `CSplitterWnd` neden olmak `CSplitterWndEx` için sınıfın bildirimlerini sınıfla değiştirin. Çerçeve penceresi uygulamaları için, splitter penceresi sınıfı mainfrm.h'de bulunan CMainFrame sınıfında bildirilir. Örneğin, Örnekler dizinindeki `OutlookDemo` örneğe bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](cobject-class.md)

[Ccmdtarget](ccmdtarget-class.md)

[Cwnd](cwnd-class.md)

[Csplitterwnd](csplitterwnd-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsplitterwndex.h

## <a name="csplitterwndexondrawsplitter"></a><a name="ondrawsplitter"></a>CSplitterWndEx::OnDrawSplitter

Bir ayırıcı pencere çizmek için çerçeve tarafından çağrıldı.

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamını işaretçi. Bu parametre NULL ise, çerçeve etkin pencereyi yeniden çizer.

*nTipi*<br/>
[içinde] Çizmek için `CSplitterWnd::ESplitType` splitter pencere elemanı belirten numaralandırma değerlerinden biri. Geçerli değerler `splitBox` `splitBar`, `splitIntersection`, `splitBorder`, ve .

*Rect*<br/>
[içinde] Belirtilen ayırıcı pencere öğesini çizmek için boyutları ve konumu belirten sınırlayıcı bir dikdörtgen.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../hierarchy-chart.md)<br/>
[Sınıflar](mfc-classes.md)<br/>
[CSplitterWnd Sınıfı](csplitterwnd-class.md)<br/>
[CMFCVisualManager Sınıfı](cmfcvisualmanager-class.md)
