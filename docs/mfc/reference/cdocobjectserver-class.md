---
title: "CDocObjectServer sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
dev_langs:
- C++
helpviewer_keywords:
- CDocObjectServer [MFC], CDocObjectServer
- CDocObjectServer [MFC], ActivateDocObject
- CDocObjectServer [MFC], OnActivateView
- CDocObjectServer [MFC], OnApplyViewState
- CDocObjectServer [MFC], OnSaveViewState
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 912262c4f1ba85c181bb30ee5d6f38a0defe5d5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdocobjectserver-class"></a>CDocObjectServer sınıfı
Normal bir yapmak için gereken ek OLE arabirimleri uygulayan `COleDocument` tam DocObject sunucu Server'a: `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`, ve `IPrint`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|Oluşturan bir `CDocObjectServer` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|Belge nesnesi sunucusu etkinleştirir, ancak bunu göstermez.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocObjectServer::OnActivateView](#onactivateview)|DocObject görünüm görüntüler.|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|DocObject görünüm durumunu geri yükler.|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|DocObject görünüm durumunu kaydeder.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDocObjectServer`türetilmiş `CCmdTarget` ve yakın bir tümleştirmede çalışır `COleServerDoc` arabirimleri kullanıma sunmak için.  
  
 Bir DocObject sunucusu belgesi içerebilir [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) sunucu arabirimi DocObject öğelerine temsil eden nesne.  
  
 DocObject sunucunuz özelleştirmek için kendi sınıfından türetilen `CDocObjectServer` ve kendi görünüm Kurulum işlevleri geçersiz kılma [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate), ve [OnSaveViewState ](#onsaveviewstate). Framework çağrıları yanıta sınıfınızda yeni bir örneğini sağlamanız gerekir.  
  
 DocObjects hakkında daha fazla bilgi için bkz: [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) ve [COleCmdUI](../../mfc/reference/colecmdui-class.md) içinde *MFC başvurusu*. Ayrıca bkz. [Internet ilk adımlar: etkin belgeler](../../mfc/active-documents-on-the-internet.md) ve [etkin belgeler](../../mfc/active-documents-on-the-internet.md).  
  
 Ayrıca aşağıdaki Bilgi Bankası makalesine bakın:  
  
-   Q247382: Sorun: ActiveX belge sunucusu denetimler için araç ipuçları ActiveX belge kapsayıcısı tarafından gizli  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdocob.h  
  
##  <a name="activatedocobject"></a>CDocObjectServer::ActivateDocObject  
 Belge nesnesi sunucusu etkinleştirin (ancak gösterme için) bu işlevini çağırın.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `ActivateDocObject`çağrıları `IOleDocumentSite`'s **ActivateMe** yöntemi, ayarlama ve çağrısında verilen görünümü görüntüleme hakkında belirli yönergeler bekler olduğundan görünüm göstermez ancak [CDocObjectServer::OnActivateView](#onactivateview).  
  
 Birlikte `ActivateDocObject` ve `OnActivateView` etkinleştirin ve DocObject görünümü görüntüleyin. DocObject etkinleştirme OLE yerinde etkinleştirme diğer tür farklı. DocObject etkinleştirme yerinde tarama Kenarlıklar ve (örneğin boyutlandırma) nesne adornments görüntüleme atlar, nesne ölçüde işlevleri yoksayar ve bunları bu dikdörtgeni (olduğu gibi normal dışında çizim aksine dikdörtgen görünümün içinde kaydırma çubukları çizer yerinde etkinleştirme).  
  
##  <a name="cdocobjectserver"></a>CDocObjectServer::CDocObjectServer  
 Oluşturur ve başlatır bir `CDocObjectServer` nesnesi.  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *pOwner*  
 İstemci DocObject sunucu için istemci site belgesi için bir işaretçi.  
  
 `pDocSite`  
 Bir işaretçi `IOleDocumentSite` kapsayıcı tarafından uygulanan arabirimi.  
  
### <a name="remarks"></a>Açıklamalar  
 DocObject etkin olduğunda, istemci site OLE arabirimi ( `IOleDocumentSite`) olan ne DocObject server kendi istemci (kapsayıcı) ile iletişim kurmasını sağlar. DocObject sunucusu etkinleştirildiğinde, ilk kapsayıcı uyguladığını denetler `IOleDocumentSite` arabirimi. Bu durumda, [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) kapsayıcı DocObjects destekleyip desteklemediğini görmek için çağrılır. Varsayılan olarak, `GetDocObjectServer` döndürür **NULL**. Geçersiz kılmanız gerekir `COleServerDoc::GetDocObjectServer` yeni oluşturmak için `CDocObjectServer` veya kendi ile işaretçileri, türetilmiş bir nesneyi `COleServerDoc` kapsayıcısı ve onun `IOleDocumentSite` oluşturucu bağımsız değişken olarak arabirimi.  
  
##  <a name="onactivateview"></a>CDocObjectServer::OnActivateView  
 DocObject görüntülemek için bu işlevini çağırın.  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata veya uyarı değeri döndürür. Varsayılan olarak, döndürür **NOERROR** başarılı; Aksi takdirde **E_FAIL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bir yerinde çerçeve penceresi oluşturur, görünümü içinde scrollbars çizer, sunucu kapsayıcısı ile paylaşır, çerçeve denetimleri ekler, etkin nesne ayarlar daha sonra son yerinde çerçeve penceresi gösterir ve odağı ayarlar menüleri ayarlar.  
  
##  <a name="onapplyviewstate"></a>CDocObjectServer::OnApplyViewState  
 Bu işlev DocObject görünüm durumunu geri yüklemek için geçersiz kılar.  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 `ar`  
 A `CArchive` görünüm durumu serileştirmek nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Görünüm kendi örneklemesi sonra ilk kez görüntülenmektedir olduğunda bu işlev çağrılır. `OnApplyViewState`verileri göre kendisini yeniden başlatmak için bir görünüm bildirir `CArchive` ile daha önce kaydettiğiniz nesne [OnSaveViewState](#onsaveviewstate). Görünüm verileri doğrulamalısınız `CArchive` kapsayıcı görünüm durumu verilerini herhangi bir şekilde yorumlamaya çalışmaz çünkü nesne.  
  
 Kullanabileceğiniz `OnSaveViewState` , görünümün durumuna özgü kalıcı bilgileri depolamak için. Geçersiz kılarsanız `OnSaveViewState` bilgileri depolamak için geçersiz kılmak istediğiniz `OnApplyViewState` bu bilgileri okuyun ve yeni etkinleştirildiğinde, görünüme uygulamak için.  
  
##  <a name="onsaveviewstate"></a>CDocObjectServer::OnSaveViewState  
 Bu işlev DocObject görünümünüzü hakkında ek durum bilgilerini kaydetmek için geçersiz kılar.  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 `ar`  
 A `CArchive` nesne görünüm durumu seri değildir.  
  
### <a name="remarks"></a>Açıklamalar  
 Durumunuza görünüm türü, yakınlaştırma faktörünü, ekleme ve seçim noktası ve benzerleri gibi özellikler içerebilir. Kapsayıcı görünümü devre dışı bırakmadan önce bu işlevin genellikle çağırır. Kaydedilmiş durumu daha sonra aracılığıyla geri yüklenebilir [OnApplyViewState](#onapplyviewstate).  
  
 Kullanabileceğiniz `OnSaveViewState` , görünümün durumuna özgü kalıcı bilgileri depolamak için. Geçersiz kılarsanız `OnSaveViewState` bilgileri depolamak için geçersiz kılmak istediğiniz `OnApplyViewState` bu bilgileri okuyun ve yeni etkinleştirildiğinde, görünüme uygulamak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem Sınıfı](../../mfc/reference/cdocobjectserveritem-class.md)
