---
title: COleDocument sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95c528ca21d0f458fe67908322ac622ad26e55e0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077510"
---
# <a name="coledocument-class"></a>COleDocument sınıfı

Görsel düzenlemeyi destekleyen OLE belgeleri için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class COleDocument : public CDocument
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDocument::COleDocument](#coledocument)|Oluşturur bir `COleDocument` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDocument::AddItem](#additem)|Belge tarafından tutulan öğeler listesine bir öğe ekler.|
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|Belge yazdırma hedef cihaz için tüm istemci öğeleri ayarlar.|
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|OLE yapılı depolama dosya biçimi kullanılarak depolanması belgeleri neden olur.|
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|Şu anda yerinde etkin OLE öğesini döndürür.|
|[COleDocument::GetNextClientItem](#getnextclientitem)|Yineleme için bir sonraki istemci öğeyi alır.|
|[COleDocument::GetNextItem](#getnextitem)|Sonraki belge öğesi yineleme için alır.|
|[COleDocument::GetNextServerItem](#getnextserveritem)|Yineleme için sonraki sunucu öğesi alır.|
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|Belgede birincil seçili OLE öğesini döndürür.|
|[COleDocument::GetStartPosition](#getstartposition)|Yineleme başlamak için ilk konumunu alır.|
|[COleDocument::HasBlankItems](#hasblankitems)|Belgedeki boş öğeleri denetler.|
|[COleDocument::OnShowViews](#onshowviews)|Belgenin görünür veya gizli çağırılır.|
|[COleDocument::RemoveItem](#removeitem)|Belge tarafından korunan öğe listesinden bir öğeyi kaldırır.|
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|Belge kapsanan OLE öğeleri değiştirilmişse, değiştirilmiş olarak işaretler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|Simge menü komutunu olayları işler.|
|[COleDocument::OnEditConvert](#oneditconvert)|Gömülü veya bağlantılı bir nesnenin bir türden diğerine dönüştürme diğerine işler.|
|[COleDocument::OnEditLinks](#oneditlinks)|Düzen menüsündeki bağlantılar olayları işler.|
|[COleDocument::OnFileSendMail](#onfilesendmail)|Belge iliştirilmiş bir posta iletisi gönderir.|
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|' % S'komutu kullanıcı Arabirimi düzenleme/Change Icon menü seçeneği için güncelleştirmek için framework tarafından çağırılır.|
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|' % S'komutu kullanıcı Arabirimi düzenleme/bağlantıları menü seçeneği için güncelleştirmek için framework tarafından çağırılır.|
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Düzenleme için kullanıcı Arabirimi komut güncelleştirmek için framework tarafından çağırılır / *ObjectName* menü seçeneği ve Düzenle ' erişilen fiili alt / *ObjectName*.|
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|' % S'komutu kullanıcı Arabirimi Özel Yapıştır menü seçeneği için güncelleştirmek için framework tarafından çağırılır.|
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|' % S'komutu kullanıcı Arabirimi Yapıştır menü seçeneği için güncelleştirmek için framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

`COleDocument` türetilen `CDocument`, OLE uygulamalarınızı Microsoft Foundation Class Kitaplığı tarafından sağlanan belge/görünüm mimarisini kullanan sağlar.

`COleDocument` bir belge koleksiyonu olarak davranır [Cdocıtem](../../mfc/reference/cdocitem-class.md) OLE öğelerini işlemek için nesneler. Belgelerinin OLE öğeleri içermesi gerektiğinden bu tür bir mimari hem kapsayıcı hem de sunucu uygulamalarına gerektirir. [Coleserverıtem](../../mfc/reference/coleserveritem-class.md) ve [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) sınıflarından türetilen her ikisi de `CDocItem`, uygulamalar ve OLE öğeleri arasındaki etkileşimler yönetin.

Basit kapsayıcılı bir uygulama yazıyorsanız, belge sınıfından türetilir `COleDocument`. Kendi belgeleri tarafından bulunan katıştırılmış öğelere bağlamayı destekleyen bir kapsayıcı uygulaması yazıyorsanız, belge sınıfından türetilir [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md). Bir sunucu uygulaması veya birleşim kapsayıcı/sunucu yazıyorsanız, belge sınıfından türetilir [COleServerDoc](../../mfc/reference/coleserverdoc-class.md). `COleLinkingDoc` ve `COleServerDoc` türetilmiştir `COleDocument`, kullanılabilen tüm hizmetler bu sınıfları devral `COleDocument` ve `CDocument`.

Kullanılacak `COleDocument`, bir sınıf türetmeniz ve uygulamanın OLE olmayan verilerin yanı sıra gömülü veya bağlantılı öğeleri yönetmek için işlevsellik ekler. Tanımlarsanız `CDocItem`-türetilmiş sınıflar uygulamanın yerel verileri depolamak için kullanabileceğiniz tarafından tanımlanan varsayılan uygulama `COleDocument` OLE ve OLE dışı verileri depolamak için. OLE dışı verilerinizden ayrı olarak OLE öğeleri depolamak için kendi veri yapıları da tasarlayabilirsiniz. Daha fazla bilgi için bkz [kapsayıcılar: bileşik dosyalar](../../mfc/containers-compound-files.md)...

`CDocument` e-posta desteği (MAPI) varsa, belgenizi e-posta yoluyla göndermeyi destekler. `COleDocument` güncelleştirilmiş [OnFileSendMail](#onfilesendmail) bileşik belgeler doğru bir şekilde işlemek için. Daha fazla bilgi için makalelere bakın [MAPI](../../mfc/mapi.md) ve [MFC'de MAPI desteği](../../mfc/mapi-support-in-mfc.md)...

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`COleDocument`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="additem"></a>  COleDocument::AddItem

Belgeye bir öğe eklemek için bu işlevi çağırın.

```
virtual void AddItem(CDocItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Eklenen belge öğesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, açıkça adlandırılır aramanızı gerekmez `COleClientItem` veya `COleServerItem` belgeye bir işaretçiyi kabul eden Oluşturucu.

##  <a name="applyprintdevice"></a>  COleDocument::ApplyPrintDevice

Tüm katıştırılmış yazdırma hedef cihazı değiştirmek için bu işlevi çağırın [Coleclientıtem](../../mfc/reference/coleclientitem-class.md) uygulamanızın kapsayıcı belgedeki öğeler.

```
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```

### <a name="parameters"></a>Parametreler

*ptd*<br/>
İşaretçi bir `DVTARGETDEVICE` yeni yazdırma hedef cihaz hakkındaki bilgileri içeren veri yapısı. NULL olabilir.

*PPD*<br/>
İşaretçi bir `PRINTDLG` yeni yazdırma hedef cihaz hakkındaki bilgileri içeren veri yapısı. NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev tüm öğeler için Hedefi Yazdır cihaz güncelleştirir, ancak bu öğeler için sunu önbellek yenilemez. Bir öğe için sunu önbelleği güncelleştirmek için çağrı [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink).

Bu işlev bağımsız değişkenleri OLE hedef cihazı tanımlamak için kullandığı bilgileri içerir. [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) yapısı Windows ortak Yazdır iletişim kutusunu başlatmak için kullandığı bilgileri içerir. Kullanıcı iletişim kutusu kapatıldıktan sonra Windows bu yapıda kullanıcının seçimler hakkındaki bilgileri döndürür. `m_pd` Üyesi bir [CPrintDialog](../../mfc/reference/cprintdialog-class.md) nesnesi bir `PRINTDLG` yapısı.

Daha fazla bilgi için [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) Windows SDK'sındaki yapısı.

Daha fazla bilgi için [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) Windows SDK'sındaki yapısı.

##  <a name="coledocument"></a>  COleDocument::COleDocument

Oluşturur bir `COleDocument` nesne.

```
COleDocument();
```

##  <a name="enablecompoundfile"></a>  COleDocument::EnableCompoundFile

Bileşik dosya biçimini kullanarak belge depolamak istiyorsanız bu işlevi çağırın.

```
void EnableCompoundFile(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
Bileşik dosya desteği etkin mi yoksa devre dışı mı olduğunu belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yapılandırılmış depolama olarak da adlandırılır. Genellikle oluşturucusunda bu işlevi çağırın, `COleDocument`-türetilmiş sınıf. Bileşik belgeler hakkında daha fazla bilgi için bkz [kapsayıcılar: bileşik dosyalar](../../mfc/containers-compound-files.md)...

Bu üye işlevini çağırmayın, belgeleri şeylerle ("Düz") dosya biçiminde depolanır.

Bileşik dosya desteği etkin veya devre dışı bir belge için sonra belgenin ömrü boyunca ayarı değiştirilmemelidir.

##  <a name="getinplaceactiveitem"></a>  COleDocument::GetInPlaceActiveItem

OLE almak için bu işlevi öğesi çağrı yerinde çerçeve penceresi tarafından tanımlanan görünüm şu anda etkinleştirilirse *pWnd*.

```
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Görüntüler kapsayıcı belge penceresi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Tek ve yerinde active OLE öğesini bir işaretçi; Yoksa hiçbir OLE öğesini şu anda "yerinde etkin" durumda NULL.

##  <a name="getnextclientitem"></a>  COleDocument::GetNextClientItem

Belgenizde istemci öğelerin her biri sürekli olarak erişmek için bu işlevi çağırın.

```
COleClientItem* GetNextClientItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından bir konuma başvuru değerinin ayarlanmış `GetNextClientItem`; tarafından döndürülen ilk değer `GetStartPosition` üye işlevi.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki istemci işaretçiye belgedeki öğe ya da daha fazla istemci öğe yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Her çağrının değerini sonra *pos* olabilir veya bir istemci öğesi olmayabilir belge içinde sonraki öğe için ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#1](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]

##  <a name="getnextitem"></a>  COleDocument::GetNextItem

Belgenizde öğelerin her biri sürekli olarak erişmek için bu işlevi çağırın.

```
virtual CDocItem* GetNextItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından bir konuma başvuru değerinin ayarlanmış `GetNextItem`; tarafından döndürülen ilk değer `GetStartPosition` üye işlevi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konumda bir belge öğesinin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Her çağrının değerini sonra *pos* belge içinde sonraki öğenin KONUMUNU değerine ayarlanır. Alınan öğenin yeni değeri belgenin içindeki son öğeden ise *pos* null.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#2](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]

##  <a name="getnextserveritem"></a>  COleDocument::GetNextServerItem

Belgenizde sunucu öğelerin her biri sürekli olarak erişmek için bu işlevi çağırın.

```
COleServerItem* GetNextServerItem(POSITION& pos) const;
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından bir konuma başvuru değerinin ayarlanmış `GetNextServerItem`; tarafından döndürülen ilk değer `GetStartPosition` üye işlevi.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki sunucuyu işaretçiye belgedeki öğe ya da daha fazla sunucu öğe yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Her çağrının değerini sonra *pos* olabilir veya bir sunucu öğesi olmayabilir belge içinde sonraki öğe için ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleServer#2](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]

##  <a name="getprimaryselecteditem"></a>  COleDocument::GetPrimarySelectedItem

Belirtilen görünümünde seçili OLE öğesini almak için framework tarafından çağırılır.

```
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```

### <a name="parameters"></a>Parametreler

*pView*<br/>
Belge görüntüleme etkin nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Seçili OLE öğesini tek bir işaretçi; NULL OLE hiçbir öğe seçili değilse veya birden fazla ise seçilir.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, içerdiği OLE listesini tek bir seçili öğe için öğeleri arar ve bir işaretçi döndürür. Seçili öğe varsa veya birden fazla öğe seçili ise, işlev NULL döndürür. Geçersiz kılmanız gerekir `CView::IsSelected` görünümü sınıfınızdaki çalışmak için bu işlevi için üye işlevi. Kapsanan OLE öğeleri saklama kendi yöntemi varsa, bu işlev geçersiz kılar.

##  <a name="getstartposition"></a>  COleDocument::GetStartPosition

Belgedeki ilk öğenin konumunu almak için bu işlevi çağırın.

```
virtual POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin öğeler arasında yineleme başlatmak için kullanılan konum değeri; Belge hiç öğe yoksa null değeri.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer geçirmek `GetNextItem`, `GetNextClientItem`, veya `GetNextServerItem`.

##  <a name="hasblankitems"></a>  COleDocument::HasBlankItems

Belge boş öğeleri içerip içermediğini belirlemek için bu işlevi çağırın.

```
BOOL HasBlankItems() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belge boş öğeler içeriyorsa, sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Boş bir öğesi olan dikdörtgen boştur biridir.

##  <a name="oneditchangeicon"></a>  COleDocument::OnEditChangeIcon

OLE Change Icon iletişim kutusu görüntüler ve iletişim kutusunda kullanıcının seçtiği simgesi seçili OLE öğesini temsil eden simgeyi değiştirir.

```
afx_msg void OnEditChangeIcon();
```

### <a name="remarks"></a>Açıklamalar

`OnEditChangeIcon` oluşturan ve başlatan bir `COleChangeIconDialog` Change Icon iletişim kutusu.

##  <a name="oneditconvert"></a>  COleDocument::OnEditConvert

OLE Dönüştür iletişim kutusu görüntüler, dönüştürür ve iletişim kutusunda kullanıcı seçimlerine göre şu anda seçili OLE öğesini etkinleştirir.

```
afx_msg void OnEditConvert();
```

### <a name="remarks"></a>Açıklamalar

`OnEditConvert` oluşturan ve başlatan bir `COleConvertDialog` Dönüştür iletişim kutusu.

Dönüştürme örneği, bir Microsoft Word belgesi WordPad belgesine dönüştürüyor.

##  <a name="oneditlinks"></a>  COleDocument::OnEditLinks

OLE Edit/Links iletişim kutusu görüntüler.

```
afx_msg void OnEditLinks();
```

### <a name="remarks"></a>Açıklamalar

`OnEditLinks` oluşturan ve başlatan bir `COleLinksDialog` bağlantılı nesneleri değiştirmesine izin veren Links iletişim kutusu.

##  <a name="onfilesendmail"></a>  COleDocument::OnFileSendMail

Yerleşik posta ana bilgisayar üzerinden bir ileti ile belge (varsa) ek olarak gönderir.

```
afx_msg void OnFileSendMail();
```

### <a name="remarks"></a>Açıklamalar

`OnFileSendMail` çağrıları `OnSaveDocument` (Kaydet) adsız ve değiştirilen belgeler elektronik posta gönderilmesi geçici bir dosyaya serileştirmek için. Belge değiştirilmemiş, geçici bir dosya gerekli değildir; özgün gönderilir. `OnFileSendMail` MAPI32 yükler. DLL zaten yüklü.

Uygulamasını aksine `OnFileSendMail` için `CDocument`, bu işlev bileşik dosyalar doğru şekilde işler.

Daha fazla bilgi için [MAPI konuları](../../mfc/mapi.md) ve [MFC'de MAPI desteği](../../mfc/mapi-support-in-mfc.md) makaleleri...

##  <a name="onshowviews"></a>  COleDocument::OnShowViews

Framework, durum değişikliklerini belgenin görünürlük sonra bu işlevi çağırır.

```
virtual void OnShowViews(BOOL bVisible);
```

### <a name="parameters"></a>Parametreler

*bVisible*<br/>
Belgenin görünür veya gizli haline gelmiştir gösterir.

### <a name="remarks"></a>Açıklamalar

Bu işlev varsayılan sürümü hiçbir şey yapmaz. Uygulamanızı belgenin görünürlüğü değiştiğinde özel bir işlem gerçekleştirmeniz gerekirse geçersiz kılar.

##  <a name="onupdateeditchangeicon"></a>  COleDocument::OnUpdateEditChangeIcon

Düzen menüsündeki simge güncelleştirmek için framework tarafından çağırılır.

```
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Bir işaretçi bir `CCmdUI` güncelleştirme komut oluşturulan menü temsil eden yapısı. Güncelleştirme işleyicisi çağrılarını `Enable` üye işlevinin `CCmdUI` aracılığıyla yapısı *pCmdUI* kullanıcı arabirimini güncelleştirmek için.

### <a name="remarks"></a>Açıklamalar

`OnUpdateEditChangeIcon` komutun kullanıcı arabirimi olup olmadığını belge içinde geçerli bir simge var. bağlı olarak güncelleştirir. Bu işlevin davranışını değiştirmek için geçersiz kılın.

##  <a name="onupdateeditlinksmenu"></a>  COleDocument::OnUpdateEditLinksMenu

Düzen menüsündeki bağlantılar güncelleştirmek için framework tarafından çağırılır.

```
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Bir işaretçi bir `CCmdUI` güncelleştirme komut oluşturulan menü temsil eden yapısı. Güncelleştirme işleyicisi çağrılarını `Enable` üye işlevinin `CCmdUI` aracılığıyla yapısı *pCmdUI* kullanıcı arabirimini güncelleştirmek için.

### <a name="remarks"></a>Açıklamalar

Belge ilk OLE öğesinde başlayarak `OnUpdateEditLinksMenu` erişen her bir öğe, öğe bir bağlantıdır ve bir bağlantı olması durumunda bağlantılar komutu sağlar olup olmadığını test eder. Bu işlevin davranışını değiştirmek için geçersiz kılın.

##  <a name="onupdateobjectverbmenu"></a>  COleDocument::OnUpdateObjectVerbMenu

Güncelleştirmek için framework tarafından çağırılır *ObjectName* Düzenle menüsü ve erişilen fiili alt menü komutunu *ObjectName* komutu, burada *ObjectName* adıdır belgeye katıştırılmış OLE nesne.

```
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Bir işaretçi bir `CCmdUI` güncelleştirme komut oluşturulan menü temsil eden yapısı. Güncelleştirme işleyicisi çağrılarını `Enable` üye işlevinin `CCmdUI` aracılığıyla yapısı *pCmdUI* kullanıcı arabirimini güncelleştirmek için.

### <a name="remarks"></a>Açıklamalar

`OnUpdateObjectVerbMenu` güncelleştirmeleri *ObjectName* olup olmadığını belge içinde geçerli bir nesne var. bağlı olarak komut kullanıcı arabirimi. Bir nesne varsa, *ObjectName* etkin Düzen menüsündeki komutu. Bu menü komutu seçildiğinde, fiil alt görüntülenir. Fiili alt düzenleme özellikleri ve benzeri gibi bir nesne için kullanılabilen tüm fiil komutları içerir. Bu işlevin davranışını değiştirmek için geçersiz kılın.

##  <a name="onupdatepastelinkmenu"></a>  COleDocument::OnUpdatePasteLinkMenu

Bağlantılı bir OLE öğe panodan yapıştırılan olup olmadığını belirlemek için framework tarafından çağırılır.

```
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Bir işaretçi bir `CCmdUI` güncelleştirme komut oluşturulan menü temsil eden yapısı. Güncelleştirme işleyicisi çağrılarını `Enable` üye işlevinin `CCmdUI` aracılığıyla yapısı *pCmdUI* kullanıcı arabirimini güncelleştirmek için.

### <a name="remarks"></a>Açıklamalar

Özel Yapıştır menü komutunu etkin veya devre dışı olup olmadığını öğesi belgeye veya yapıştırılabilir bağlı olarak.

##  <a name="onupdatepastemenu"></a>  COleDocument::OnUpdatePasteMenu

Katıştırılmış OLE öğesini panodan yapıştırılan olup olmadığını belirlemek için framework tarafından çağırılır.

```
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Parametreler

*pCmdUI*<br/>
Bir işaretçi bir `CCmdUI` güncelleştirme komut oluşturulan menü temsil eden yapısı. Güncelleştirme işleyicisi çağrılarını `Enable` üye işlevinin `CCmdUI` aracılığıyla yapısı *pCmdUI* kullanıcı arabirimini güncelleştirmek için.

### <a name="remarks"></a>Açıklamalar

Yapıştır menü komutu ve düğmesi etkin veya devre dışı olup olmadığını öğesi belgeye veya yapıştırılabilir bağlı olarak.

##  <a name="removeitem"></a>  COleDocument::RemoveItem

Belgeden bir öğe kaldırmak için bu işlevi çağırın.

```
virtual void RemoveItem(CDocItem* pItem);
```

### <a name="parameters"></a>Parametreler

*pItem*<br/>
Kaldırılacak bir belge öğesinin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Genellikle bu işlevi açıkça çağırmanız gerekmez; yok ediciler için tarafından adlandırılan `COleClientItem` ve `COleServerItem`.

##  <a name="updatemodifiedflag"></a>  COleDocument::UpdateModifiedFlag

Belge kapsanan OLE öğeleri değiştirilmişse, değiştirilmiş olarak işaretlemek için bu işlevi çağırın.

```
virtual void UpdateModifiedFlag();
```

### <a name="remarks"></a>Açıklamalar

Bu belgedeki yerel veri değiştirilmemiş olsa bile belge kapatmadan önce kaydetmek için kullanıcıdan istemek çerçeve sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek KAPSAYICI](../../visual-cpp-samples.md)<br/>
[MFC örnek MFCBIND](../../visual-cpp-samples.md)<br/>
[CDocument Sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

