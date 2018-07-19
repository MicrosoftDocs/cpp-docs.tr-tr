---
title: CDocObjectServer sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 701cfc2f8a88f57a1c50c9c4310ecd21154ef09a
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337872"
---
# <a name="cdocobjectserver-class"></a>CDocObjectServer sınıfı
Normal hale getirmek için gereken ek OLE arabirimlerini uygular `COleDocument` sunucu bir tam DocObject sunucusuna: `IOleDocument`, `IOleDocumentView`, `IOleCommandTarget`, ve `IPrint`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDocObjectServer : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocObjectServer::CDocObjectServer](#cdocobjectserver)|Oluşturur bir `CDocObjectServer` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocObjectServer::ActivateDocObject](#activatedocobject)|Belge nesnesi sunucusu etkinleştirir, ancak bunu göstermez.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDocObjectServer::OnActivateView](#onactivateview)|DocObject görünümünü gösterir.|  
|[CDocObjectServer::OnApplyViewState](#onapplyviewstate)|DocObject görünümünün durumunu geri yükler.|  
|[CDocObjectServer::OnSaveViewState](#onsaveviewstate)|DocObject görünümünün durumunu kaydeder.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDocObjectServer` türetilen `CCmdTarget` ve yakın bir tümleştirmede çalışır `COleServerDoc` arabirimleri kullanıma sunmak için.  
  
 DocObject sunucusuna belge içerebilir [Cdocobjectserverıtem](../../mfc/reference/cdocobjectserveritem-class.md) sunucu arabirimi DocObject öğeleri temsil eden nesneleri.  
  
 DocObject sunucunuzun özelleştirmek için kendi sınıfından türetilen `CDocObjectServer` ve kendi görünüm Kurulum işlevleri geçersiz kılma [OnActivateView](#onactivateview), [OnApplyViewState](#onapplyviewstate), ve [OnSaveViewState ](#onsaveviewstate). Sınıfınıza yanıt framework çağrıları olarak yeni bir örneğini sağlamanız gerekir.  
  
 DocObjects hakkında daha fazla bilgi için bkz: [Cdocobjectserverıtem](../../mfc/reference/cdocobjectserveritem-class.md) ve [Colecmduı](../../mfc/reference/colecmdui-class.md) içinde *MFC başvurusu*. Ayrıca bkz: [Internet ilk adımlar: etkin belgeler](../../mfc/active-documents-on-the-internet.md) ve [etkin belgeler](../../mfc/active-documents-on-the-internet.md).  
  
 Ayrıca aşağıdaki Bilgi Bankası makalesine bakın:  
  
-   Q247382: Sorun: ActiveX belge sunucusu denetimler için ToolTips ActiveX belgesini kapsayıcı tarafından gizli  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocObjectServer`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdocob.h  
  
##  <a name="activatedocobject"></a>  CDocObjectServer::ActivateDocObject  
 Belge nesnesi sunucusu etkinleştir (ancak değil göstermek için) bu işlevi çağırın.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `ActivateDocObject` çağrıları `IOleDocumentSite`'s `ActivateMe` yöntemi ayarlamak ve çağrı verilen görünümü görüntülemek belirli yönergeler bitirmesini beklediğinden görünümü göstermez ancak [CDocObjectServer::OnActivateView](#onactivateview).  
  
 Birlikte `ActivateDocObject` ve `OnActivateView` etkinleştirmek ve DocObject görünümünü görüntüleyin. DocObject etkinleştirme diğer OLE yerinde etkinleştirme türlerindeki farklıdır. DocObject etkinleştirme yerinde tarama Kenarlıklar ve nesne Kenarlıklar (gibi boyutlandırma) görüntüleme atlar, nesne uzantı işlevleri yoksayar ve bunları bu dikdörtgeni (olduğu gibi normal dışında çizim yerine dikdörtgen görünümün içinde kaydırma çubukları çizer yerinde etkinleştirme için).  
  
##  <a name="cdocobjectserver"></a>  CDocObjectServer::CDocObjectServer  
 Oluşturur ve başlatır bir `CDocObjectServer` nesne.  
  
```  
explicit CDocObjectServer(
    COleServerDoc* pOwner,  
    LPOLEDOCUMENTSITE pDocSite = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *pOwner*  
 DocObject sunucusu için istemci istemci site belgeye bir işaretçi.  
  
 *pDocSite*  
 Bir işaretçi `IOleDocumentSite` kapsayıcı tarafından uygulanan arabirimi.  
  
### <a name="remarks"></a>Açıklamalar  
 DocObject etkin olduğunda, istemcinin site OLE arabirimi ( `IOleDocumentSite`) ne istemcisini (kapsayıcı) ile iletişim kurmak DocObject sunucusuna sağlar. DocObject sunucusuna etkinleştirildiğinde, ilk kapsayıcı uyguladığını denetler `IOleDocumentSite` arabirimi. Bu durumda, [COleServerDoc::GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) kapsayıcı DocObjects destekleyip desteklemediğini görmek için çağrılır. Varsayılan olarak, `GetDocObjectServer` NULL döndürür. Geçersiz kılmanız gerekir `COleServerDoc::GetDocObjectServer` yeni oluşturmak için `CDocObjectServer` veya türetilmiş bir nesneyi kendi ile işaretçiler `COleServerDoc` kapsayıcısı ve onun `IOleDocumentSite` arabirimi oluşturucu bağımsız değişkenleri olarak.  
  
##  <a name="onactivateview"></a>  CDocObjectServer::OnActivateView  
 DocObject görünümünü görüntülemek için bu işlevi çağırın.  
  
```  
virtual HRESULT OnActivateView();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hata veya uyarı değeri döndürür. Varsayılan olarak, NOERROR döndürür başarılıysa; Aksi takdirde, E_FAIL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bir yerinde çerçeve penceresi oluşturur, kaydırma çubukları görünümündeki çizer, sunucu kapsayıcısı ile paylaşır, çerçeve denetimleri ekler, etkin bir nesne ayarlar daha sonra son yerinde çerçeve penceresini gösterir ve odağı ayarlar menüleri ayarlar.  
  
##  <a name="onapplyviewstate"></a>  CDocObjectServer::OnApplyViewState  
 DocObject görünümünün durumunu geri yüklemek için bu işlevi geçersiz kılar.  
  
```  
virtual void OnApplyViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 *ar*  
 A `CArchive` nesnesi, Görünüm durumu serileştirmek.  
  
### <a name="remarks"></a>Açıklamalar  
 Görünüm, örnekleme sonra ilk kez görüntülenmektedir olduğunda bu işlev çağrılır. `OnApplyViewState` bir görünüm verilere göre kendini yeniden başlatmasını bildirir `CArchive` nesne ile daha önce kaydettiğiniz [OnSaveViewState](#onsaveviewstate). Görünüm verileri doğrulamalıdır `CArchive` kapsayıcı görünüm durumu verilerinin herhangi bir şekilde yorumlamaya çalışmaz çünkü nesne.  
  
 Kullanabileceğiniz `OnSaveViewState` görünümünüzün durumuna özgü kalıcı bilgileri depolamak için. Kılarsanız `OnSaveViewState` bilgileri depolamak için geçersiz kılmak istediğiniz `OnApplyViewState` bu bilgileri okuyun ve yeni etkinleştirildiğinde görünümünüzü uygulamak için.  
  
##  <a name="onsaveviewstate"></a>  CDocObjectServer::OnSaveViewState  
 DocObject görünümünüzü ilgili ek durum bilgisini kaydetmek için bu işlevi geçersiz kılar.  
  
```  
virtual void OnSaveViewState(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 *ar*  
 A `CArchive` görünüm durumu serileştirildiği nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Görünüm türü, yakınlaştırma faktörünü, ekleme ve seçim noktası ve benzeri gibi özelliklerini, durumunu içerebilir. Kapsayıcı genellikle görünümü devre dışı bırakmadan önce bu işlevi çağırır. Kaydedilmiş durumu daha sonra üzerinden geri yüklenebilir [OnApplyViewState](#onapplyviewstate).  
  
 Kullanabileceğiniz `OnSaveViewState` görünümünüzün durumuna özgü kalıcı bilgileri depolamak için. Kılarsanız `OnSaveViewState` bilgileri depolamak için geçersiz kılmak istediğiniz `OnApplyViewState` bu bilgileri okuyun ve yeni etkinleştirildiğinde görünümünüzü uygulamak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDocObjectServerItem Sınıfı](../../mfc/reference/cdocobjectserveritem-class.md)
