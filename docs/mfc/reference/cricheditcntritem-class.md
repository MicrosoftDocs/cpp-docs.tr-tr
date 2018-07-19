---
title: Cricheditcntrıtem sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a0566ef5eead5950f2b4de1f6e1a220f79bcfbe
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849333"
---
# <a name="cricheditcntritem-class"></a>Cricheditcntrıtem sınıfı
İle [CRichEditView](../../mfc/reference/cricheditview-class.md) ve [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), MFC'nin belge görüntüleme mimarisi bağlamında zengin düzenleme denetimi işlevlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Oluşturur bir `CRichEditCntrItem` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Öğe, başka bir tür olarak etkinleştirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 "Zengin düzenleme denetimi" kullanıcı girin ve metin düzenleme bir penceredir. Metnin karakteri ve paragraf biçimlendirme atanabilir ve katıştırılmış OLE nesnelerine içerebilir. Zengin düzenleme denetimleri, metin biçimlendirmesi için bir programlama arabirimi sağlar. Ancak, bir uygulamanın tüm biçimlendirme işlemlerini kullanıcı tarafından kullanılabilir hale getirmek için gerekli olan kullanıcı arabirimi bileşenleri uygulamalıdır.  
  
 `CRichEditView` metin biçimlendirme özelliği ve metin tutar. `CRichEditDoc` OLE istemci Görünümü'nde olan öğelerin listesini tutar. `CRichEditCntrItem` bir OLE istemci öğesi kapsayıcı tarafı erişim sağlar.  
  
 Bu Windows ortak denetimi (ve bu nedenle [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) ve üzeri yalnızca Windows 95/98 ve Windows NT sürümler 3.51 altında çalışan programlar için kullanılabilir.  
  
 Zengin düzenleme kapsayıcı öğeleri bir MFC uygulamasında kullanma örneği için bkz: [WORDPAD](../../visual-cpp-samples.md) örnek uygulama.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [Cdocıtem](../../mfc/reference/cdocitem-class.md)  
  
 [Coleclientıtem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrich.h  
  
##  <a name="cricheditcntritem"></a>  CRichEditCntrItem::CRichEditCntrItem  
 Oluşturmak için bu işlevi çağırın bir `CRichEditCntrItem` nesne ve kapsayıcının belgeye ekleyin.  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *preo*  
 İşaretçi bir [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE öğesini tanımlayan yapısı. Yeni `CRichEditCntrItem` nesne bu OLE öğesini yapılandırılmıştır. Varsa *preo* NULL ise istemci öğesi boş.  
  
 *Implement_serıalıze*  
 Bu öğeyi içeren kapsayıcı belge işaretçisi. Varsa *Implement_serıalıze* null, açıkça çağırmalıdır [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) belge bu istemci öğesi eklemek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, tüm OLE başlatma gerçekleştirmez.  
  
 Daha fazla bilgi için [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Windows SDK'sındaki yapısı.  
  
##  <a name="synctoricheditobject"></a>  CRichEditCntrItem::SyncToRichEditObject  
 Cihaz yönü eşitlemek için bu işlevi çağırın [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318), bu `CRichEditCntrltem` tarafından belirtilen için *yeniden a*.  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>Parametreler  
 *yeniden a*  
 Başvuru bir [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE öğesini tanımlayan yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek WORDPAD](../../visual-cpp-samples.md)   
 [Coleclientıtem sınıfı](../../mfc/reference/coleclientitem-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc sınıfı](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
