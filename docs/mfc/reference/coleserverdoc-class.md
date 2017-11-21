---
title: "COleServerDoc sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
dev_langs: C++
helpviewer_keywords:
- COleServerDoc [MFC], COleServerDoc
- COleServerDoc [MFC], ActivateDocObject
- COleServerDoc [MFC], ActivateInPlace
- COleServerDoc [MFC], DeactivateAndUndo
- COleServerDoc [MFC], DiscardUndoState
- COleServerDoc [MFC], GetClientSite
- COleServerDoc [MFC], GetEmbeddedItem
- COleServerDoc [MFC], GetItemClipRect
- COleServerDoc [MFC], GetItemPosition
- COleServerDoc [MFC], GetZoomFactor
- COleServerDoc [MFC], IsDocObject
- COleServerDoc [MFC], IsEmbedded
- COleServerDoc [MFC], IsInPlaceActive
- COleServerDoc [MFC], NotifyChanged
- COleServerDoc [MFC], NotifyClosed
- COleServerDoc [MFC], NotifyRename
- COleServerDoc [MFC], NotifySaved
- COleServerDoc [MFC], OnDeactivate
- COleServerDoc [MFC], OnDeactivateUI
- COleServerDoc [MFC], OnDocWindowActivate
- COleServerDoc [MFC], OnResizeBorder
- COleServerDoc [MFC], OnShowControlBars
- COleServerDoc [MFC], OnUpdateDocument
- COleServerDoc [MFC], RequestPositionChange
- COleServerDoc [MFC], SaveEmbedding
- COleServerDoc [MFC], ScrollContainerBy
- COleServerDoc [MFC], UpdateAllItems
- COleServerDoc [MFC], CreateInPlaceFrame
- COleServerDoc [MFC], DestroyInPlaceFrame
- COleServerDoc [MFC], GetDocObjectServer
- COleServerDoc [MFC], OnClose
- COleServerDoc [MFC], OnExecOleCmd
- COleServerDoc [MFC], OnFrameWindowActivate
- COleServerDoc [MFC], OnGetEmbeddedItem
- COleServerDoc [MFC], OnReactivateAndUndo
- COleServerDoc [MFC], OnSetHostNames
- COleServerDoc [MFC], OnSetItemRects
- COleServerDoc [MFC], OnShowDocument
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7363aca122d002a3ae77f071287942783ac7fbf2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="coleserverdoc-class"></a>COleServerDoc sınıfı
OLE sunucu belgeleri için temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleServerDoc::COleServerDoc](#coleserverdoc)|Oluşturan bir `COleServerDoc` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleServerDoc::ActivateDocObject](#activatedocobject)|İlişkili DocObject belge etkinleştirir.|  
|[COleServerDoc::ActivateInPlace](#activateinplace)|Belgesini yerinde düzenleme için etkinleştirir.|  
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|Sunucunun kullanıcı arabirimini devre dışı bırakır.|  
|[COleServerDoc::DiscardUndoState](#discardundostate)|Geri alma işlemi durum bilgilerini atar.|  
|[COleServerDoc::GetClientSite](#getclientsite)|Arka plandaki bir işaretçi alır `IOleClientSite` arabirimi.|  
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|Bir işaretçi tüm belgeyi temsil eden bir öğeyi döndürür.|  
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|Yerinde düzenlemek için geçerli kırpma dikdörtgen döndürür.|  
|[COleServerDoc::GetItemPosition](#getitemposition)|Geçerli konumu dikdörtgen, yerinde düzenlemek için kapsayıcı uygulamanın istemci alanını göre döndürür.|  
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|Yakınlaştırma faktörünü piksel cinsinden döndürür.|  
|[COleServerDoc::IsDocObject](#isdocobject)|Belge DocObject olup olmadığını belirler.|  
|[COleServerDoc::IsEmbedded](#isembedded)|Belge kapsayıcı belgedeki katıştırılmış veya çalışan tek başına olup olmadığını gösterir.|  
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|Döndürür `TRUE` öğe şu anda yerinde etkinleştirilmişse.|  
|[COleServerDoc::NotifyChanged](#notifychanged)|Kullanıcı belge değişti kapsayıcıları bildirir.|  
|[COleServerDoc::NotifyClosed](#notifyclosed)|Kullanıcının belgeyi kapattığı kapsayıcıları bildirir.|  
|[COleServerDoc::NotifyRename](#notifyrename)|Kullanıcının belgeyi yeniden adlandırılamaz kapsayıcıları bildirir.|  
|[COleServerDoc::NotifySaved](#notifysaved)|Kullanıcının belgeyi kaydetti kapsayıcıları bildirir.|  
|[COleServerDoc::OnDeactivate](#ondeactivate)|Yerinde etkinleştirildiği bir öğe kullanıcı devre dışı bırakır çerçevesi tarafından çağrılır.|  
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|Denetimleri ve yerinde etkinleştirme için oluşturulan diğer kullanıcı arabirimi öğeleri yok etmek için çerçevesi tarafından çağrılır.|  
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|Kapsayıcının belge çerçeve penceresi etkin veya devre dışı bırakıldığında çerçevesi tarafından çağrılır.|  
|[COleServerDoc::OnResizeBorder](#onresizeborder)|Kapsayıcı uygulamanın çerçeve penceresi veya belge penceresine boyutlandırıldığında çerçevesi tarafından çağrılır.|  
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|Yerinde düzenlemek için Denetim çubuklarını gösterme veya gizleme için çerçevesi tarafından çağrılır.|  
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|Katıştırılmış bir öğe bir sunucu Belge kaydedildiğinde öğenin kapsayıcının kopyasını güncelleştirme çerçevesi tarafından çağrılır.|  
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|Yerinde düzenleme çerçeve konumunu değiştirir.|  
|[COleServerDoc::SaveEmbedding](#saveembedding)|Belgeyi kaydetmek için kapsayıcı uygulama söyler.|  
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|Kapsayıcı belge kayar.|  
|[COleServerDoc::UpdateAllItems](#updateallitems)|Kullanıcı belge değişti kapsayıcıları bildirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|Yerinde düzenlemek için bir çerçeve penceresinde oluşturmak için çerçevesi tarafından çağrılır.|  
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|Yerinde düzenlemek için bir çerçeve pencere yok etme çerçevesi tarafından çağrılır.|  
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|Yeni bir oluşturmak için bu işlevi geçersiz `CDocObjectServer` nesne ve bu belgenin DocObject kapsayıcı olduğunu gösteriyor.|  
|[COleServerDoc::OnClose](#onclose)|Belge kapatmak için bir kapsayıcı istediğinde, çerçevesi tarafından çağrılır.|  
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|Belirtilen komut yürütür veya komutu için yardımı görüntüler.|  
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|Kapsayıcının çerçeve penceresi etkin veya devre dışı olduğunda çerçevesi tarafından çağrılır.|  
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|Alınacak adlı bir `COleServerItem` , tüm belgeyi temsil eder; katıştırılmış öğeyi almak için kullanılır. Gerekli uygulama.|  
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|Yerinde düzenleme sırasında yapılan değişiklikleri geri alma çerçevesi tarafından çağrılır.|  
|[COleServerDoc::OnSetHostNames](#onsethostnames)|Pencere Başlığı katıştırılmış nesne için bir kapsayıcı ayarlar çerçevesi tarafından çağrılır.|  
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|Kapsayıcı uygulamanın pencereye yerinde düzenleme çerçeve pencere konumunu çerçevesi tarafından çağrılır.|  
|[COleServerDoc::OnShowDocument](#onshowdocument)|Görüntülemek veya belgenin gizlemek için çerçevesi tarafından çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir sunucu belge içerebilir [COleServerItem](../../mfc/reference/coleserveritem-class.md) sunucu arabirimi katıştırılmış veya bağlı öğeleri temsil eden nesne. Bir sunucu uygulaması katıştırılmış bir öğeyi düzenlemek için bir kapsayıcı başlatıldığında, öğesi, kendi sunucu belgesi olarak yüklenir; `COleServerDoc` nesnesini içeren tek `COleServerItem` tüm belgenin oluşan nesne. Bağlantılı bir öğe düzenlemek için bir kapsayıcı tarafından bir sunucu uygulaması başlatıldığında, var olan bir belgeyi diskten yüklenir; bir belge içeriğini kısmı bağlantılı öğesi belirtmek için vurgulanır.  
  
 `COleServerDoc`nesneleri ayrıca öğeleri içeren [COleClientItem](../../mfc/reference/coleclientitem-class.md) sınıfı. Bu kapsayıcı sunuculu uygulamalar oluşturmanıza olanak sağlar. Çerçeve düzgün bir şekilde depolamak için işlevleri sağlar `COleClientItem` bakım sırasında öğeleri `COleServerItem` nesneleri.  
  
 Sunucu uygulamanızı bağlantılar desteklemiyorsa, server belge her zaman bir belge olarak tüm katıştırılmış nesneyi temsil eden yalnızca bir sunucu öğesini içerir. Sunucu uygulamanızı bağlantılar destekliyorsa, seçim panoya kopyalandı her zaman bir sunucu öğesi oluşturmanız gerekir.  
  
 Kullanılacak `COleServerDoc`, buradan bir sınıf türetin ve uygulama [OnGetEmbeddedItem](#ongetembeddeditem) sunucunuzun katıştırılmış öğeleri desteklemesi için sağlayan üye işlevi. Öğesinden bir sınıf türetin `COleServerItem` öğeleri belgelerinizde uygulamak ve bu sınıftan nesneleri döndürmek için `OnGetEmbeddedItem`.  
  
 Bağlantılı öğeler desteklemek için `COleServerDoc` sağlar [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) üye işlevi. Varsayılan uygulama veya belge öğeleri yönetme kendi yolu varsa geçersiz kılma kullanabilirsiniz.  
  
 Bir gereksinim `COleServerDoc`-her sunucu türü belge için uygulamanızın desteklediği türetilmiş sınıf. Çalışma sayfaları ve grafikler sunucu uygulamanız destekliyorsa, örneğin, iki gereksinim duyduğunuz `COleServerDoc`-türetilmiş sınıfları.  
  
 Makaleyi sunucuları hakkında daha fazla bilgi için bkz: [sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="activatedocobject"></a>COleServerDoc::ActivateDocObject  
 İlişkili DocObject belge etkinleştirir.  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `COleServerDoc` (DocObjects da bilinir) etkin belgeler desteklemiyor. Bu desteğini etkinleştirmek için bkz: [GetDocObjectServer](#getdocobjectserver) ve sınıf [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md).  
  
##  <a name="activateinplace"></a>COleServerDoc::ActivateInPlace  
 Öğeyi yerinde düzenleme için etkinleştirir.  
  
```  
BOOL ActivateInPlace();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi halde 0, öğesi tam olarak açık olduğunu gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yerinde etkinleştirme için gerekli tüm işlemleri gerçekleştirir. Yerinde çerçeve penceresi oluşturur, etkinleştirir ve öğesine boyutları, paylaşılan menüleri ve diğer denetimlerin ayarlar, görünüme öğesi gelene ve yerinde çerçeve penceresi odağı ayarlar.  
  
 Bu işlev varsayılan uygulaması tarafından çağrılır [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow). Uygulamanız (örneğin, yürütme) yerinde etkinleştirme için başka bir fiil destekliyorsa bu işlevini çağırın.  
  
##  <a name="coleserverdoc"></a>COleServerDoc::COleServerDoc  
 Oluşturan bir `COleServerDoc` OLE sistem DLL'leri bağlanmadan nesnesi.  
  
```  
COleServerDoc();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız [COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) iletişimleri OLE ile açın. Kullanıyorsanız [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) , uygulamanızda `COleLinkingDoc::Register` tarafından sizin için adlı `COleLinkingDoc`'s uyarlamasını `OnNewDocument`, `OnOpenDocument`, ve `OnSaveDocument`.  
  
##  <a name="createinplaceframe"></a>COleServerDoc::CreateInPlaceFrame  
 Framework yerinde düzenlemek için bir çerçeve penceresinde oluşturmak için bu işlevi çağırır.  
  
```  
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentWnd`  
 Kapsayıcı uygulamanın ana pencereyi işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerinde çerçeve penceresi için bir işaretçi veya **NULL** başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama çerçevesi oluşturmak için belge şablonda belirtilen bilgileri kullanır. Kullanılan görünümü ve belge için oluşturulan ilk görünümdür. Bu görünüm geçici olarak özgün çerçevesinden ayrılmış ve yeni oluşturulan çerçeve bağlı.  
  
 Gelişmiş budur geçersiz kılınabilir.  
  
##  <a name="deactivateandundo"></a>COleServerDoc::DeactivateAndUndo  
 Bu işlev, uygulamanızın desteklediği geri ve geri alma öğeyi etkinleştirdikten sonra ancak düzenlemeden önce kullanıcının seçtiği çağırın.  
  
```  
BOOL DeactivateAndUndo();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcı uygulama Microsoft Foundation Class Kitaplığı kullanılarak yazılmışsa, bu işlev çağırma neden [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) çağrılacak, sunucunun kullanıcı arabirimini bırakır.  
  
##  <a name="destroyinplaceframe"></a>COleServerDoc::DestroyInPlaceFrame  
 Çerçeve bir yerinde çerçeve penceresi yok ve sunucu durumuna yerinde etkinleştirme önce uygulamanın belge penceresine dönmek için bu işlevi çağırır.  
  
```  
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFrameWnd`  
 Yerinde çerçeve penceresi yok edilmesi için işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Gelişmiş budur geçersiz kılınabilir.  
  
##  <a name="discardundostate"></a>COleServerDoc::DiscardUndoState  
 Kullanıcı geri alınamaz bir düzenleme işlemi gerçekleştirirse, geri alma işlemi durum bilgilerini atmak için kapsayıcı uygulama zorlamak için bu işlevini çağırın.  
  
```  
BOOL DiscardUndoState();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, böylece Geri Al'ı destekleyen sunucular kullanılamaz geri alma işlemi durum bilgilerini tarafından tüketilen kaynakları boşaltabilirsiniz sağlanır.  
  
##  <a name="getclientsite"></a>COleServerDoc::GetClientSite  
 Arka plandaki bir işaretçi alır `IOleClientSite` arabirimi.  
  
```  
LPOLECLIENTSITE GetClientSite() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arka plandaki bir işaretçi alır [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706) arabirimi.  
  
##  <a name="getdocobjectserver"></a>COleServerDoc::GetDocObjectServer  
 Yeni bir oluşturmak için bu işlevi geçersiz `CDocObjectServer` öğesi ve bir işaretçi döndürün.  
  
```  
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDocSite`  
 İşaretçi `IOleDocumentSite` bu belgeyi sunucuya bağlanır arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CDocObjectServer`; **NULL** işlemi başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir DocObject sunucusu etkinleştirildiğinde, olmayan bir dönüşünü **NULL** işaretçi gösterir istemci DocObjects destekleyebilir. Varsayılan uygulama döndürür **NULL**.  
  
 DocObjects destekleyen bir belge için tipik bir uygulama yalnızca yeni bir ayırır `CDocObjectServer` nesne ve çağırana döndürür. Örneğin:  
  
 [!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]  
  
##  <a name="getembeddeditem"></a>COleServerDoc::GetEmbeddedItem  
 Tüm belgeyi temsil eden bir öğe için bir işaretçi almak için bu işlevini çağırın.  
  
```  
COleServerItem* GetEmbeddedItem();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tüm belgeyi temsil eden bir öğe için bir işaretçi; **NULL** işlemi başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırır [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), bir sanal işleve hiçbir varsayılan uygulaması.  
  
##  <a name="getitemcliprect"></a>COleServerDoc::GetItemClipRect  
 Çağrı `GetItemClipRect` yerinde düzenlenmekte olan öğe kırpması dikdörtgen koordinatlarını alma üye işlevi.  
  
```  
void GetItemClipRect(LPRECT lpClipRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpClipRect`  
 İşaretçi bir `RECT` yapısı veya `CRect` öğe kırpması dikdörtgen koordinatlarını almak için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Piksel cinsinden kapsayıcı uygulama penceresinin istemci alanına göre koordinatlar belirlenir.  
  
 Çizim dışında dikdörtgen kırpma oluşmamalıdır. Genellikle, çizim otomatik olarak sınırlandırılır. Kullanıcının belgeyi görünen dilimini dışında kaydırılan olup olmadığını belirlemek için bu işlevi kullanın; Öyleyse, kapsayıcı belge için bir çağrı yoluyla gerektiği şekilde kaydırın [ScrollContainerBy](#scrollcontainerby).  
  
##  <a name="getitemposition"></a>COleServerDoc::GetItemPosition  
 Çağrı `GetItemPosition` yerinde düzenlenmekte öğesi koordinatlarını alma üye işlevi.  
  
```  
void GetItemPosition(LPRECT lpPosRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpPosRect`  
 İşaretçi bir `RECT` yapısı veya `CRect` öğesi koordinatlarını almak için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Piksel cinsinden kapsayıcı uygulama penceresinin istemci alanına göre koordinatlar belirlenir.  
  
 Öğe olduğu görünür (veya görünür) hasarın belirlemek için geçerli kırpma dikdörtgen öğesi'nin konumu karşılaştırılabilir ekranında.  
  
##  <a name="getzoomfactor"></a>COleServerDoc::GetZoomFactor  
 `GetZoomFactor` Üye fonksiyonu "yakınlaştırma faktörünü" yerinde düzenleme için etkinleştirilmiş bir öğenin belirler.  
  
```  
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,  
    LPSIZE lpSizeDenom = NULL,  
    LPCRECT lpPosRect = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lpSizeNum*  
 Sınıfın bir nesnesi için işaretçi `CSize` yakınlaştırma faktörünü 's pay tutun. Olabilir **NULL**.  
  
 *lpSizeDenom*  
 Sınıfın bir nesnesi için işaretçi `CSize` yakınlaştırma faktörünü 's payda tutun. Olabilir **NULL**.  
  
 `lpPosRect`  
 Sınıfın bir nesnesi için işaretçi `CRect` öğesi'nin yeni konumu açıklar. Bu bağımsız değişken ise **NULL**, işlevi öğesi'nin geçerli konumunu kullanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Madde yerinde için etkinleştirildiğinde sıfır olmayan düzenleme ve yakınlaştırma faktörünü olduğunu (1:1); % 100 dışında Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Yakınlaştırma faktörünü piksel cinsinden geçerli uzantı öğesi'nin boyutuna oranı ' dir. Kapsayıcı uygulama öğesi'nin ölçüde, kendi doğal ölçüde ayarlı değil ise (tarafından belirlenen [COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) kullanılır.  
  
 İşlev, ilk iki bağımsız değişkenlerinin pay ve payda öğesi'nin "yakınlaştırma faktörü." ayarlar Öğe yerinde düzenlenmekte olan değil, işlevi bu bağımsız değişkenler % 100'den (ya da 1:1) varsayılan değerine ayarlar ve sıfır döndürür. Teknik Not 40, daha fazla bilgi için bkz: [MFC/OLE yerinde yeniden boyutlandırma ve yakınlaştırma](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
##  <a name="isdocobject"></a>COleServerDoc::IsDocObject  
 Belge DocObject olup olmadığını belirler.  
  
```  
BOOL IsDocObject() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** belge DocObject; ise aksi **FALSE**.  
  
##  <a name="isembedded"></a>COleServerDoc::IsEmbedded  
 Çağrı `IsEmbedded` belgenin bir kapsayıcıda katıştırılmış bir nesneyi temsil edip etmediğini belirlemek için üye işlevi.  
  
```  
BOOL IsEmbedded() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `COleServerDoc` nesnesi olan bir nesneyi temsil eden bir belge katıştırılmış bir kapsayıcıda; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bağlantı olarak bir kapsayıcı uygulama tarafından yönetilen ancak bir dosyasından yüklenen bir belge katıştırılmış değil. Katıştırılmış bir kapsayıcı belge içine katıştırılmış bir belge olarak kabul edilir.  
  
##  <a name="isinplaceactive"></a>COleServerDoc::IsInPlaceActive  
 Çağrı `IsInPlaceActive` öğe şu anda yerinde etkin durumda olup olmadığını belirlemek için üye işlevi.  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `COleServerDoc` nesnesidir yerinde active; Aksi halde 0.  
  
##  <a name="notifychanged"></a>COleServerDoc::NotifyChanged  
 Belge değişti belgeye bağlı tüm bağlantılı öğeler bildirmek için bu işlevini çağırın.  
  
```  
void NotifyChanged();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, sunucu belgesinin boyutları gibi bazı genel öznitelik kullanıcı değiştirdikten sonra bu işlevini çağırın. OLE öğesi belgeye otomatik bir bağlantıyla bağlı ise, öğenin değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Kitaplığı ile yazılmış kapsayıcı uygulamalarında [değiştiğinde](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevini `COleClientItem` olarak adlandırılır.  
  
> [!NOTE]
>  Bu işlev OLE 1 ile uyumluluk için dahil edilmiştir. Yeni uygulamalar kullanması gereken [UpdateAllItems](#updateallitems).  
  
##  <a name="notifyclosed"></a>COleServerDoc::NotifyClosed  
 Belge kapalı kaldırıldığından bildirmek için bu işlevini çağırın.  
  
```  
void NotifyClosed();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı Dosya menüsünden Kapat komutunu seçtiğinde `NotifyClosed` tarafından çağrılır `COleServerDoc`'s uyarlamasını [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) üye işlevi. Microsoft Foundation Class Kitaplığı ile yazılmış kapsayıcı uygulamalarında [değiştiğinde](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevini `COleClientItem` olarak adlandırılır.  
  
##  <a name="notifyrename"></a>COleServerDoc::NotifyRename  
 Sunucu belgesinin kullanıcının yeniden adlandırır sonra bu işlevini çağırın.  
  
```  
void NotifyRename(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszNewName`  
 Sunucu belgesinin yeni adını belirten bir dize işaretçi; Bu, genellikle tam nitelenmiş bir yol olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı Dosya menüsünden Kaydet komutunu seçtiğinde `NotifyRename` tarafından çağrılır `COleServerDoc`'s uyarlamasını [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) üye işlevi. Bu işlev OLE sistemi sırayla kapsayıcıları bildir DLL'leri bildirir. Microsoft Foundation Class Kitaplığı ile yazılmış kapsayıcı uygulamalarında [değiştiğinde](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevini `COleClientItem` olarak adlandırılır.  
  
##  <a name="notifysaved"></a>COleServerDoc::NotifySaved  
 Sunucu belgesinin kullanıcı kaydettikten sonra bu işlevini çağırın.  
  
```  
void NotifySaved();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı Dosya menüsünden Kaydet komutunu seçtiğinde `NotifySaved` tarafından sizin için adlı `COleServerDoc`'s uyarlamasını [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument). Bu işlev OLE sistemi sırayla kapsayıcıları bildir DLL'leri bildirir. Microsoft Foundation Class Kitaplığı ile yazılmış kapsayıcı uygulamalarında [değiştiğinde](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevini `COleClientItem` olarak adlandırılır.  
  
##  <a name="onclose"></a>COleServerDoc::OnClose  
 Bir kapsayıcı sunucu belgesinin kapatılması istediğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnClose(OLECLOSE dwCloseOption);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwCloseOption`  
 Numaralandırma arasında bir değer `OLECLOSE`. Bu parametre aşağıdaki değerlerden biri olabilir:  
  
- `OLECLOSE_SAVEIFDIRTY`Bunu güncellendiyse dosya kaydedilmiş kalır.  
  
- `OLECLOSE_NOSAVE`Dosya kaydedildi olmadan kapalı.  
  
- `OLECLOSE_PROMPTSAVE`Dosya değiştirilirse kaydetme hakkında kullanıcıya sorulur.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Uygulama çağrıları `CDocument::OnCloseDocument`.  
  
 Daha fazla bilgi ve ek değerler için bkz: [OLECLOSE](http://msdn.microsoft.com/library/windows/desktop/ms680623) Windows SDK'sındaki.  
  
##  <a name="ondeactivate"></a>COleServerDoc::OnDeactivate  
 Kullanıcı şu anda yerinde etkin olduğu bir katıştırılmış veya bağlantılı bir öğe devre dışı bırakır çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, kapsayıcı uygulamanın kullanıcı arabirimi özgün durumuna geri yükler ve tüm menüleri ve yerinde etkinleştirme için oluşturulmuş olan diğer denetimleri yok eder.  
  
 Geri alma işlemi durum bilgilerini koşulsuz olarak bu noktada yayımlanması.  
  
 Daha fazla bilgi için bkz: [etkinleştirme](../../mfc/activation-cpp.md)...  
  
##  <a name="ondeactivateui"></a>COleServerDoc::OnDeactivateUI  
 Yerinde etkinleştirildiği bir öğe kullanıcı devre dışı bırakır çağrılır.  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>Parametreler  
 `bUndoable`  
 Düzenleme değişiklikleri alınabilecek olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev kapsayıcı uygulamanın kullanıcı arabirimi menüler ve yerinde etkinleştirme için oluşturulmuş olan diğer denetimleri gizleme özgün durumuna geri yükler.  
  
 Her zaman framework ayarlar `bUndoable` için **FALSE**. Sunucunun geri alma destekliyorsa ve alınabilecek bir işlem, bir taban sınıfı uygulama ile çağrı `bUndoable` kümesine **doğru**.  
  
##  <a name="ondocwindowactivate"></a>COleServerDoc::OnDocWindowActivate  
 Framework etkinleştirme veya devre dışı yerinde düzenlemek için bir belge penceresi için bu işlevi çağırır.  
  
```  
virtual void OnDocWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 `bActivate`  
 Belge penceresine etkinleştirilmiş veya devre dışı olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama çerçeve düzeyi kullanıcı arabirimi öğeleri uygun şekilde ekler veya kaldırır. Öğenizi içeren belge etkinleştirilmiş veya devre dışı olduğunda ek eylemleri gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.  
  
 Daha fazla bilgi için bkz: [etkinleştirme](../../mfc/activation-cpp.md)...  
  
##  <a name="onexecolecmd"></a>COleServerDoc::OnExecOleCmd  
 Framework belirtilen komut yürütme ya da komut için Yardım görüntülemek için bu işlevi çağırır.  
  
```  
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,  
    DWORD nCmdID,  
    DWORD nCmdExecOpt,  
    VARIANTARG* pvarargIn,  
    VARIANTARG* pvarargOut);
```  
  
### <a name="parameters"></a>Parametreler  
 `pguidCmdGroup`  
 Bir işaretçi komutları kümesini tanımlayan bir GUID. Olabilir **NULL** varsayılan komut grubu belirtmek için.  
  
 `nCmdID`  
 Yürütülecek komut. Tarafından tanımlanan grubunda olmalıdır `pguidCmdGroup`.  
  
 *nCmdExecOut*  
 Yol nesne komutu, bir veya daha fazla aşağıdaki değerlerden birini yürütülecek **OLECMDEXECOPT** numaralandırma:  
  
 **OLECMDEXECOPT_DODEFAULT**  
  
 **OLECMDEXECOPT_PROMPTUSER**  
  
 **OLECMDEXECOPT_DONTPROMPTUSER**  
  
 **OLECMDEXECOPT_SHOWHELP**  
  
 `pvarargIn`  
 İşaretçi bir **VARIANTARG** komut için giriş bağımsız değişkeni içeren. Olabilir **NULL**.  
  
 `pvarargOut`  
 İşaretçi bir **VARIANTARG** komuttan çıkış dönüş değerleri almak için. Olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK` başarılı; Aksi takdirde aşağıdaki hata kodları:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Beklenmeyen bir hata oluştu|  
|**E_FAIL**|Bir hata oluştu|  
|**E_NOTIMPL**|MFC gösterir kendisini çevirin ve komut gönderme girişiminde|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup`olmayan olan **NULL** tanınan komut grubu belirtmiyor ancak|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID`grubun geçerli bir komut olarak tanınmıyor`pguidCmdGroup`|  
|**OLECMDERR_DISABLED**|Tarafından tanımlanan komutu `nCmdID` devre dışı bırakılır ve yürütülemez|  
|**OLECMDERR_NOHELP**|Çağıran tarafından tanımlanan komutu hakkında Yardım için sorulan `nCmdID` ancak Yardım yok|  
|**OLECMDERR_CANCELED**|Kullanıcı yürütme iptal edildi|  
  
### <a name="remarks"></a>Açıklamalar  
 `COleCmdUI`etkinleştirme, güncelleştirme ve diğer DocObject kullanıcı arabirimi komutları özelliklerini ayarlamak için kullanılabilir. Komutları başlatıldıktan sonra yürütebilir `OnExecOleCmd`.  
  
 Framework çevirin ve OLE belge komut gönderme girişiminde bulunmadan önce işlevi çağırır. Standart OLE belge komutları işlemek için bu işlev geçersiz kılmak gerekli değildir, ancak kendi özel komutları işleyebilir veya parametreleri kabul veya sonuçları döndüren komutları işlemek istiyorsanız, bu işlev bir geçersiz kılma sağlamanız gerekir.  
  
 Komutların çoğu olmayan bağımsız değişkenler almayan veya dönüş değerleri. Komutların çoğu için arayan geçirebilirsiniz **NULL**s için `pvarargIn` ve `pvarargOut`. Giriş değerleri beklediğini komutları çağıran bildirme başlatmak ve bir **VARIANTARG** değişkeni değişken bir işaretçi geçirin `pvarargIn`. Tek bir değer gerektiren komutlar için bağımsız değişken doğrudan depolanabilir **VARIANTARG** ve işleve. İçinde birden fazla bağımsız değişkenini paketlenmesi **VARIANTARG** desteklenen türlerden birini kullanarak (gibi `IDispatch` ve **SAFEARRAY** ).  
  
 Bir komut bağımsız değişkenleri çağıran döndürürse benzer şekilde, bildirmek için beklenen bir **VARIANTARG**, kendisine başlatma `VT_EMPTY`ve kendi adres geçirin `pvarargOut`. Bir komut tek bir değer döndürürse, nesne doğrudan bu değeri saklayabilir `pvarargOut`. Birden çok çıktı değerleri için uygun şekilde paketlenmesi **VARIANTARG**.  
  
 Bu işlevin temel sınıf uygulamasını yükselteceğinizi **OLE_COMMAND_MAP** uygun bir işleyici komutuna gönderileceği deneyin ve komut hedefi ile ilişkili yapıları. Temel sınıf uygulamasını bağımsız değişkenlerini kabul eder veya dönüş değerleri komutları ile çalışır. Bağımsız değişkenler kabul eden ya da dönüş değerleri komutları işlemek gerekiyorsa, bu işlevi geçersiz gerekir ve çalışmak `pvarargIn` ve `pvarargOut` parametreleri kendiniz.  
  
##  <a name="onframewindowactivate"></a>COleServerDoc::OnFrameWindowActivate  
 Kapsayıcı uygulamanın çerçeve penceresi etkinleştirilmiş veya devre dışı bırakıldığında framework bu işlevi çağırır.  
  
```  
virtual void OnFrameWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 `bActivate`  
 Çerçeve penceresi etkin veya devre dışı olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama çerçeve penceresi olabilir. tüm Yardım modları iptal eder. Çerçeve penceresi etkin veya devre dışı bırakıldığında özel işlem gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.  
  
 Daha fazla bilgi için bkz: [etkinleştirme](../../mfc/activation-cpp.md)...  
  
##  <a name="ongetembeddeditem"></a>COleServerDoc::OnGetEmbeddedItem  
 Bir kapsayıcı uygulama oluşturmak veya katıştırılmış bir öğeyi düzenlemek için sunucu uygulaması çağırdığında çerçevesi tarafından çağrılır.  
  
```  
virtual COleServerItem* OnGetEmbeddedItem() = 0;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tüm belgeyi temsil eden bir öğe için bir işaretçi; **NULL** işlemi başarısız olursa.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama yok. Tüm belgeyi temsil eden bir öğesi döndürmek için bu işleve geçersiz kılmanız gerekir. Bu dönüş değeri bir nesne olmalıdır bir `COleServerItem`-türetilmiş sınıf.  
  
##  <a name="onreactivateandundo"></a>COleServerDoc::OnReactivateAndUndo  
 Kullanıcı yerinde etkinleştirildi, değişti, ve ardından devre dışı bir öğesine yapılan değişiklikleri geri almak seçtiğinde framework bu işlevi çağırır.  
  
```  
virtual BOOL OnReactivateAndUndo();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama dönüş dışında hiçbir şey yapmaz **FALSE** hatayı belirtmek için.  
  
 Geri alma uygulamanız destekliyorsa, bu işlev geçersiz kılar. Genellikle, geri alma işlemi gerçekleştirebilir ve ardından öğeyi çağırarak etkinleştirme `ActivateInPlace`. Kapsayıcı uygulama, Microsoft Foundation Class Kitaplığı ile yazılmış çağrılmadan `COleClientItem::ReactivateAndUndo` bu işlevinin çağrılmasına neden olur.  
  
##  <a name="onresizeborder"></a>COleServerDoc::OnResizeBorder  
 Kapsayıcı uygulamanın çerçeve pencereleri boyutunu değiştirdiğinizde framework bu işlevi çağırır.  
  
```  
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,  
    LPOLEINPLACEUIWINDOW lpUIWindow,  
    BOOL bFrame);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRectBorder`  
 İşaretçi bir `RECT` yapısı veya `CRect` kenarlık koordinatlarını belirtir nesnesi.  
  
 `lpUIWindow`  
 Sınıfın bir nesnesi için işaretçi **IOleInPlaceUIWindow** geçerli yerinde düzenleme oturum sahibi.  
  
 *bFrame*  
 **DOĞRU** varsa `lpUIWindow` işaret kapsayıcı uygulamanın üst düzey çerçeve penceresine veya **FALSE** varsa `lpUIWindow` işaret kapsayıcı uygulamanın belge düzeyi çerçeve penceresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yeniden boyutlandırır ve araç çubuklarını ve diğer kullanıcı arabirimi öğeleri yeni pencere boyutunu uygun olarak ayarlar.  
  
 Daha fazla bilgi için bkz: [IOleInPlaceUIWindow](http://msdn.microsoft.com/library/windows/desktop/ms680716) Windows SDK'sındaki.  
  
 Gelişmiş budur geçersiz kılınabilir.  
  
##  <a name="onsethostnames"></a>COleServerDoc::OnSetHostNames  
 Kapsayıcı ayarlar ya da bu belge için ana bilgisayar adlarını çerçevesi tarafından çağrılır.  
  
```  
virtual void OnSetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszHost`  
 İşaretçi bir dizeye kapsayıcı uygulamanın adını belirtir.  
  
 `lpszHostObj`  
 İşaretçi belge için kapsayıcının adını belirten dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama bu belgeye başvuran tüm görünümleri için belge başlığı değiştirir.  
  
 Bu işlev, uygulamanız farklı bir mekanizma aracılığıyla başlıklarını ayarlarsa geçersiz kılar.  
  
##  <a name="onsetitemrects"></a>COleServerDoc::OnSetItemRects  
 Framework yerinde düzenleme çerçeve penceresi kapsayıcı uygulamanın çerçeve penceresi içinde konumlandırmak için bu işlevi çağırır.  
  
```  
virtual void OnSetItemRects(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpPosRect`  
 İşaretçi bir `RECT` yapısı veya `CRect` kapsayıcı uygulamanın istemci alanını göre yerinde çerçeve pencere konumunu belirten nesne.  
  
 `lpClipRect`  
 İşaretçi bir `RECT` yapısı veya `CRect` yerinde çerçeve pencere kapsayıcı uygulamanın istemci alanını göre dikdörtgen kırpma belirtir nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Gerekirse görünümün yakınlaştırma faktörünü güncelleştirmek için bu işlevi geçersiz kılar.  
  
 Bu işlev genellikle yanıt olarak adlandırılır bir `RequestPositionChange` herhangi bir zamanda, yerinde öğesi için bir konum değişiklik isteği kapsayıcıya tarafından çağrılabilir rağmen çağırın.  
  
##  <a name="onshowcontrolbars"></a>COleServerDoc::OnShowControlBars  
 Framework tarafından tanımlanan çerçeve penceresi ile ilişkili sunucu uygulamasının denetim çubuklarını gösterme veya gizleme için bu işlevi çağırır `pFrameWnd`.  
  
```  
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFrameWnd`  
 Çerçeve penceresi, Denetim çubukları gizli veya gösterilen gerektiğini işaretçi.  
  
 `bShow`  
 Denetim çubukları gösterileceğini veya gizleneceğini olup olmadığını belirler.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama, çerçeve penceresi tarafından sahip olunan tüm denetim çubukları numaralandırır ve gizler veya bunları gösterir.  
  
##  <a name="onshowdocument"></a>COleServerDoc::OnShowDocument  
 Framework çağrıları `OnShowDocument` işlev sunucu belgesinin gizli veya gösterilen gerekir.  
  
```  
virtual void OnShowDocument(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 `bShow`  
 Belge için kullanıcı arabirimi gösterileceğini veya gizleneceğini olup olmadığını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bShow` olan **doğru**, varsayılan uygulama gerekirse sunucu uygulaması etkinleştirir ve onun penceresi öğesi görünür olmasını sağlamak kaydırmak kapsayıcı uygulamanın neden olur. Varsa `bShow` olan **FALSE**, varsayılan uygulaması bir çağrıyla öğesi devre dışı bırakır `OnDeactivate`, ardından yok eder veya ilki dışında belge için oluşturulan tüm çerçeve pencereleri gizler. Varsayılan uygulama görünür belge kalırsa, sunucu uygulaması gizler.  
  
##  <a name="onupdatedocument"></a>COleServerDoc::OnUpdateDocument  
 Bir belgeyi kaydetmeyi bileşik belge katıştırılmış bir öğeyi olduğunda çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnUpdateDocument();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belge başarıyla güncelleştirildiyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan Uygulama çağrıları [COleServerDoc::NotifySaved](#notifysaved) ve [COleServerDoc::SaveEmbedding](#saveembedding) üye işlevleri ve belgeyi temiz olarak işaretler. Özel bir katıştırılmış öğesi güncellenirken işleme gerçekleştirmek istiyorsanız, bu işlev geçersiz kılar.  
  
##  <a name="requestpositionchange"></a>COleServerDoc::RequestPositionChange  
 Öğenin konumunu değiştirme kapsayıcı uygulama sağlamak için bu üye işlevini çağırın.  
  
```  
void RequestPositionChange(LPCRECT lpPosRect);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpPosRect`  
 İşaretçi bir `RECT` yapısı veya `CRect` öğesi'nin yeni konumunu içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev genellikle çağrılır (birlikte `UpdateAllItems`) yerinde etkin öğeyi verilerinde zaman değişti. Bu çağrı aşağıdaki kapsayıcı olabilir ya da değişiklik çağırarak yerine getirmeyebilir `OnSetItemRects`. Sonuçta elde edilen konumu, istenen farklı olabilir.  
  
##  <a name="saveembedding"></a>COleServerDoc::SaveEmbedding  
 Katıştırılmış nesne kaydetmek için kapsayıcı uygulamaya bildirmek için bu işlevini çağırın.  
  
```  
void SaveEmbedding();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev otomatik olarak çağrılır `OnUpdateDocument`. Bu işlev yalnızca belirli bir kullanıcı eylemi sonucunda genellikle olarak adlandırılan şekilde diskte güncelleştirilecek öğesi neden olduğunu unutmayın.  
  
##  <a name="scrollcontainerby"></a>COleServerDoc::ScrollContainerBy  
 Çağrı `ScrollContainerBy` piksel cinsinden miktar kapsayıcı belge kaydırmak için üye işlevi belirtilen tarafından `sizeScroll`.  
  
```  
BOOL ScrollContainerBy(CSize sizeScroll);
```  
  
### <a name="parameters"></a>Parametreler  
 `sizeScroll`  
 İlerlemek için ne kadar kapsayıcı belge olduğunu gösterir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Pozitif değerler aşağı ve sağa kaydırma gösterir; negatif değerler yukarı ve sola kaydırma gösterir.  
  
##  <a name="updateallitems"></a>COleServerDoc::UpdateAllItems  
 Belge değişti belgeye bağlı tüm bağlantılı öğeler bildirmek için bu işlevini çağırın.  
  
```  
void UpdateAllItems(
    COleServerItem* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSender`  
 İşaretçi belge değiştirilen öğeye veya **NULL** tüm öğeleri güncelleştirilmesi gerekiyorsa.  
  
 `lHint`  
 Değiştirme hakkında bilgi içerir.  
  
 `pHint`  
 Nesneyi değiştirme hakkında bilgi depolamak için işaretçi.  
  
 `nDrawAspect`  
 Nasıl çizilecek öğedir belirler. Bu bir değerdir `DVASPECT` numaralandırması. Bu parametre aşağıdaki değerlerden biri olabilir:  
  
- `DVASPECT_CONTENT`Öğesi, katıştırılmış nesne kapsayıcısı içinde olarak görüntülenebilir şekilde gösterilir.  
  
- `DVASPECT_THUMBNAIL`Tarama Aracı içinde görüntülenebilir böylece öğesi bir "küçük" gösterimi işlenir.  
  
- `DVASPECT_ICON`Öğe bir simge ile temsil edilir.  
  
- `DVASPECT_DOCPRINT`Dosya menüsünden Yazdır komutunu kullanarak yazdırılan gibi öğeyi temsil edilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sunucu belgesinin kullanıcı değiştirdikten sonra genellikle bu işlevini çağırın. OLE öğesi belgeye otomatik bir bağlantıyla bağlı ise, öğenin değişiklikleri yansıtacak şekilde güncelleştirilir. Microsoft Foundation Class Kitaplığı ile yazılmış kapsayıcı uygulamalarında [değiştiğinde](../../mfc/reference/coleclientitem-class.md#onchange) üye işlevini `COleClientItem` olarak adlandırılır.  
  
 Bu işlev çağrılarını `OnUpdate` öğesi, geçirme gönderme dışında belgenin öğelerin her biri için üye işlevi `pHint`, `lHint`, ve `nDrawAspect`. Bu parametreler öğelerine belgede yapılan değişiklikler hakkında bilgi aktarmak için kullanın. Bilgi kodlama `lHint` veya tanımlayabilirsiniz bir `CObject`-türetilmiş sınıf değişiklikler hakkında bilgi depolamak ve bu sınıfı kullanarak bir nesneyi geçirmek için `pHint`. Geçersiz kılma `OnUpdate` üye işlevinde, `COleServerItem`-türetilmiş sınıf kendi sunu değiştirilip bağlı olarak her bir öğeyi güncelleştirme en iyi duruma getirme.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek HIERSVR](../../visual-cpp-samples.md)   
 [COleLinkingDoc sınıfı](../../mfc/reference/colelinkingdoc-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDocument sınıfı](../../mfc/reference/coledocument-class.md)   
 [COleLinkingDoc sınıfı](../../mfc/reference/colelinkingdoc-class.md)   
 [COleTemplateServer sınıfı](../../mfc/reference/coletemplateserver-class.md)
