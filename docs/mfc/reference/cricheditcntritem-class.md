---
title: "CRichEditCntrItem sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
dev_langs: C++
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ebb8cf92a522b63fb88338fe9befacc7d5f1d506
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem sınıfı
İle [CRichEditView](../../mfc/reference/cricheditview-class.md) ve [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), zengin düzenleme denetimine MFC'nin belge görünüm mimarisi bağlamında işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Oluşturan bir `CRichEditCntrItem` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Öğe, başka bir tür olarak etkinleştirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 "Zengin düzenleme denetimi" kullanıcı girin ve metin düzenleme bir penceredir. Metin karakter ve paragraf biçimlendirmesini atanabilir ve katıştırılmış OLE nesnelerine içerebilir. Zengin düzenleme denetimlerinde metin biçimlendirme için bir programlama arabirimi sağlar. Ancak, bir uygulamanın tüm biçimlendirme işlemlerini kullanıcı için kullanılabilir hale getirmek için gerekli olan kullanıcı arabirimi bileşenlerini uygulamalıdır.  
  
 `CRichEditView`metin ve biçimlendirme karakteristiğini metin, tutar. `CRichEditDoc`OLE istemci görünümünde olan bir öğe listesini tutar. `CRichEditCntrItem`OLE istemci öğesi kapsayıcı tarafı erişim sağlar.  
  
 Bu Windows yaygın bir denetim (ve bu nedenle [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) yalnızca Windows 95/98 ve Windows NT sürümler 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Zengin düzenleme kapsayıcı öğeler bir MFC uygulamasında kullanarak bir örnek için bkz: [WORDPAD](../../visual-cpp-samples.md) örnek uygulama.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrich.h  
  
##  <a name="cricheditcntritem"></a>CRichEditCntrItem::CRichEditCntrItem  
 Oluşturmak için bu işlevi çağırmak bir `CRichEditCntrItem` nesne ve kapsayıcı belgeye ekleyin.  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *preo*  
 İşaretçi bir [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE öğeyi tanımlayan yapısı. Yeni `CRichEditCntrItem` nesnesi, bu OLE öğenin etrafında yapılandırılmıştır. Varsa *preo* olan **NULL**, istemci öğesi boş.  
  
 `pContainer`  
 Bu öğeyi içerecek kapsayıcı belge işaretçi. Varsa `pContainer` olan **NULL**, açıkça çağırmalısınız [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) bir belgeye bu istemci öğesi eklemek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, tüm OLE başlatma işlemini gerçekleştirir.  
  
 Daha fazla bilgi için bkz: [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Windows SDK'sındaki yapısı.  
  
##  <a name="synctoricheditobject"></a>CRichEditCntrItem::SyncToRichEditObject  
 Cihaz en boy eşitlemek için bu işlevi çağırmak [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318), bu **CRichEditCntrltem** tarafından belirtilen için *yeniden a*.  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>Parametreler  
 *yeniden a*  
 Başvuru bir [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE öğeyi tanımlayan yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek WORDPAD](../../visual-cpp-samples.md)   
 [COleClientItem sınıfı](../../mfc/reference/coleclientitem-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc sınıfı](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
