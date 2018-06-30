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
ms.openlocfilehash: 0ae4a24424acc4385927e0f7c99735bd50a6d472
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121656"
---
# <a name="csplitterwndex-class"></a>CSplitterWndEx sınıfı



Özelleştirilmiş Bölümlendirici pencere temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSplitterWndEx : public CSplitterWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CSplitterWndEx::CSplitterWndEx`|Varsayılan Oluşturucu.|  
|`CSplitterWndEx::~CSplitterWndEx`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Bölümlendirici pencere çizmek için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Geçersiz kılma `OnDrawSplitter` Bölümlendirici pencere grafik bileşenlerinin görünümünü özelleştirmek için yöntem.  
  
 `CSplitterWndEx` Sınıfı ile birlikte kullanılır [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox), ve [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) olan yöntemleri görsel Yöneticisi tarafından uygulanır. Bölümlendirici pencere uygulamanızda çizmek görsel bir Yöneticisi neden için bildirimlerini yerini `CSplitterWnd` ile sınıfı `CSplitterWndEx` sınıfı. Çerçeve penceresi uygulamalar için mainfrm.h içinde bulunan CMainFrame sınıfı içinde Bölümlendirici pencere sınıfı bildirilir. Bir örnek için bkz: `OutlookDemo` örnekleri dizininde örnek.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 [CSplitterWnd](csplitterwnd-class.md)  
   
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxsplitterwndex.h  
  
##  <a name="ondrawsplitter"></a>  CSplitterWndEx::OnDrawSplitter  
 Bölümlendirici pencere çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawSplitter(  
   CDC* pDC,  
   ESplitType nType,  
   const CRect& rect   
);  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Cihaz bağlamı işaretçi. Bu parametre NULL ise, framework etkin pencereyi yeniden çizer.  
  
 [in] *nTür*  
 Aşağıdakilerden birini `CSplitterWnd::ESplitType` çizmek için Bölümlendirici pencere öğesi belirten numaralandırma değerlerinin. Geçerli değerler `splitBox`, `splitBar`, `splitIntersection`, ve `splitBorder`.  
  
 [in] *rect*  
 Bir sınırlayıcı dikdörtgenini boyutları ve belirtilen Bölümlendirici pencere öğesi çizmek için konumu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../hierarchy-chart.md)   
 [Sınıfları](mfc-classes.md)   
 [CSplitterWnd sınıfı](csplitterwnd-class.md)   
 [CMFCVisualManager Sınıfı](cmfcvisualmanager-class.md)