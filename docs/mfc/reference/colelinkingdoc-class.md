---
title: "COleLinkingDoc sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
dev_langs: C++
helpviewer_keywords:
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d9d02d128a96550cce393fc439ef7fdabcccd293
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="colelinkingdoc-class"></a>COleLinkingDoc sınıfı
Katıştırılmış öğelerine bağlama desteği OLE kapsayıcı belgeler için temel sınıfı içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|Oluşturan bir `COleLinkingDoc` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleLinkingDoc::Register](#register)|Belge OLE sistem DLL'leri ile kaydeder.|  
|[COleLinkingDoc::Revoke](#revoke)|Belgenin kaydını iptal eder.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|Belirtilen katıştırılmış öğeyi bulur.|  
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|Belirtilen bağlantılı öğeyi bulur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Katıştırılmış öğelerine bağlama destekleyen bir kapsayıcı uygulaması bir "bağlantı kapsayıcı." olarak adlandırılır [OCLIENT](../../visual-cpp-samples.md) örnek uygulama bir bağlantı kapsayıcı örneğidir.  
  
 Bağlantılı bir öğenin kaynak katıştırılmış bir öğe başka bir belgede olduğunda içeren belge katıştırılmış öğenin düzenlenmesi sırayla yüklenmesi gerekir. Bu nedenle, bir bağlantı kapsayıcı bağlantılı bir öğe kaynağını düzenlemek kullanıcının istediği zaman başka bir kapsayıcı uygulama tarafından başlatılan kurabilmesi gerekir. Uygulamanız da kullanmalıdır [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) başlatıldığında program aracılığıyla belgeleri oluşturabilmesi için sınıf.  
  
 Bir bağlantı kapsayıcı, kapsayıcı yapmak için belge sınıfından türetilen `COleLinkingDoc` yerine [COleDocument](../../mfc/reference/coledocument-class.md). Tüm diğer OLE kapsayıcısı ile gibi uygulamanın yerel veri yanı sıra katıştırılmış veya bağlantılı öğeler depolamak için sınıfınız tasarlamanız gerekir. Ayrıca, yerel verilerinizi depolamak için veri yapıları tasarlamanız gerekir. Tanımlarsanız bir `CDocItem`-uygulamanızı yerel için türetilmiş sınıf verileri tarafından tanımlanan arabirimi kullanabilir `COleDocument` OLE verilerinizi yanı sıra yerel verilerinizi depolamak için.  
  
 Program aracılığıyla başka bir kapsayıcı tarafından başlatılan uygulamanıza izin vermek için bildirme bir `COleTemplateServer` nesnesi, uygulamanızın bir üyesi olarak `CWinApp`-türetilmiş sınıf:  
  
 [!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]  
  
 İçinde `InitInstance` üye işlevini, `CWinApp`-türetilmiş sınıf, bir belge şablonu oluşturun ve belirtin, `COleLinkingDoc`-türetilmiş sınıf belge sınıfı:  
  
 [!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]  
  
 Bağlanma, `COleTemplateServer` nesnenin çağırarak belge şablonlarınızı nesnesine `ConnectTemplate` üye işlevini ve tüm sınıf çağırarak OLE sistemiyle nesneleri kaydetme **COleTemplateServer::RegisterAll**:  
  
 [!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]  
  
 Bir örnek için `CWinApp`-türetilmiş sınıf tanımı ve `InitInstance` işlev, OCLIENT bakın. H ve OCLIENT. MFC örnekteki CPP [OCLIENT](../../visual-cpp-samples.md).  
  
 Kullanma hakkında daha fazla bilgi için `COleLinkingDoc`, makalelerine bakın [kapsayıcıları: bir kapsayıcı uygulama](../../mfc/containers-implementing-a-container.md) ve [kapsayıcılar: Gelişmiş Özellikler](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="colelinkingdoc"></a>COleLinkingDoc::COleLinkingDoc  
 Oluşturan bir `COleLinkingDoc` OLE sistem DLL'leri ile iletişim başlayan olmadan nesnesi.  
  
```  
COleLinkingDoc();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız `Register` OLE belge açık olduğunu bildirmek için üye işlevi.  
  
##  <a name="onfindembeddeditem"></a>COleLinkingDoc::OnFindEmbeddedItem  
 Belge belirtilen ada sahip bir katıştırılmış OLE öğe içerip içermediğini belirlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszItemName`  
 Katıştırılmış OLE öğesi istenen adını işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen öğe için bir işaretçi; **NULL** öğenin bulunamaması durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama (adı karşılaştırma büyük küçük harfe duyarlı) belirtilen ada sahip bir öğe için katıştırılmış öğeleri listesi arar. Depolama veya katıştırılmış OLE öğeleri adlandırma kendi yöntemi varsa, bu işlev geçersiz kılar.  
  
##  <a name="ongetlinkeditem"></a>COleLinkingDoc::OnGetLinkedItem  
 Belgenin belirtilen ada sahip bir bağlantılı sunucu öğesi içerip içermediğini denetlemek için çerçevesi tarafından çağrılır.  
  
```  
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszItemName`  
 İstenen öğe bağlantılı OLE adını işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen öğe için bir işaretçi; **NULL** öğenin bulunamaması durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan `COleLinkingDoc` uygulama her zaman döndürür **NULL**. Bu işlev geçersiz kılınmadı türetilmiş sınıfında `COleServerDoc` (adı karşılaştırma büyük küçük harfe duyarlı) belirtilen ad ile bağlantılı bir öğe için OLE sunucusu öğeleri listesi aramak için. Depolama veya bağlantılı sunucu öğeleri alınıyor kendi yönteminizi uyguladıysanız bu işlev geçersiz kılar.  
  
##  <a name="register"></a>COleLinkingDoc::Register  
 OLE sistem DLL'leri belgenin açık olduğunu bildirir.  
  
```  
BOOL Register(
    COleObjectFactory* pFactory,  
    LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pFactory*  
 OLE üretecini işaretçisine (olabilir **NULL**).  
  
 `lpszPathName`  
 İşaretçi kapsayıcı belge tam yolu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belge başarıyla kaydedildi, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma veya belge OLE sistem DLL'leri ile kaydetmek için bir adlandırılmış dosya açılırken bu işlevini çağırın. Belge katıştırılmış bir öğeyi temsil eder, bu işlevi çağırmak için gerek yoktur.  
  
 Kullanıyorsanız `COleTemplateServer` , uygulamanızda `Register` tarafından sizin için adlı `COleLinkingDoc`'s uyarlamasını `OnNewDocument`, `OnOpenDocument`, ve `OnSaveDocument`.  
  
##  <a name="revoke"></a>COleLinkingDoc::Revoke  
 OLE sistem DLL'leri belgeyi artık açık olduğunu bildirir.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Açıklamalar  
 OLE sistem DLL'leri belgenin kaydı iptal etmek için bu işlevini çağırın.  
  
 Bu işlev bir adlandırılmış dosya kapatılırken çağırmanız gerekir, ancak genellikle doğrudan çağırmanız gerekmez. `Revoke`tarafından sizin için adlı `COleLinkingDoc`'s uyarlamasını `OnCloseDocument`, `OnNewDocument`, `OnOpenDocument`, ve `OnSaveDocument`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek OCLIENT](../../visual-cpp-samples.md)   
 [COleDocument sınıfı](../../mfc/reference/coledocument-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)
