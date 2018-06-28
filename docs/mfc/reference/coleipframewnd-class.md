---
title: COleIPFrameWnd sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9136f3c57358a71186b196a4223b401e6abad2a9
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040031"
---
# <a name="coleipframewnd-class"></a>COleIPFrameWnd sınıfı
Uygulamanızın yerinde düzenleme penceresinin tabanı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Oluşturan bir `COleIPFrameWnd` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Bir öğe yerinde düzenleme için etkinleştirildiğinde çerçevesi tarafından çağrılır.|  
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Yerinde düzenleme penceresinin yeniden konumlandırmak için çerçevesi tarafından çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf oluşturur ve kapsayıcı uygulamanın belge penceresi içinde çubukları konumlar denetleyebilirsiniz. Ayrıca bir katıştırılmış tarafından oluşturulan bildirimlerini işleme [COleResizeBar](../../mfc/reference/coleresizebar-class.md) nesne kullanıcı yerinde düzenleme yeniden boyutlandırır olduğunda.  
  
 Kullanma hakkında daha fazla bilgi için `COleIPFrameWnd`, makaleye bakın [etkinleştirme](../../mfc/activation-cpp.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="coleipframewnd"></a>  COleIPFrameWnd::COleIPFrameWnd  
 Oluşturan bir `COleIPFrameWnd` nesne ve türü yapısında depolanmış kendi yerinde durum bilgilerini başlatır **OLEINPLACEFRAMEINFO**.  
  
```  
COleIPFrameWnd();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) Windows SDK'sındaki.  
  
##  <a name="oncreatecontrolbars"></a>  COleIPFrameWnd::OnCreateControlBars  
 Framework çağrıları `OnCreateControlBars` işlev öğeyi yerinde düzenleme için etkinleştirildiğinde.  
  
```  
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,  
    CWnd* pWndDoc);

 
virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,  
    CFrameWnd* pWndDoc);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWndFrame*  
 Kapsayıcı uygulamanın çerçeve penceresi işaretçi.  
  
 *pWndDoc*  
 Kapsayıcının belge düzeyi penceresi işaretçi. Olabilir **NULL** kapsayıcı SDI uygulama ise.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı sıfır olmayan; Aksi takdirde, 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama hiçbir şey yapmaz. Denetim çubukları oluştururken gerekli herhangi bir özel işlem gerçekleştirmek için bu işlevi geçersiz kılar.  
  
##  <a name="repositionframe"></a>  COleIPFrameWnd::RepositionFrame  
 Framework çağrıları `RepositionFrame` denetim çubukları düzenlemek ve tüm bu şekilde görünür yerinde düzenleme penceresinin yeniden konumlandırmak için üye işlevi.  
  
```  
virtual void RepositionFrame(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpPosRect*  
 İşaretçi bir `RECT` yapısı veya `CRect` yerinde içeren bir nesne, pencerenin geçerli konumu koordinatları, istemci alanını göreli piksel cinsinden çerçeve.  
  
 *lpClipRect*  
 İşaretçi bir `RECT` yapısı veya `CRect` yerinde içeren bir nesne, pencerenin geçerli dikdörtgen kırpma koordinatları piksel cinsinden istemci alanını göre çerçeve.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim çubukları kapsayıcı penceresinde yerleşimini farklı olarak bir OLE dışı çerçeve pencere tarafından gerçekleştirilen. Denetim çubukları ve bir belirtilen çerçeve pencere boyutu, çağrı olduğu gibi diğer nesnelerden konumlarını OLE dışı çerçeve penceresi hesaplar [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Denetim çubukları ve diğer nesneleri için boşluk çıkarılır sonra ne kalır istemci alanıdır. A `COleIPFrameWnd` penceresinde, diğer yandan, araç çubukları verilen istemci alanını uygun olarak yerleştirir. Diğer bir deyişle, `CFrameWnd::RecalcLayout` çalışır "dışarıdan," ise `COleIPFrameWnd::RepositionFrame` çalışır "Inside out."  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek HIERSVR](../../visual-cpp-samples.md)   
 [CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)
