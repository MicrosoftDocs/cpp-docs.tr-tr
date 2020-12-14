---
description: 'Daha fazla bilgi edinin: CSplitterWndEx sınıfı'
title: CSplitterWndEx sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: 357f650551871cc9768c8e4e693bd62bb5e69bc4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345101"
---
# <a name="csplitterwndex-class"></a>CSplitterWndEx sınıfı

Özelleştirilmiş bir ayırıcı pencereyi temsil eder.

## <a name="syntax"></a>Syntax

```
class CSplitterWndEx : public CSplitterWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CSplitterWndEx::CSplitterWndEx`|Varsayılan Oluşturucu.|
|`CSplitterWndEx::~CSplitterWndEx`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSplitterWndEx:: OnDrawSplitter](#ondrawsplitter)|Ayırıcı penceresi çizmek için Framework tarafından çağırılır. ( [CSplitterWnd:: OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter)geçersiz kılar.)|

## <a name="remarks"></a>Açıklamalar

`OnDrawSplitter`Ayırıcı penceresinin grafik bileşenlerinin görünümünü özelleştirmek için yöntemini geçersiz kılın.

`CSplitterWndEx`Sınıfı, bir Visual Manager tarafından uygulanan [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox)ve [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) yöntemleriyle birlikte kullanılır. Visual Manager 'ın uygulamanızda bir ayırıcı pencere çizmesine neden olmak için `CSplitterWnd` sınıf bildirimlerini `CSplitterWndEx` sınıfıyla değiştirin. Çerçeve penceresi uygulamaları için, splitter pencere sınıfı, MainFrm. h içinde bulunan Canabilgisayar sınıfında bildirilmiştir. Örnek için `OutlookDemo` örnekler dizinindeki örneğe bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

[CSplitterWnd](csplitterwnd-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsplitterwndex. h

## <a name="csplitterwndexondrawsplitter"></a><a name="ondrawsplitter"></a> CSplitterWndEx:: OnDrawSplitter

Ayırıcı penceresi çizmek için Framework tarafından çağırılır.

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamı işaretçisi. Bu parametre NULL ise, çerçeve etkin pencereyi yeniden çizer.

*nTür*<br/>
'ndaki `CSplitterWnd::ESplitType` Çizilecek ayırıcı pencere öğesini belirten sabit listesi değerlerinden biri. Geçerli değerler `splitBox`, `splitBar`, `splitIntersection` veya `splitBorder` değerleridir.

*Rect*<br/>
'ndaki Belirtilen ayırıcı pencere öğesinin çizileceği boyutları ve konumu belirten bir sınırlayıcı dikdörtgen.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../hierarchy-chart.md)<br/>
[Sınıflar](mfc-classes.md)<br/>
[CSplitterWnd sınıfı](csplitterwnd-class.md)<br/>
[CMFCVisualManager sınıfı](cmfcvisualmanager-class.md)
