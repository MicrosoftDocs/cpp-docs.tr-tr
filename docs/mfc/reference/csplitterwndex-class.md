---
title: CSplitterWndEx sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
dev_langs:
- C++
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a74691b17e04c20fa45045fa4105fd73925f19f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065401"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../hierarchy-chart.md)<br/>
[Sınıflar](mfc-classes.md)<br/>
[CSplitterWnd Sınıfı](csplitterwnd-class.md)<br/>
[CMFCVisualManager Sınıfı](cmfcvisualmanager-class.md)