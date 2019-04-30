---
title: CSplitterWndEx sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: 8dedad4e99a37b13dc618859c8e6d8a83a65ea76
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339608"
---
# <a name="csplitterwndex-class"></a>CSplitterWndEx sınıfı

Özelleştirilmiş Bölümlendirici pencereyi temsil eder.

## <a name="syntax"></a>Sözdizimi

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
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Ayırıcı penceresi çizmek için framework tarafından çağırılır. (Geçersiz kılmaları [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|

## <a name="remarks"></a>Açıklamalar

Geçersiz kılma `OnDrawSplitter` bir ayırıcı penceresi grafik bileşenlerden görünümünü özelleştirmek için yöntemi.

`CSplitterWndEx` Sınıfı ile birlikte kullanılır [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox), ve [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) olan yöntemler görsel yönetici tarafından uygulanır. Ayırıcı penceresi, uygulamanızda çizmek bir görsel yöneticiyi neden olmak için bildirimleri yerine `CSplitterWnd` sınıfıyla `CSplitterWndEx` sınıfı. Çerçeve penceresi uygulamalar için Bölümlendirici pencere sınıfını mainfrm.h içinde bulunan CMainFrame sınıfı olarak bildirilir. Bir örnek için bkz `OutlookDemo` örnekleri dizinde örnek.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

[CSplitterWnd](csplitterwnd-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxsplitterwndex.h

##  <a name="ondrawsplitter"></a>  CSplitterWndEx::OnDrawSplitter

Ayırıcı penceresi çizmek için framework tarafından çağırılır.

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Cihaz bağlamı işaretçisi. Bu parametre NULL ise, framework etkin pencereyi yeniden çizer.

*nTür*<br/>
[in] Aşağıdakilerden birini `CSplitterWnd::ESplitType` çizmek için Bölümlendirici pencere öğesini belirten numaralandırma değerlerinden. Geçerli değerler `splitBox`, `splitBar`, `splitIntersection`, ve `splitBorder`.

*Rect*<br/>
[in] Belirtilen Bölümlendirici pencere öğesinin çizmek için konum ve boyut belirtir sınırlayıcı bir dikdörtgen.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../hierarchy-chart.md)<br/>
[Sınıflar](mfc-classes.md)<br/>
[CSplitterWnd Sınıfı](csplitterwnd-class.md)<br/>
[CMFCVisualManager Sınıfı](cmfcvisualmanager-class.md)
