---
title: "COleDocument sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDocument
- AFXOLE/COleDocument
- AFXOLE/COleDocument::COleDocument
- AFXOLE/COleDocument::AddItem
- AFXOLE/COleDocument::ApplyPrintDevice
- AFXOLE/COleDocument::EnableCompoundFile
- AFXOLE/COleDocument::GetInPlaceActiveItem
- AFXOLE/COleDocument::GetNextClientItem
- AFXOLE/COleDocument::GetNextItem
- AFXOLE/COleDocument::GetNextServerItem
- AFXOLE/COleDocument::GetPrimarySelectedItem
- AFXOLE/COleDocument::GetStartPosition
- AFXOLE/COleDocument::HasBlankItems
- AFXOLE/COleDocument::OnShowViews
- AFXOLE/COleDocument::RemoveItem
- AFXOLE/COleDocument::UpdateModifiedFlag
- AFXOLE/COleDocument::OnEditChangeIcon
- AFXOLE/COleDocument::OnEditConvert
- AFXOLE/COleDocument::OnEditLinks
- AFXOLE/COleDocument::OnFileSendMail
- AFXOLE/COleDocument::OnUpdateEditChangeIcon
- AFXOLE/COleDocument::OnUpdateEditLinksMenu
- AFXOLE/COleDocument::OnUpdateObjectVerbMenu
- AFXOLE/COleDocument::OnUpdatePasteLinkMenu
- AFXOLE/COleDocument::OnUpdatePasteMenu
dev_langs:
- C++
helpviewer_keywords:
- COleDocument [MFC], COleDocument
- COleDocument [MFC], AddItem
- COleDocument [MFC], ApplyPrintDevice
- COleDocument [MFC], EnableCompoundFile
- COleDocument [MFC], GetInPlaceActiveItem
- COleDocument [MFC], GetNextClientItem
- COleDocument [MFC], GetNextItem
- COleDocument [MFC], GetNextServerItem
- COleDocument [MFC], GetPrimarySelectedItem
- COleDocument [MFC], GetStartPosition
- COleDocument [MFC], HasBlankItems
- COleDocument [MFC], OnShowViews
- COleDocument [MFC], RemoveItem
- COleDocument [MFC], UpdateModifiedFlag
- COleDocument [MFC], OnEditChangeIcon
- COleDocument [MFC], OnEditConvert
- COleDocument [MFC], OnEditLinks
- COleDocument [MFC], OnFileSendMail
- COleDocument [MFC], OnUpdateEditChangeIcon
- COleDocument [MFC], OnUpdateEditLinksMenu
- COleDocument [MFC], OnUpdateObjectVerbMenu
- COleDocument [MFC], OnUpdatePasteLinkMenu
- COleDocument [MFC], OnUpdatePasteMenu
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 147a3bca2f4ad91aeaa2c74ac7a356d9404943fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="coledocument-class"></a>COleDocument sınıfı
Görsel düzenleme desteği OLE belgeleri için temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleDocument : public CDocument  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDocument::COleDocument](#coledocument)|Oluşturan bir `COleDocument` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDocument::AddItem](#additem)|Belgenin tarafından korunan öğeleri listesi için bir öğe ekler.|  
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|Yazdırma hedef cihaz için tüm istemci öğeleri belgede ayarlar.|  
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|OLE yapılandırılmış depolama dosya biçimini kullanarak depolanması belgeleri neden olur.|  
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|Şu anda yerinde etkin OLE öğeyi döndürür.|  
|[COleDocument::GetNextClientItem](#getnextclientitem)|Yineleme için sonraki istemci öğesini alır.|  
|[COleDocument::GetNextItem](#getnextitem)|Sonraki belge öğesi yineleme için alır.|  
|[COleDocument::GetNextServerItem](#getnextserveritem)|Yineleme için sonraki sunucu öğesini alır.|  
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|Birincil OLE öğeye belgede döndürür.|  
|[COleDocument::GetStartPosition](#getstartposition)|Yineleme başlamak için ilk konumunu alır.|  
|[COleDocument::HasBlankItems](#hasblankitems)|Belgedeki boş öğeleri denetler.|  
|[COleDocument::OnShowViews](#onshowviews)|Belge olduğunda görünür veya görünmez çağrılır.|  
|[COleDocument::RemoveItem](#removeitem)|Belgenin tarafından korunan öğelerin listesini öğeyi kaldırır.|  
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|Belge kapsanan OLE öğeleri değiştirilmişse, değiştirilmiş olarak işaretler.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|Simge menü komutu olayları işler.|  
|[COleDocument::OnEditConvert](#oneditconvert)|Katıştırılmış veya bağlantılı nesnenin bir türden diğerine dönüştürme diğerine işler.|  
|[COleDocument::OnEditLinks](#oneditlinks)|Düzen menüsünde bağlantılar komutta olayları işler.|  
|[COleDocument::OnFileSendMail](#onfilesendmail)|Bir posta iletisi belge ekli gönderir.|  
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|Düzenle/simge menü seçeneği için kullanıcı Arabirimi komutu güncelleştirmek için çerçevesi tarafından çağrılır.|  
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|Düzenle/bağlantılar menü seçeneği için kullanıcı Arabirimi komutu güncelleştirmek için çerçevesi tarafından çağrılır.|  
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Düzenleme için kullanıcı Arabirimi komutu güncelleştirmek için framework tarafından çağrılan / *ObjectName* menü seçeneğini ve düzenleme erişilen fiil alt / *ObjectName*.|  
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|Özel Yapıştır menü seçeneği için kullanıcı Arabirimi komutu güncelleştirmek için çerçevesi tarafından çağrılır.|  
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|' % S'komut UI Yapıştır menü seçeneği için güncelleştirmek için framework tarafından çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleDocument`türetilmiş **CDocument**, Microsoft Foundation Class Kitaplığı tarafından sağlanan belge/görünüm mimarisinin kullanmak, OLE uygulamaları sağlar.  
  
 `COleDocument`bir belge koleksiyonu olarak davranır [CDocItem](../../mfc/reference/cdocitem-class.md) OLE öğeleri işlemek için nesneleri. Çünkü, belgeleri OLE öğeleri içeren gerekir kapsayıcı ve sunucu uygulamaları böyle bir mimari gerektirir. [COleServerItem](../../mfc/reference/coleserveritem-class.md) ve [COleClientItem](../../mfc/reference/coleclientitem-class.md) sınıfları, hem de türetilmiş `CDocItem`, uygulamalar ve OLE öğeleri arasındaki etkileşimler yönetin.  
  
 Basit kapsayıcı uygulama yazıyorsanız, belge sınıfından türetilen `COleDocument`. Kendi belgeleri tarafından bulunan katıştırılmış öğeleri bağlantılandırma destekleyen bir kapsayıcı uygulama yazıyorsanız, belge sınıfından türetilen [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md). Bir sunucu uygulaması veya birleşimi kapsayıcı/sunucu yazıyorsanız, belge sınıfından türetilen [COleServerDoc](../../mfc/reference/coleserverdoc-class.md). `COleLinkingDoc`ve `COleServerDoc` türetilmiş `COleDocument`, kullanılabilir tüm hizmetleri bu sınıfların devralmak için `COleDocument` ve **CDocument**.  
  
 Kullanılacak `COleDocument`, buradan bir sınıf türetin ve uygulamanın OLE dışı veri yanı sıra katıştırılmış veya bağlı öğeleri yönetmek için işlevselliği ekleyin. Tanımlarsanız `CDocItem`-türetilmiş uygulamanın yerel verileri depolamak için sınıflar tarafından tanımlanan varsayılan uygulaması kullanabileceğiniz `COleDocument` , OLE ve OLE dışı verilerinizi depolamak için. OLE dışı verilerinizden ayrı olarak OLE öğeleri depolamak için kendi veri yapılarını de tasarlayabilirsiniz. Daha fazla bilgi için bkz: [kapsayıcılar: bileşik dosyaları](../../mfc/containers-compound-files.md)...  
  
 **CDocument** posta desteği (MAPI) varsa, belgenizi posta aracılığıyla göndermeyi destekler. `COleDocument`güncelleştirilmiş [OnFileSendMail](#onfilesendmail) bileşik belgeler düzgün işlenecek. Daha fazla bilgi için makalelere bakın [MAPI](../../mfc/mapi.md) ve [MFC içinde MAPI desteği](../../mfc/mapi-support-in-mfc.md)...  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="additem"></a>COleDocument::AddItem  
 Belgeye bir öğe eklemek için bu işlevini çağırın.  
  
```  
virtual void AddItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 Eklenmekte olan belge öğesi işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrılır olduğunda bu işlev açıkça çağırın gerekmez `COleClientItem` veya `COleServerItem` bir belge için bir işaretçi kabul Oluşturucusu.  
  
##  <a name="applyprintdevice"></a>COleDocument::ApplyPrintDevice  
 Tüm katıştırılmış Hedefi Yazdır aygıtı değiştirmek için bu işlevi çağırmak [COleClientItem](../../mfc/reference/coleclientitem-class.md) uygulamanızın kapsayıcı belge öğeleri.  
  
```  
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptd`  
 İşaretçi bir **DVTARGETDEVICE** yeni yazdırma hedef aygıt hakkındaki bilgileri içeren veri yapısı. Olabilir **NULL**.  
  
 `ppd`  
 İşaretçi bir **PRINTDLG** yeni yazdırma hedef aygıt hakkındaki bilgileri içeren veri yapısı. Olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev tüm öğeler için yazdırma hedef aygıt güncelleştirir, ancak bu öğeler için sunu önbelleğini yenilemez. Bir öğe için sunu önbelleği güncelleştirmek için arama [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink).  
  
 Bu işlev bağımsız değişkenleri OLE hedef aygıtı belirlemek için kullandığı bilgileri içerir. [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) yapısı ortak Yazdır iletişim kutusunu başlatmak için Windows kullandığı bilgileri içerir. Kullanıcı iletişim kutusunu kapattıktan sonra Windows bu yapısında kullanıcının seçimlerini hakkında bilgi verir. `m_pd` Üyesi bir [CPrintDialog](../../mfc/reference/cprintdialog-class.md) nesne bir **PRINTDLG** yapısı.  
  
 Daha fazla bilgi için bkz: [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Windows SDK'sındaki yapısı.  
  
 Daha fazla bilgi için bkz: [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) Windows SDK'sındaki yapısı.  
  
##  <a name="coledocument"></a>COleDocument::COleDocument  
 Oluşturan bir `COleDocument` nesnesi.  
  
```  
COleDocument();
```  
  
##  <a name="enablecompoundfile"></a>COleDocument::EnableCompoundFile  
 Bileşik dosya biçimini kullanarak belgeyi saklamak isterseniz bu işlevini çağırın.  
  
```  
void EnableCompoundFile(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bEnable`  
 Bileşik dosya desteği etkin mi yoksa devre dışı mı olduğunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapısal depolama olarak da adlandırılır. Oluşturucudan genellikle bu işlev çağrısı, `COleDocument`-türetilmiş sınıf. Bileşik belgeler hakkında daha fazla bilgi için bkz: [kapsayıcılar: bileşik dosyalar](../../mfc/containers-compound-files.md)...  
  
 Bu üye işlevini çağırmayın, belgeleri nonstructured ("Düz") dosya biçiminde depolanır.  
  
 Bileşik dosya desteği etkin veya devre dışı bir belge için sonra ayarı belgenin ömrü boyunca değiştirilmemelidir.  
  
##  <a name="getinplaceactiveitem"></a>COleDocument::GetInPlaceActiveItem  
 OLE almak için bu işlevi öğesi çağrısı tarafından tanımlanan görünüm içeren çerçeve penceresi yerinde şu anda etkinleştirilirse `pWnd`.  
  
```  
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Kapsayıcı belge görüntüleyen pencerenin işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek, yerinde etkin OLE öğesi için bir işaretçi; **NULL** olup olmadığını OLE öğe şu anda "yerinde etkin" durumunda.  
  
##  <a name="getnextclientitem"></a>COleDocument::GetNextClientItem  
 Art arda belgenize istemci öğelerin her birini erişmek için bu işlevini çağırın.  
  
```  
COleClientItem* GetNextClientItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Bir başvuru bir **konumu** değerinin ayarlanmış önceki çağrısıyla `GetNextClientItem`; başlangıç değeri tarafından döndürülen `GetStartPosition` üye işlevi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belgede, sonraki istemci öğesi için bir işaretçi veya **NULL** olması durumunda daha fazla istemci öğe yok.  
  
### <a name="remarks"></a>Açıklamalar  
 Her çağrı değerini sonra `pos` olabilir veya bir istemci öğesi olmayabilir belgedeki bir sonraki öğe için ayarlanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]  
  
##  <a name="getnextitem"></a>COleDocument::GetNextItem  
 Art arda belgenize öğelerin her birini erişmek için bu işlevini çağırın.  
  
```  
virtual CDocItem* GetNextItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Bir başvuru bir **konumu** değerinin ayarlanmış önceki çağrısıyla `GetNextItem`; başlangıç değeri tarafından döndürülen `GetStartPosition` üye işlevi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirli bir konumda belge öğesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Her çağrı değerini sonra `pos` ayarlanır **konumu** belgedeki sonraki öğesinin değeri. Alınan öğe belgesinde, yeni değer, son öğe ise `pos` olan **NULL**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]  
  
##  <a name="getnextserveritem"></a>COleDocument::GetNextServerItem  
 Art arda belgenize sunucu öğelerin her birini erişmek için bu işlevini çağırın.  
  
```  
COleServerItem* GetNextServerItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Bir başvuru bir **konumu** değerinin ayarlanmış önceki çağrısıyla `GetNextServerItem`; başlangıç değeri tarafından döndürülen `GetStartPosition` üye işlevi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belgede, sonraki sunucu öğesine bir işaretçi veya **NULL** olması durumunda daha fazla sunucu öğe yok.  
  
### <a name="remarks"></a>Açıklamalar  
 Her çağrı değerini sonra `pos` olabilir ya da bir sunucu öğesi olmayabilir belgedeki bir sonraki öğe için ayarlanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]  
  
##  <a name="getprimaryselecteditem"></a>COleDocument::GetPrimarySelectedItem  
 Belirtilen görünüm şu anda seçili OLE öğesinde almak için çerçevesi tarafından çağrılır.  
  
```  
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```  
  
### <a name="parameters"></a>Parametreler  
 `pView`  
 Belge görüntüleme etkin Görünüm nesnesine işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek bir işaretçi OLE öğesi seçili; **NULL** hiçbir OLE öğeleri seçili ya da birden fazla bir seçilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama kapsanan OLE listesini tek bir seçili öğe için öğeleri arar ve bir işaretçi kendisine döndürür. Seçilen öğe yok veya olup olmadığını seçili birden fazla öğesi, işlevi döndürür **NULL**. Geçersiz kılmanız gerekir `CView::IsSelected` çalışması bu işlev için Görünüm sınıfınızda üye işlevi. Kapsanan OLE öğeleri depolama kendi yöntemi varsa, bu işlev geçersiz kılar.  
  
##  <a name="getstartposition"></a>COleDocument::GetStartPosition  
 Belge ilk öğe konumunu almak için bu işlevini çağırın.  
  
```  
virtual POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** belgenin öğeler arasında; yineleme başlatmak için kullanılan değer **NULL** belgedeki hiçbir öğe varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen değer geçirmek `GetNextItem`, `GetNextClientItem`, veya `GetNextServerItem`.  
  
##  <a name="hasblankitems"></a>COleDocument::HasBlankItems  
 Belgenin boş bir öğe içerip içermediğini belirlemek için bu işlevini çağırın.  
  
```  
BOOL HasBlankItems() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belge boş öğeler içeriyorsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Boş bir öğenin, dikdörtgen boştur biridir.  
  
##  <a name="oneditchangeicon"></a>COleDocument::OnEditChangeIcon  
 OLE Simge Değiştir iletişim kutusu görüntüler ve şu anda seçili OLE öğesi iletişim kutusunda kullanıcının seçtiği simgesini temsil eden simgeyi değiştirir.  
  
```  
afx_msg void OnEditChangeIcon();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `OnEditChangeIcon`oluşturur ve başlatır bir `COleChangeIconDialog` Simge Değiştir iletişim kutusu.  
  
##  <a name="oneditconvert"></a>COleDocument::OnEditConvert  
 OLE Dönüştür iletişim kutusu görüntüler ve iletişim kutusunda kullanıcı seçimlerini göre şu anda seçili OLE öğesi etkinleştirir veya dönüştürür.  
  
```  
afx_msg void OnEditConvert();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `OnEditConvert`oluşturur ve başlatır bir `COleConvertDialog` Dönüştür iletişim kutusu.  
  
 Dönüştürme örneği Microsoft Word belgesi WordPad belgesine dönüştürülüyor.  
  
##  <a name="oneditlinks"></a>COleDocument::OnEditLinks  
 OLE düzenleme/bağlantıları iletişim kutusunu görüntüler.  
  
```  
afx_msg void OnEditLinks();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `OnEditLinks`oluşturur ve başlatır bir `COleLinksDialog` bağlantılı nesneleri değiştirmek kullanıcı sağlayan bağlantıları iletişim kutusu.  
  
##  <a name="onfilesendmail"></a>COleDocument::OnFileSendMail  
 Yerleşik posta ana bilgisayar üzerinden bir ileti (varsa) belgeyle ek olarak gönderir.  
  
```  
afx_msg void OnFileSendMail();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `OnFileSendMail`çağrıları `OnSaveDocument` (Kaydet) adsız ve değiştirilmiş belgeleri elektronik posta gönderilir geçici bir dosya için seri hale getirilemedi. Belge değiştirilmedi, geçici bir dosya gerekli değildir; özgün gönderilir. `OnFileSendMail`MAPI32 yükler. DLL zaten yüklü.  
  
 Uygulaması aksine `OnFileSendMail` için **CDocument**, bu işlev bileşik dosyalar doğru şekilde işler.  
  
 Daha fazla bilgi için bkz: [MAPI konuları](../../mfc/mapi.md) ve [MFC içinde MAPI desteği](../../mfc/mapi-support-in-mfc.md) makaleleri...  
  
##  <a name="onshowviews"></a>COleDocument::OnShowViews  
 Framework durum değişiklikleri belgenin görünürlük sonra bu işlevi çağırır.  
  
```  
virtual void OnShowViews(BOOL bVisible);
```  
  
### <a name="parameters"></a>Parametreler  
 `bVisible`  
 Belge görünür veya görünmez hale geldi gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan sürümü hiçbir şey yapmaz. Uygulamanızı belgenin görünürlük değiştiğinde özel bir işlem gerçekleştirmeniz gerekirse geçersiz kılar.  
  
##  <a name="onupdateeditchangeicon"></a>COleDocument::OnUpdateEditChangeIcon  
 Düzen menüsünde Simge Değiştir komutu güncelleştirmek için framework tarafından çağrılır.  
  
```  
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCmdUI`  
 Bir işaretçi bir `CCmdUI` yapısı güncelleştirme komutu oluşturulan menü temsil eder. Güncelleştirme işleyicisi çağrılarını **etkinleştirmek** üye işlevini `CCmdUI` aracılığıyla yapısı `pCmdUI` kullanıcı arabirimini güncelleştirmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 `OnUpdateEditChangeIcon`Geçerli bir simge olup olmadığına belgede var bağlı olarak komutun kullanıcı arabirimini güncelleştirir. Bu işlev davranışını değiştirmek için geçersiz kılar.  
  
##  <a name="onupdateeditlinksmenu"></a>COleDocument::OnUpdateEditLinksMenu  
 Düzen menüsünden Bağlantılar komutunu güncelleştirmek için çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCmdUI`  
 Bir işaretçi bir `CCmdUI` yapısı güncelleştirme komutu oluşturulan menü temsil eder. Güncelleştirme işleyicisi çağrılarını **etkinleştirmek** üye işlevini `CCmdUI` aracılığıyla yapısı `pCmdUI` kullanıcı arabirimini güncelleştirmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Belge ilk OLE öğesi ile başlayan `OnUpdateEditLinksMenu` erişen her bir öğe, öğe, bir bağlantı olduğu ve bir bağlantı olması durumunda bağlantılar komutunu etkinleştirir olup olmadığını sınar. Bu işlev davranışını değiştirmek için geçersiz kılar.  
  
##  <a name="onupdateobjectverbmenu"></a>COleDocument::OnUpdateObjectVerbMenu  
 Güncelleştirilecek çerçevesi tarafından çağrılır *ObjectName* Düzen menüsü ve erişilen fiil alt komutunu *ObjectName* komutu, burada *ObjectName* adıdır belgede katıştırılmış OLE nesne.  
  
```  
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCmdUI`  
 Bir işaretçi bir `CCmdUI` yapısı güncelleştirme komutu oluşturulan menü temsil eder. Güncelleştirme işleyicisi çağrılarını **etkinleştirmek** üye işlevini `CCmdUI` aracılığıyla yapısı `pCmdUI` kullanıcı arabirimini güncelleştirmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 `OnUpdateObjectVerbMenu`güncelleştirmeleri *ObjectName* bağlı olarak desteklemediğini geçerli bir nesne belgede komutunun kullanıcı arabirimi. Bir nesne varsa, *ObjectName* Düzenle menüsündeki etkindir. Bu komutu seçildiğinde fiil alt görüntülenir. Fiili alt düzenleme, Özellikler vb. gibi nesne için kullanılabilen tüm fiil komutlarını içerir. Bu işlev davranışını değiştirmek için geçersiz kılar.  
  
##  <a name="onupdatepastelinkmenu"></a>COleDocument::OnUpdatePasteLinkMenu  
 Bağlantılı bir OLE öğe panodan yapıştırılan olup olmadığını belirlemek için çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCmdUI`  
 Bir işaretçi bir `CCmdUI` yapısı güncelleştirme komutu oluşturulan menü temsil eder. Güncelleştirme işleyicisi çağrılarını **etkinleştirmek** üye işlevini `CCmdUI` aracılığıyla yapısı `pCmdUI` kullanıcı arabirimini güncelleştirmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel Yapıştır menü komutu etkin veya devre dışı olup olmadığını öğesi belgeye veya yapıştırılabilmesi için bağlı olarak.  
  
##  <a name="onupdatepastemenu"></a>COleDocument::OnUpdatePasteMenu  
 Katıştırılmış OLE öğe panodan yapıştırılan olup olmadığını belirlemek için çerçevesi tarafından çağrılır.  
  
```  
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCmdUI`  
 Bir işaretçi bir `CCmdUI` yapısı güncelleştirme komutu oluşturulan menü temsil eder. Güncelleştirme işleyicisi çağrılarını **etkinleştirmek** üye işlevini `CCmdUI` aracılığıyla yapısı `pCmdUI` kullanıcı arabirimini güncelleştirmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Yapıştır menü komutu ve düğmesi etkinleştirilir veya olup öğesi belgeye veya yapıştırılabilmesi için bağlı olarak devre dışı.  
  
##  <a name="removeitem"></a>COleDocument::RemoveItem  
 Belgeden öğe kaldırmak için bu işlevini çağırın.  
  
```  
virtual void RemoveItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `pItem`  
 Kaldırılacak belge öğesi işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle bu işlev açıkça çağırın gerekmez; için Yıkıcılar tarafından çağrılan `COleClientItem` ve `COleServerItem`.  
  
##  <a name="updatemodifiedflag"></a>COleDocument::UpdateModifiedFlag  
 Belge kapsanan OLE öğeleri değiştirilmişse, değiştirilmiş olarak işaretlemek için bu işlevini çağırın.  
  
```  
virtual void UpdateModifiedFlag();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu belgeyi yerel verilerde değişiklik olsa bile kapatmadan önce belgeyi kaydetmek için kullanıcıdan framework sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek KAPSAYICI](../../visual-cpp-samples.md)   
 [MFC örnek MFCBIND](../../visual-cpp-samples.md)   
 [CDocument sınıfı](../../mfc/reference/cdocument-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



