---
title: Cotadocument sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 666ca54f55c5bb0dd4070a4984500dc19dc9d372
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504034"
---
# <a name="coledocument-class"></a>Cotadocument sınıfı

Görsel düzenlemesini destekleyen OLE belgelerinin temel sınıfı.

## <a name="syntax"></a>Sözdizimi

```
class COleDocument : public CDocument
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copadocument:: Cotadocument](#coledocument)|Bir `COleDocument` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotadocument:: AddItem](#additem)|Belge tarafından tutulan öğeler listesine bir öğe ekler.|
|[Cotadocument:: ApplyPrintDevice](#applyprintdevice)|Yazdırma hedefi cihazını belgedeki tüm istemci öğeleri için ayarlar.|
|[Cotadocument:: EnableCompoundFile](#enablecompoundfile)|Belgelerin OLE yapısal depolama dosya biçimi kullanılarak depolanmasına neden olur.|
|[Cotadocument:: Getınplaceactiveıtem](#getinplaceactiveitem)|Şu anda yerinde etkin olan OLE öğesini döndürür.|
|[Cotadocument:: Getnextclienentidıtem](#getnextclientitem)|Yineleme için bir sonraki istemci öğesini alır.|
|[Cotadocument:: GetNextItem](#getnextitem)|Yineleme için bir sonraki belge öğesini alır.|
|[Cotadocument:: GetNextServerItem](#getnextserveritem)|Yineleme için bir sonraki sunucu öğesini alır.|
|[Copadocument:: Getprimaryselectedidıtem](#getprimaryselecteditem)|Belgedeki birincil seçili OLE öğesini döndürür.|
|[Cotadocument:: GetStartPosition](#getstartposition)|Yinelemeye başlamak için başlangıç konumunu alır.|
|[Cotadocument:: Hasblankıtems](#hasblankitems)|Belgedeki boş öğeleri denetler.|
|[Cotadocument:: OnShowViews](#onshowviews)|Belge görünür veya görünmez hale geldiğinde çağırılır.|
|[Cotadocument:: RemoveItem](#removeitem)|Belge tarafından tutulan öğelerin listesinden bir öğeyi kaldırır.|
|[Cotadocument:: UpdateModifiedFlag](#updatemodifiedflag)|İçerilen OLE öğelerinden herhangi biri değiştirilmişse belgeyi değiştirilmiş olarak işaretler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotadocument:: Oneditchangeıcon](#oneditchangeicon)|Değişiklik simgesi menü komutunda olayları işler.|
|[Cotadocument:: OnEditConvert](#oneditconvert)|Katıştırılmış veya bağlantılı nesnenin bir türden diğerine dönüştürülmesini işler.|
|[Cotadocument:: OnEditLinks](#oneditlinks)|Düzenleme menüsündeki Bağlantılar komutunda olayları işler.|
|[Cotadocument:: OnFileSendMail](#onfilesendmail)|Belge ekli olarak bir posta iletisi gönderir.|
|[Cotadocument:: Onupdateeditchangeıcon](#onupdateeditchangeicon)|Düzenle/Değiştir simgesi menü seçeneği için komut Kullanıcı arabirimini güncelleştirmek üzere Framework tarafından çağırılır.|
|[Cotadocument:: OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|Düzenleme/bağlantılar menü seçeneği için komut Kullanıcı arabirimini güncelleştirmek üzere Framework tarafından çağırılır.|
|[Cotadocument:: OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Düzenleme/ *NesneAdı* menü seçeneği için komut Kullanıcı arabirimini ve Edit/ *ObjectName*öğesinden erişilen fiil alt menüsünü güncelleştirmek için Framework tarafından çağırılır.|
|[Cotadocument:: OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|Özel Yapıştır menü seçeneği için komut Kullanıcı arabirimini güncelleştirmek üzere Framework tarafından çağırılır.|
|[Cotadocument:: OnUpdatePasteMenu](#onupdatepastemenu)|Yapıştırma menü seçeneği için komut Kullanıcı arabirimini güncelleştirmek üzere Framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

`COleDocument`, OLE uygulamalarınızın `CDocument`Microsoft Foundation Class Kitaplığı tarafından belirtilen belge/görünüm mimarisini kullanmasına izin veren öğesinden türetilir.

`COleDocument`OLE öğelerini işlemek için bir belgeyi [CDocItem](../../mfc/reference/cdocitem-class.md) nesneleri koleksiyonu olarak değerlendirir. Hem kapsayıcı hem de sunucu uygulamaları, belgelerinin OLE öğeleri içermesi gerektiğinden böyle bir mimari gerektirir. Her ikisi de türetilmiş olan `CDocItem` [copaserverıtem](../../mfc/reference/coleserveritem-class.md) ve [Colet clienentidıtem](../../mfc/reference/coleclientitem-class.md) sınıfları, uygulamalar ve OLE öğeleri arasındaki etkileşimleri yönetir.

Basit bir kapsayıcı uygulaması yazıyorsanız, belge sınıfınızı öğesinden `COleDocument`türetirsiniz. Belgelerinin içerdiği katıştırılmış öğelere bağlamayı destekleyen bir kapsayıcı uygulaması yazıyorsanız, belge sınıfınızı [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)öğesinden türetirsiniz. Bir sunucu uygulaması veya birleşim kapsayıcısı/sunucusu yazıyorsanız, belge sınıfınızı [Cotaserverdoc](../../mfc/reference/coleserverdoc-class.md)' dan türetirsiniz. `COleLinkingDoc`ve `COleServerDoc` ' den `COleDocument`türetilir, bu nedenle bu sınıfların ve `CDocument`' de `COleDocument` bulunan tüm hizmetleri devralması gerekir.

Kullanmak `COleDocument`için, öğesinden bir sınıf türetirsiniz ve uygulamanın OLE dışı verilerini ve katıştırılmış ya da bağlantılı öğeleri yönetmek için işlevsellik ekleyin. Uygulamanın yerel verilerini `CDocItem`depolamak için türetilmiş sınıflar tanımlarsanız, hem ole hem de OLE olmayan verileri depolamak için tarafından `COleDocument` tanımlanan varsayılan uygulamayı kullanabilirsiniz. OLE olmayan verilerinizi OLE öğelerinden ayrı olarak depolamak için kendi veri yapılarınızı da tasarlayabilirsiniz. Daha fazla bilgi için bkz. Makale [kapsayıcıları: Bileşik dosyalar](../../mfc/containers-compound-files.md)..

`CDocument`posta desteği (MAPI) varsa, belgenizi posta yoluyla göndermeyi destekler. `COleDocument`, bileşen belgelerini doğru şekilde işlemek için [OnFileSendMail](#onfilesendmail) 'i güncelleştirmiştir. Daha fazla bilgi için MFC 'de [MAPI](../../mfc/mapi.md) ve [MAPI desteği](../../mfc/mapi-support-in-mfc.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

##  <a name="additem"></a>Cotadocument:: AddItem

Belgeye öğe eklemek için bu işlevi çağırın.

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Eklenmekte olan belge öğesinin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir belge işaretçisi kabul eden veya `COleClientItem` `COleServerItem` Oluşturucusu tarafından çağrıldığında, bu işlevi açıkça çağırmanız gerekmez.

##  <a name="applyprintdevice"></a>Cotadocument:: ApplyPrintDevice

Uygulamanızın kapsayıcı belgesindeki tüm gömülü [Colet](../../mfc/reference/coleclientitem-class.md) öğeleri için yazdırma hedefi cihazını değiştirmek için bu işlevi çağırın.

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>Parametreler

*ptd*<br/>
Yeni yazdırma hedefi `DVTARGETDEVICE` aygıtı hakkında bilgi içeren bir veri yapısına yönelik işaretçi. NULL olabilir.

*PDF*<br/>
Yeni yazdırma hedefi `PRINTDLG` aygıtı hakkında bilgi içeren bir veri yapısına yönelik işaretçi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, yazdırma hedefi cihazını tüm öğeler için güncelleştirir, ancak bu öğelerin sunu önbelleğini yenilemez. Bir öğenin sunu önbelleğini güncelleştirmek için [Cotaclientidıtem:: UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)komutunu çağırın.

Bu işlevin bağımsız değişkenleri, OLE tarafından hedef cihazı tanımlamak için kullanılan bilgileri içerir. [PrintDlg](/windows/win32/api/commdlg/ns-commdlg-pdw) yapısı, Windows 'un ortak Yazdır iletişim kutusunu başlatmak için kullandığı bilgileri içerir. Kullanıcı iletişim kutusunu kapattıktan sonra, Windows kullanıcının bu yapıda seçimleriyle ilgili bilgileri döndürür. [CPrintDialog](../../mfc/reference/cprintdialog-class.md) nesnesinin `PRINTDLG` üyesi bir yapıdır. `m_pd`

Daha fazla bilgi için Windows SDK [PrintDlg](/windows/win32/api/commdlg/ns-commdlg-pdw) yapısına bakın.

Daha fazla bilgi için Windows SDK [Dvtargetdevice](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) yapısına bakın.

##  <a name="coledocument"></a>Copadocument:: Cotadocument

Bir `COleDocument` nesnesi oluşturur.

```
COleDocument();
```

##  <a name="enablecompoundfile"></a>Cotadocument:: EnableCompoundFile

Belgeyi bileşik dosya biçimini kullanarak depolamak istiyorsanız bu işlevi çağırın.

```
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
Birleşik dosya desteğinin etkin veya devre dışı olduğunu belirtir.

### <a name="remarks"></a>Açıklamalar

Bu, yapılandırılmış depolama olarak da adlandırılır. Genellikle bu işlevi türetilmiş sınıfınızın oluşturucusundan `COleDocument`çağırabilirsiniz. Bileşik belgeler hakkında daha fazla bilgi için bkz. Makale [kapsayıcıları: Bileşik dosyalar](../../mfc/containers-compound-files.md)..

Bu üye işlevini çağırmayın, belgeler yapılandırılmamış ("düz") dosya biçiminde depolanır.

Bir belge için Birleşik dosya desteği etkinleştirildikten veya devre dışı bırakıldıktan sonra, ayar belgenin ömrü boyunca değiştirilmemelidir.

##  <a name="getinplaceactiveitem"></a>Cotadocument:: Getınplaceactiveıtem

Bu işlevi, şu anda etkin olan OLE öğesini, *pWnd*tarafından tanımlanan görünümü içeren çerçeve penceresinde yerinde sağlamak için çağırın.

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Kapsayıcı belgesini görüntüleyen pencerenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Tek, yerinde etkin OLE öğesine yönelik bir işaretçi; Şu anda "yerinde etkin" durumunda hiçbir OLE öğesi yoksa NULL.

##  <a name="getnextclientitem"></a>Cotadocument:: Getnextclienentidıtem

Belgenizdeki her bir istemci öğesine erişmek için bu işlevi tekrar tekrar çağırın.

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Önceki bir çağrısıyla `GetNextClientItem`ayarlanan konum değerine bir başvuru; ilk değer `GetStartPosition` üye işlevi tarafından döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Belgedeki bir sonraki istemci öğesine yönelik bir işaretçi veya daha fazla istemci öğesi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Her çağrıdan sonra, *POS* değeri belgedeki bir sonraki öğe için ayarlanır, bu da bir istemci öğesi olabilir veya olmayabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

##  <a name="getnextitem"></a>Cotadocument:: GetNextItem

Belgenizdeki her öğeye erişmek için bu işlevi tekrar tekrar çağırın.

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Önceki bir çağrısıyla `GetNextItem`ayarlanan konum değerine bir başvuru; ilk değer `GetStartPosition` üye işlevi tarafından döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konumdaki belge öğesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Her çağrıdan sonra, *POS* 'un değeri belgedeki bir sonrakı öğenin konum değerine ayarlanır. Alınan öğe belgedeki son öğe ise, *POS* 'un yenı değeri null olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

##  <a name="getnextserveritem"></a>Cotadocument:: GetNextServerItem

Belgenizdeki her bir sunucu öğesine erişmek için bu işlevi tekrar tekrar çağırın.

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Önceki bir çağrısıyla `GetNextServerItem`ayarlanan konum değerine bir başvuru; ilk değer `GetStartPosition` üye işlevi tarafından döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Belgedeki bir sonraki sunucu öğesine yönelik bir işaretçi veya daha fazla sunucu öğesi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Her çağrıdan sonra, *POS* değeri belgedeki bir sonraki öğe için ayarlanır, bu da bir sunucu öğesi olabilir veya olmayabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

##  <a name="getprimaryselecteditem"></a>Copadocument:: Getprimaryselectedidıtem

Belirtilen görünümde seçili olan OLE öğesini almak için Framework tarafından çağırılır.

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>Parametreler

*pView*<br/>
Belgeyi görüntüleyen etkin görünüm nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Tek, seçili OLE öğesine yönelik bir işaretçi; Hiçbir OLE öğesi seçilmezse veya birden fazla seçilirse NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, tek bir seçili öğe için içerilen OLE öğelerinin listesini arar ve ona bir işaretçi döndürür. Seçili bir öğe yoksa veya birden fazla öğe seçili ise, işlev NULL değerini döndürür. Bu işlevin çalışması için `CView::IsSelected` görünüm sınıfınıza üye işlevini geçersiz kılmanız gerekir. İçerilen OLE öğelerini depolamak için kendi yönteminiz varsa, bu işlevi geçersiz kılın.

##  <a name="getstartposition"></a>Cotadocument:: GetStartPosition

Belgedeki ilk öğenin konumunu almak için bu işlevi çağırın.

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin öğeleri arasında yineleme başlamak için kullanılabilecek bir konum değeri; Belgede hiç öğe yoksa NULL.

### <a name="remarks"></a>Açıklamalar

`GetNextItem` ,`GetNextClientItem`, Veya`GetNextServerItem`döndürülen değeri geçirin.

##  <a name="hasblankitems"></a>Cotadocument:: Hasblankıtems

Belgenin boş öğeler içerip içermediğini öğrenmek için bu işlevi çağırın.

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belge herhangi bir boş öğe içeriyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Boş bir öğe, dikdörtgeni boş olan bir öğedir.

##  <a name="oneditchangeicon"></a>Cotadocument:: Oneditchangeıcon

OLE Change Icon iletişim kutusunu görüntüler ve seçili olan OLE öğesini temsil eden simgeyi kullanıcının iletişim kutusunda seçtiği simgeye dönüştürür.

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>Açıklamalar

`OnEditChangeIcon``COleChangeIconDialog` değişiklik simgesi iletişim kutusu oluşturur ve başlatır.

##  <a name="oneditconvert"></a>Cotadocument:: OnEditConvert

OLE Convert iletişim kutusunu görüntüler ve iletişim kutusundaki Kullanıcı seçimlerine göre şu anda seçili olan OLE öğesini dönüştürür veya etkinleştirir.

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>Açıklamalar

`OnEditConvert`bir `COleConvertDialog` Dönüştür iletişim kutusu oluşturur ve başlatır.

Dönüştürme örneği bir Microsoft Word belgesini WordPad belgesine dönüştürmektir.

##  <a name="oneditlinks"></a>Cotadocument:: OnEditLinks

OLE düzenleme/bağlantılar iletişim kutusunu görüntüler.

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>Açıklamalar

`OnEditLinks`kullanıcının bağlı nesneleri değiştirmesine `COleLinksDialog` izin veren bir bağlantılar iletişim kutusu oluşturur ve başlatır.

##  <a name="onfilesendmail"></a>Cotadocument:: OnFileSendMail

Belge eki olan yerleşik posta ana bilgisayarı (varsa) aracılığıyla bir ileti gönderir.

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>Açıklamalar

`OnFileSendMail`adsız `OnSaveDocument` ve değiştirilmiş belgeleri, daha sonra elektronik posta aracılığıyla gönderilen geçici bir dosyaya seri hale getirmek (kaydetmek) için çağırır. Belge değiştirilmediyse geçici bir dosya gerekmez; özgün değer gönderilir. `OnFileSendMail`MAPI32 yükler. DLL dosyası zaten yüklü değilse.

Uygulamasının uygulamasından `OnFileSendMail` `CDocument`farklı olarak, bu işlev bileşik dosyaları doğru şekilde işler.

Daha fazla bilgi için bkz. MFC makalelerinde [MAPI konuları](../../mfc/mapi.md) ve [MAPI desteği](../../mfc/mapi-support-in-mfc.md) .

##  <a name="onshowviews"></a>Cotadocument:: OnShowViews

Çerçeve, belgenin görünürlük durumu değişikliklerinden sonra bu işlevi çağırır.

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>Parametreler

*bVisible*<br/>
Belgenin görünür olup olmadığını veya görünmez hale geldiğini gösterir.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan sürümü hiçbir şey yapmaz. Belge görünürlüğü değiştiğinde uygulamanızın özel bir işlem gerçekleştirmesi gerekiyorsa bunu geçersiz kılın.

##  <a name="onupdateeditchangeicon"></a>Cotadocument:: Onupdateeditchangeıcon

Düzenleme menüsünde simge değiştir komutunu güncelleştirmek için Framework tarafından çağırılır.

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Update komutunu oluşturan menüyü `CCmdUI` temsil eden bir yapıya yönelik işaretçi. Güncelleştirme işleyicisi, Kullanıcı arabirimini `Enable` güncelleştirmek için *pCmdUI* aracılığıyla `CCmdUI` yapının üye işlevini çağırır.

### <a name="remarks"></a>Açıklamalar

`OnUpdateEditChangeIcon`belgede geçerli bir simgenin var olup olmadığına bağlı olarak komutun Kullanıcı arabirimini güncelleştirir. Davranışı değiştirmek için bu işlevi geçersiz kılın.

##  <a name="onupdateeditlinksmenu"></a>Cotadocument:: OnUpdateEditLinksMenu

Düzenleme menüsündeki Links komutunu güncelleştirmek için Framework tarafından çağırılır.

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Update komutunu oluşturan menüyü `CCmdUI` temsil eden bir yapıya yönelik işaretçi. Güncelleştirme işleyicisi, Kullanıcı arabirimini `Enable` güncelleştirmek için *pCmdUI* aracılığıyla `CCmdUI` yapının üye işlevini çağırır.

### <a name="remarks"></a>Açıklamalar

Belgedeki ilk OLE öğesiyle başlayarak, her öğeye `OnUpdateEditLinksMenu` erişir, öğenin bir bağlantı olup olmadığını sınar ve bağlantı varsa, Bağlantılar komutunu sağlar. Davranışı değiştirmek için bu işlevi geçersiz kılın.

##  <a name="onupdateobjectverbmenu"></a>Cotadocument:: OnUpdateObjectVerbMenu

Düzenleme menüsünde *ObjectName* komutunu ve ObjectName komutundan erişilen fiil alt menüsünü güncelleştirmek için Framework tarafından çağırılır; burada *NesneAdı* , belgeye katıştırılmış OLE nesnesinin adıdır.

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Update komutunu oluşturan menüyü `CCmdUI` temsil eden bir yapıya yönelik işaretçi. Güncelleştirme işleyicisi, Kullanıcı arabirimini `Enable` güncelleştirmek için *pCmdUI* aracılığıyla `CCmdUI` yapının üye işlevini çağırır.

### <a name="remarks"></a>Açıklamalar

`OnUpdateObjectVerbMenu`*ObjectName* komutunun Kullanıcı arabirimini, belgede geçerli bir nesne olup olmadığına bağlı olarak güncelleştirir. Bir nesne varsa, Düzenle menüsünde *ObjectName* komutu etkinleştirilir. Bu menü komutu seçildiğinde, fiil alt menüsü görüntülenir. Fiil alt menüsü, nesne için kullanılabilen, düzenleme, özellikler gibi tüm fiil komutlarını içerir. Davranışı değiştirmek için bu işlevi geçersiz kılın.

##  <a name="onupdatepastelinkmenu"></a>Cotadocument:: OnUpdatePasteLinkMenu

Bağlantılı bir OLE öğesinin panodan yapıştırılamayacağını anlamak için Framework tarafından çağırılır.

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Update komutunu oluşturan menüyü `CCmdUI` temsil eden bir yapıya yönelik işaretçi. Güncelleştirme işleyicisi, Kullanıcı arabirimini `Enable` güncelleştirmek için *pCmdUI* aracılığıyla `CCmdUI` yapının üye işlevini çağırır.

### <a name="remarks"></a>Açıklamalar

Özel Yapıştır menü komutu etkin veya öğenin belgeye yapıştırılabilse veya devre dışı bırakıldığına bağlı olarak devre dışıdır.

##  <a name="onupdatepastemenu"></a>Cotadocument:: OnUpdatePasteMenu

Katıştırılmış OLE öğesinin panodan yapıştırılamayacağını anlamak için Framework tarafından çağırılır.

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Update komutunu oluşturan menüyü `CCmdUI` temsil eden bir yapıya yönelik işaretçi. Güncelleştirme işleyicisi, Kullanıcı arabirimini `Enable` güncelleştirmek için *pCmdUI* aracılığıyla `CCmdUI` yapının üye işlevini çağırır.

### <a name="remarks"></a>Açıklamalar

Yapıştırma menü komutu ve düğmesi, öğenin belgeye yapıştırılamayacağı veya bu öğeye bağlı olarak etkin veya devre dışı bırakılmış.

##  <a name="removeitem"></a>Cotadocument:: RemoveItem

Belgeden bir öğeyi kaldırmak için bu işlevi çağırın.

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Kaldırılacak belge öğesine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Genellikle bu işlevi açıkça çağırmanız gerekmez; `COleClientItem` ve`COleServerItem`için Yıkıcılar tarafından çağırılır.

##  <a name="updatemodifiedflag"></a>Cotadocument:: UpdateModifiedFlag

İçerilen OLE öğelerinden herhangi biri değiştirilmişse belgeyi değiştirilmiş olarak işaretlemek için bu işlevi çağırın.

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>Açıklamalar

Bu, belgedeki yerel veriler değiştirilmemiş olsa bile, çerçevenin kapatmadan önce kullanıcının belgeyi kaydetmesine izin verir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek KAPSAYıCıSı](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[CDocument Sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
