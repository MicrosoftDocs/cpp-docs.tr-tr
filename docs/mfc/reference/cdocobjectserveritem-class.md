---
title: CDocObjectServerItem sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
dev_langs:
- C++
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c6f990a00fb96195a54ee7ed6906068985b052f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367054"
---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem sınıfı
Implements OLE sunucu fiilleri özellikle DocObject sunucuları için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Oluşturan bir `CDocObjectServerItem` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](#getdocument)|Öğeyi içeren belge için bir işaretçi alır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](#onhide)|DocObject öğesini gizlemek framework çalışırsa, bir özel durum oluşturur.|  
|[CDocObjectServerItem::OnShow](#onshow)|Öğesi yerinde DocObject yapma çerçevesi tarafından çağrılır etkin. Öğe DocObject değilse, çağıran [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDocObjectServerItem` geçersiz kılınabilir üye işlevleri tanımlar: [OnHide](#onhide), [açıldığında](http://msdn.microsoft.com/en-us/7a9b1363-6ad8-4732-9959-4e35c07644fd), ve [OnShow](#onshow).  
  
 Kullanılacak `CDocObjectServerItem`, güvence altına almak [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) geçersiz kılması, `COleServerDoc`-türetilen sınıfın yeni bir döndürür `CDocObjectServerItem` nesnesi. Öğenizi herhangi bir işlevsellik değiştirmeniz gerekiyorsa, yeni bir örneğini kendi oluşturabilirsiniz `CDocObjectServerItem`-türetilmiş sınıf.  
  
 DocObjects hakkında daha fazla bilgi için bkz: [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) ve [COleCmdUI](../../mfc/reference/colecmdui-class.md) içinde *MFC başvurusu*. Ayrıca bkz. [Internet ilk adımlar: etkin belgeler](../../mfc/active-documents-on-the-internet.md) ve [etkin belgeler](../../mfc/active-documents-on-the-internet.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdocob.h  
  
##  <a name="cdocobjectserveritem"></a>  CDocObjectServerItem::CDocObjectServerItem  
 Oluşturan bir `CDocObjectServerItem` nesnesi.  
  
```  
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Parametreler  
 `pServerDoc`  
 Yeni DocObject öğeyi içerecek belge için bir işaretçi.  
  
 `bAutoDelete`  
 Bir bağlantı serbest bırakıldığında nesne silinebilir olup olmadığını gösterir. Bağımsız değişken kümesine **FALSE** varsa `CDocObjectServerItem` nesnesidir belgenizin veri ayrılmaz bir parçasıdır. Ayarlamak **TRUE** nesne çerçevesi tarafından silinebilir belgenizin verileri içindeki bir aralık tanımlamak için kullanılan ikincil bir yapı ise.  
  
##  <a name="getdocument"></a>  CDocObjectServerItem::GetDocument  
 Öğeyi içeren belge için bir işaretçi alır.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeyi içeren belge için bir işaretçi; **NULL** öğesi belgenin bir bölümünü değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bağımsız değişken olarak geçirilen sunucu belgeye erişimi sağlayan [CDocObjectServerItem](#cdocobjectserveritem) Oluşturucusu.  
  
##  <a name="onhide"></a>  CDocObjectServerItem::OnHide  
 Öğesini gizlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğe DocObject ise varsayılan uygulaması bir özel durum oluşturur. Tam görünümü aldığından etkin DocObject öğeyi gizleyemezsiniz. Kayboluyor yapmak için DocObject öğesi devre dışı bırakmanız gerekir. Öğe DocObject değilse, varsayılan uygulamasını çağıran [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).  
  
##  <a name="onshow"></a>  CDocObjectServerItem::OnShow  
 Öğesi yerinde DocObject yapmak için sunucu uygulaması istemek üzere çerçevesi tarafından çağrılır etkin.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğe DocObject değilse, varsayılan uygulamasını çağıran [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Özel bir DocObject öğesi açarken işleme gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COleServerItem sınıfı](../../mfc/reference/coleserveritem-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer sınıfı](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem Sınıfı](../../mfc/reference/coledocobjectitem-class.md)
