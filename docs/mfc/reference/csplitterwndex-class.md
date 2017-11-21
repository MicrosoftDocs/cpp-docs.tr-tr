---
title: "CSplitterWndEx sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
dev_langs: C++
helpviewer_keywords: CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e45a136941ccaf34108085a14ddefb64bcdb3fa4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
##  <a name="ondrawsplitter"></a>CSplitterWndEx::OnDrawSplitter  
 Bölümlendirici pencere çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawSplitter(  
   CDC* pDC,  
   ESplitType nType,  
   const CRect& rect   
);  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Cihaz bağlamı işaretçi. Bu parametre ise `NULL`, framework etkin pencereyi yeniden çizer.  
  
 [in]`nType`  
 Aşağıdakilerden birini `CSplitterWnd::ESplitType` çizmek için Bölümlendirici pencere öğesi belirten numaralandırma değerlerinin. Geçerli değerler `splitBox`, `splitBar`, `splitIntersection`, ve `splitBorder`.  
  
 [in]`rect`  
 Bir sınırlayıcı dikdörtgenini boyutları ve belirtilen Bölümlendirici pencere öğesi çizmek için konumu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../hierarchy-chart.md)   
 [Sınıfları](mfc-classes.md)   
 [CSplitterWnd sınıfı](csplitterwnd-class.md)   
 [CMFCVisualManager sınıfı](cmfcvisualmanager-class.md)