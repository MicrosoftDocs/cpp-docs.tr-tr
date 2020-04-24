---
title: COleDocument Sınıfı
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
ms.openlocfilehash: 1500035cb8be3036678090918154829aace48d2f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753867"
---
# <a name="coledocument-class"></a>COleDocument Sınıfı

Görsel düzenlemeyi destekleyen OLE belgelerinin taban sınıfı.

## <a name="syntax"></a>Sözdizimi

```
class COleDocument : public CDocument
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleDocument::COleDocument](#coledocument)|Bir `COleDocument` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDocument::AddItem](#additem)|Belge tarafından tutulan öğeler listesine bir öğe ekler.|
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|Belgedeki tüm istemci öğeleri için yazdırma hedef aygıtını ayarlar.|
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|Belgelerin OLE Yapılandırılmış Depolama dosya biçimini kullanarak depolanmasına neden olur.|
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|Şu anda etkin olan OLE öğesini döndürür.|
|[COleDocument::GetNextClientItem](#getnextclientitem)|Bir sonraki istemci öğesini yineleiçin alır.|
|[COleDocument::GetNextItem](#getnextitem)|Bir sonraki belge öğesini yinelemek için alır.|
|[COleDocument::GetNextServerItem](#getnextserveritem)|Bir sonraki sunucu öğesini yineleiçin alır.|
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|Belgedeki birincil seçili OLE öğesini döndürür.|
|[COleDocument::GetStartPosition](#getstartposition)|Yinelemeye başlamak için ilk konumu alır.|
|[COleDocument::HasBlankItems](#hasblankitems)|Belgedeki boş öğeleri denetler.|
|[COleDocument::OnShowViews](#onshowviews)|Belge görünür veya görünmez olduğunda çağrılır.|
|[COleDocument::RemoveItem](#removeitem)|Bir öğeyi belge tarafından tutulan öğeler listesinden kaldırır.|
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|İçerdiği OLE öğelerinden herhangi biri değiştirilmişse belgeyi değiştirilmiş olarak işaretler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|Simgeyi Değiştir menüsündeki olayları işler.|
|[COleDocument::OnEditConvert](#oneditconvert)|Katıştılı veya bağlantılı bir nesnenin bir türden diğerine dönüştürülmesini işler.|
|[COleDocument::OnEditLinks](#oneditlinks)|Edit menüsündeki Bağlantılar komutundaki olayları işler.|
|[COleDocument::OnFileSendMail](#onfilesendmail)|Belge eklenmiş bir posta iletisi gönderir.|
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|Düzenleme/Değiştir Simgesi menüsü için komut UI'sini güncelleştirmek için çerçeve tarafından çağrılır.|
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|Düzenleme/Bağlantılar menüsü seçeneği için komut UI'yi güncelleştirmek için çerçeve tarafından çağrılır.|
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Düzenleme/ *ObjectName* menüsü seçeneği ve Edit/ *ObjectName'den*erişilen Fiil alt menüsü için komut UI'yi güncelleştirmek için çerçeve tarafından çağrıldı.|
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|Yapıştır Özel menü seçeneği için komut UI'yi güncelleştirmek için çerçeve tarafından çağrılır.|
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|Yapıştır menüsü seçeneği için komut UI'yi güncelleştirmek için çerçeve tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

`COleDocument`OLE `CDocument`uygulamalarınızın Microsoft Hazırlık Sınıfı Kitaplığı tarafından sağlanan belge/görünüm mimarisini kullanmasına olanak tanıyan türetilmiştir.

`COleDocument`bir belgeyi, OLE öğelerini işlemek için [CDocItem](../../mfc/reference/cdocitem-class.md) nesnelerinin bir koleksiyonu olarak ele alır. Hem kapsayıcı hem de sunucu uygulamaları, belgeleri OLE öğelerini içerebilmesi gerektiğinden, böyle bir mimari gerektirir. [COleServerItem](../../mfc/reference/coleserveritem-class.md) ve [COleClientItem](../../mfc/reference/coleclientitem-class.md) sınıfları, `CDocItem`her ikisi de türetilen, uygulamalar ve OLE öğeleri arasındaki etkileşimleri yönetmek.

Basit bir kapsayıcı uygulaması yazıyorsanız, belge sınıfınızı `COleDocument`. Belgelerinin içerdiği katıştırılmış öğelere bağlanmayı destekleyen bir kapsayıcı uygulaması yazıyorsanız, belge sınıfınızı [COleLinkingDoc'tan](../../mfc/reference/colelinkingdoc-class.md)türetin. Bir sunucu uygulaması veya karma kapsayıcı/sunucu yazıyorsanız, belge sınıfınızı [COleServerDoc'tan](../../mfc/reference/coleserverdoc-class.md)türetin. `COleLinkingDoc`ve `COleServerDoc` `COleDocument`türetilmiştir, bu nedenle bu sınıflar `COleDocument` `CDocument`mevcut tüm hizmetleri devralır ve .

Kullanmak `COleDocument`için, ondan bir sınıf türetmek ve uygulamanın OLE olmayan verilerinyanı sıra gömülü veya bağlantılı öğeleri yönetmek için işlevsellik ekleyin. Uygulamanın `CDocItem`yerel verilerini depolamak için türetilmiş sınıfları tanımlarsanız, `COleDocument` hem OLE hem de OLE olmayan verilerinizi depolamak için tanımlanan varsayılan uygulamayı kullanabilirsiniz. Ayrıca, OLE olmayan verilerinizi OLE öğelerinden ayrı olarak depolamak için kendi veri yapılarınızı da tasarlayabilirsiniz. Daha fazla bilgi için, makale [Kapsayıcılar bakın: Bileşik Dosyalar](../../mfc/containers-compound-files.md)...

`CDocument`posta desteği (MAPI) varsa belgenizi posta yoluyla göndermeyi destekler. `COleDocument`bileşik belgeleri doğru işlemek için [OnFileSendMail'i](#onfilesendmail) güncelleştirmiştir. Daha fazla bilgi için [MapI](../../mfc/mapi.md) ve [MAPI Desteği makalelerini MFC'de](../../mfc/mapi-support-in-mfc.md)görebilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cdocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="coledocumentadditem"></a><a name="additem"></a>COleDocument::AddItem

Belgeye öğe eklemek için bu işlevi çağırın.

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Eklenen belge öğesiiçin işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir belgeiçin işaretçi kabul eden `COleClientItem` veya `COleServerItem` oluşturucu tarafından çağrıldığında bu işlevi açıkça çağırmanız gerekmez.

## <a name="coledocumentapplyprintdevice"></a><a name="applyprintdevice"></a>COleDocument::ApplyPrintDevice

Uygulamanızın kapsayıcı belgesinde gömülü tüm [COleClientItem](../../mfc/reference/coleclientitem-class.md) öğeleriiçin yazdırma hedef aygıtını değiştirmek için bu işlevi arayın.

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>Parametreler

*ptd*<br/>
Yeni yazdırma `DVTARGETDEVICE` hedef aygıtı hakkında bilgi içeren bir veri yapısıişaretçisi. NULL olabilir.

*Ppd*<br/>
Yeni yazdırma `PRINTDLG` hedef aygıtı hakkında bilgi içeren bir veri yapısıişaretçisi. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm öğeler için yazdırma hedef aygıtını güncelleştirir, ancak bu öğeler için sunu önbelleğini yenilemez. Bir öğenin sunu önbelleğini güncelleştirmek için [COleClientItem'i arayın:UpdateLink.](../../mfc/reference/coleclientitem-class.md#updatelink)

Bu işlevin bağımsız değişkenleri, OLE'nin hedef aygıtı tanımlamak için kullandığı bilgileri içerir. [PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) yapısı, Windows'un ortak Yazdırma iletişim kutusunu başlatmada kullandığı bilgileri içerir. Kullanıcı iletişim kutusunu kapattıktan sonra, Windows bu yapıdaki kullanıcı seçimleri hakkında bilgi verir. [CPrintDialog](../../mfc/reference/cprintdialog-class.md) nesnesinin `m_pd` üyesi bir `PRINTDLG` yapıdır.

Daha fazla bilgi için Windows [SDK'daki PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga) yapısına bakın.

Daha fazla bilgi için Windows SDK'daki [DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) yapısına bakın.

## <a name="coledocumentcoledocument"></a><a name="coledocument"></a>COleDocument::COleDocument

Bir `COleDocument` nesne inşa eder.

```
COleDocument();
```

## <a name="coledocumentenablecompoundfile"></a><a name="enablecompoundfile"></a>COleDocument::EnableCompoundFile

Bileşik dosya biçimini kullanarak belgeyi depolamak istiyorsanız bu işlevi arayın.

```cpp
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
Bileşik dosya desteğinin etkin veya devre dışı bırakıldığını belirtir.

### <a name="remarks"></a>Açıklamalar

Buna yapılandırılmış depolama da denir. Bu işlevi genellikle türetilmiş sınıfınızın `COleDocument`oluşturucusundan çağırırsınız. Bileşik belgeler hakkında daha fazla bilgi için, makale [Kapsayıcılar bakın: Bileşik Dosyalar](../../mfc/containers-compound-files.md)...

Bu üye işlevini çağırmazsanız, belgeler yapılandırılmamış ("düz") dosya biçiminde depolanır.

Bileşik dosya desteği etkinleştirildikten veya belge için devre dışı bırakıldıktan sonra, ayar belgenin ömrü boyunca değiştirilmemelidir.

## <a name="coledocumentgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>COleDocument::GetInPlaceActiveItem

*PWnd*tarafından tanımlanan görünümü içeren çerçeve penceresinde şu anda etkinleştirilmiş Olan OLE öğesini almak için bu işlevi arayın.

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Kapsayıcı belgesini görüntüleyen pencereyi işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Tek, yerinde etkin OLE öğesiiçin bir işaretçi; NULL şu anda "yerinde etkin" durumunda ole öğesi yoksa.

## <a name="coledocumentgetnextclientitem"></a><a name="getnextclientitem"></a>COleDocument::GetNextClientItem

Belgenizdeki istemci öğelerin her birine erişmek için bu işlevi tekrar tekrar arayın.

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Bir önceki çağrı tarafından ayarlanan bir `GetNextClientItem`POSITION değerine başvuru; ilk değer `GetStartPosition` üye işlev tarafından döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Belgedeki bir sonraki istemci öğesine işaretçi veya başka istemci öğesi yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Her çağrıdan sonra, *pos* değeri belgedeki bir sonraki öğe için ayarlanır ve bu da istemci öğesi olabilir veya olmayabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

## <a name="coledocumentgetnextitem"></a><a name="getnextitem"></a>COleDocument::GetNextItem

Belgenizdeki öğelerin her birine erişmek için bu işlevi tekrar tekrar arayın.

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Bir önceki çağrı tarafından ayarlanan bir `GetNextItem`POSITION değerine başvuru; ilk değer `GetStartPosition` üye işlev tarafından döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konumda belge öğesiiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Her çağrıdan sonra *pos* değeri belgedeki bir sonraki öğenin KONUM değerine ayarlanır. Alınan öğe belgedeki son öğeyse, *pos'un* yeni değeri NULL'dur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

## <a name="coledocumentgetnextserveritem"></a><a name="getnextserveritem"></a>COleDocument::GetNextServerItem

Belgenizdeki sunucu öğelerinin her birine erişmek için bu işlevi tekrar tekrar arayın.

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Bir önceki çağrı tarafından ayarlanan bir `GetNextServerItem`POSITION değerine başvuru; ilk değer `GetStartPosition` üye işlev tarafından döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Belgede bir sonraki sunucu öğesiiçin bir işaretçi veya artık sunucu öğeleri varsa NULL.

### <a name="remarks"></a>Açıklamalar

Her *çağrıdan* sonra pos değeri, sunucu öğesi olabilir veya olmayabilir belgedeki bir sonraki öğe için ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

## <a name="coledocumentgetprimaryselecteditem"></a><a name="getprimaryselecteditem"></a>COleDocument::GetPrimarySelectedItem

Belirtilen görünümde şu anda seçili OLE öğesini almak için çerçeve tarafından çağrılır.

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>Parametreler

*pGörünüm*<br/>
Belgeyi görüntüleyen etkin görünüm nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Tek, seçili OLE öğesi için bir işaretçi; Null hiçbir OLE öğesi seçili değilse veya birden fazla seçiliyse.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, tek bir seçili öğe için bulunan OLE öğelerinin listesini arar ve işaretçisini döndürür. Seçili öğe yoksa veya birden fazla öğe seçiliyse, işlev NULL döndürür. Bu işlevin `CView::IsSelected` çalışması için görünüm sınıfınızdaki üye işlevi geçersiz kılmanız gerekir. İçerdiği OLE öğelerini depolamak için kendi yönteminiz varsa bu işlevi geçersiz kılın.

## <a name="coledocumentgetstartposition"></a><a name="getstartposition"></a>COleDocument::GetStartPosition

Belgedeki ilk öğenin konumunu almak için bu işlevi arayın.

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin öğeleri ni yeniden yapılandırılmaya başlamak için kullanılabilecek bir POSITION değeri; Belgede öğe yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Döndürülen değeri `GetNextItem`, `GetNextClientItem`veya `GetNextServerItem`.

## <a name="coledocumenthasblankitems"></a><a name="hasblankitems"></a>COleDocument::HasBlankItems

Belgenin boş öğeler bulunup içermediğini belirlemek için bu işlevi arayın.

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belge boş öğeler içeriyorsa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Boş bir öğe, dikdörtgeni boş olan öğedir.

## <a name="coledocumentoneditchangeicon"></a><a name="oneditchangeicon"></a>COleDocument::OnEditChangeIcon

OLE Değiştir Simgesi iletişim kutusunu görüntüler ve şu anda seçili OLE öğesini temsil eden simgeyi kullanıcının iletişim kutusunda seçtiği simgeyle değiştirir.

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>Açıklamalar

`OnEditChangeIcon`Bir `COleChangeIconDialog` Değişiklik Simgesi iletişim kutusu oluşturur ve başlatın.

## <a name="coledocumentoneditconvert"></a><a name="oneditconvert"></a>COleDocument::OnEditConvert

OLE Convert iletişim kutusunu görüntüler ve iletişim kutusundaki kullanıcı seçimlerine göre şu anda seçili OLE öğesini dönüştürür veya etkinleştirir.

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>Açıklamalar

`OnEditConvert`Dönüştür `COleConvertDialog` iletişim kutusu oluşturur ve başlatın.

Dönüşüm eki, Microsoft Word belgesini WordPad belgesine dönüştürmektir.

## <a name="coledocumentoneditlinks"></a><a name="oneditlinks"></a>COleDocument::OnEditLinks

OLE Edit/Links iletişim kutusunu görüntüler.

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>Açıklamalar

`OnEditLinks`kullanıcının bağlı nesneleri `COleLinksDialog` değiştirmesine olanak tanıyan bir Bağlantılar iletişim kutusu oluşturur ve başlatın.

## <a name="coledocumentonfilesendmail"></a><a name="onfilesendmail"></a>COleDocument::OnFileSendMail

Yerleşik posta ana bilgisayarı (varsa) üzerinden belgeek olarak ileti gönderir.

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>Açıklamalar

`OnFileSendMail`adsız ve değiştirilmiş belgeleri geçici bir dosyaya serihale (kaydetme) çağırır `OnSaveDocument` ve bu da elektronik posta yoluyla gönderilir. Belge değiştirilmemişse, geçici bir dosya gerekmez; orijinal gönderilir. `OnFileSendMail`MAPI32 yükler. DLL zaten yüklenmediyse.

for `CDocument`uygulamasının `OnFileSendMail` aksine, bu işlev bileşik dosyaları doğru işler.

Daha fazla bilgi için MFC makalelerinde [MAPI Konuları](../../mfc/mapi.md) ve [MAPI Desteği'ne](../../mfc/mapi-support-in-mfc.md) bakın...

## <a name="coledocumentonshowviews"></a><a name="onshowviews"></a>COleDocument::OnShowViews

Çerçeve, belgenin görünürlük durumu değiştikten sonra bu işlevi çağırır.

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>Parametreler

*bGörünür*<br/>
Belgenin görünür veya görünmez olup olmadığını gösterir.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan sürümü hiçbir şey yapmaz. Belgenin görünürlüğü değiştiğinde uygulamanızın herhangi bir özel işlem gerçekleştirmesi gerekiyorsa geçersiz kılın.

## <a name="coledocumentonupdateeditchangeicon"></a><a name="onupdateeditchangeicon"></a>COleDocument::OnUpdateEditChangeIcon

Düzenleme menüsündeki Simgeyi Değiştir komutunu güncelleştirmek için çerçeve tarafından çağrıldı.

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Güncelleştirme komutunu `CCmdUI` oluşturan menüyü temsil eden bir yapının işaretçisi. Güncelleştirme işleyicisi, kullanıcı `CCmdUI` arabirimini güncelleştirmek için *pCmdUI* aracılığıyla yapının `Enable` üye işlevini çağırır.

### <a name="remarks"></a>Açıklamalar

`OnUpdateEditChangeIcon`belgede geçerli bir simge olup olmadığına bağlı olarak komutun kullanıcı arabirimini güncelleştirir. Davranışı değiştirmek için bu işlevi geçersiz kılın.

## <a name="coledocumentonupdateeditlinksmenu"></a><a name="onupdateeditlinksmenu"></a>COleDocument::OnUpdateEditLinksMenu

Düzenleme menüsündeki Bağlantılar komutunu güncelleştirmek için çerçeve tarafından çağrıldı.

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Güncelleştirme komutunu `CCmdUI` oluşturan menüyü temsil eden bir yapının işaretçisi. Güncelleştirme işleyicisi, kullanıcı `CCmdUI` arabirimini güncelleştirmek için *pCmdUI* aracılığıyla yapının `Enable` üye işlevini çağırır.

### <a name="remarks"></a>Açıklamalar

Belgedeki ilk OLE öğesinden `OnUpdateEditLinksMenu` başlayarak, her öğeye erişir, öğenin bir bağlantı olup olmadığını sınar ve bağlantı ysa Bağlantılar komutunu etkinleştirir. Davranışı değiştirmek için bu işlevi geçersiz kılın.

## <a name="coledocumentonupdateobjectverbmenu"></a><a name="onupdateobjectverbmenu"></a>COleDocument::OnUpdateObjectVerbMenu

Düzenleme menüsündeki *ObjectName* komutunu ve ObjectName komutundan erişilen Fiil alt menüsünü güncelleştirmek için çerçeve tarafından çağrılan *ObjectName,* belgeye katıştırılmış OLE nesnesinin adıdır. *ObjectName*

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Güncelleştirme komutunu `CCmdUI` oluşturan menüyü temsil eden bir yapının işaretçisi. Güncelleştirme işleyicisi, kullanıcı `CCmdUI` arabirimini güncelleştirmek için *pCmdUI* aracılığıyla yapının `Enable` üye işlevini çağırır.

### <a name="remarks"></a>Açıklamalar

`OnUpdateObjectVerbMenu`Belgede geçerli bir nesnenin bulunup bulunmadığına bağlı olarak *ObjectName* komutunun kullanıcı arabirimini güncelleştirir. Bir nesne varsa, Edit menüsündeki *ObjectName* komutu etkinleştirilir. Bu menü komutu seçildiğinde Fiil alt menüsü görüntülenir. Fiil alt menüsü, nesne için Edit, Özellikler ve benzeri tüm fiil komutlarını içerir. Davranışı değiştirmek için bu işlevi geçersiz kılın.

## <a name="coledocumentonupdatepastelinkmenu"></a><a name="onupdatepastelinkmenu"></a>COleDocument::OnUpdatePasteLinkMenu

Bağlı bir OLE öğesinin Pano'dan yapıştırılıp yapıştırılamadığını belirlemek için çerçeve tarafından çağrılır.

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Güncelleştirme komutunu `CCmdUI` oluşturan menüyü temsil eden bir yapının işaretçisi. Güncelleştirme işleyicisi, kullanıcı `CCmdUI` arabirimini güncelleştirmek için *pCmdUI* aracılığıyla yapının `Enable` üye işlevini çağırır.

### <a name="remarks"></a>Açıklamalar

Özel Yapıştır menüsü komutu, öğenin belgeye yapıştırılıp yapıştırılmayacağına bağlı olarak etkin veya devre dışı bırakılır.

## <a name="coledocumentonupdatepastemenu"></a><a name="onupdatepastemenu"></a>COleDocument::OnUpdatePasteMenu

Katıştılı Bir OLE öğesinin Pano'dan yapıştırılıp yapıştırılamadığını belirlemek için çerçeve tarafından çağrılır.

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Güncelleştirme komutunu `CCmdUI` oluşturan menüyü temsil eden bir yapının işaretçisi. Güncelleştirme işleyicisi, kullanıcı `CCmdUI` arabirimini güncelleştirmek için *pCmdUI* aracılığıyla yapının `Enable` üye işlevini çağırır.

### <a name="remarks"></a>Açıklamalar

Öğenin belgeye yapıştırılıp yapıştırılamayacağına bağlı olarak Paste menü komutu ve düğmesi etkin veya devre dışı bırakılır.

## <a name="coledocumentremoveitem"></a><a name="removeitem"></a>COleDocument::RemoveItem

Bir öğeyi belgeden kaldırmak için bu işlevi çağırın.

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Kaldırılacak belge öğesiiçin işaretçi.

### <a name="remarks"></a>Açıklamalar

Genellikle bu işlevi açıkça aramanız gerekmez; bu için yıkıcılar tarafından denir `COleClientItem` ve `COleServerItem`.

## <a name="coledocumentupdatemodifiedflag"></a><a name="updatemodifiedflag"></a>COleDocument::UpdateModifiedFlag

İçerdiği OLE öğelerinden herhangi biri değiştirildiyse, belgeyi değiştirilmiş olarak işaretlemek için bu işlevi çağırın.

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>Açıklamalar

Bu, belgedeki yerel veriler değiştirilmemiş olsa bile, çerçevenin kullanıcıdan belgeyi kapatmadan önce kaydetmesini istemesine olanak tanır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek KONTEYNER](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[Kişniş Sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
