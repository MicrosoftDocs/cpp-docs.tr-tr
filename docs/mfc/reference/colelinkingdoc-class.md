---
title: COleLinkingDoc Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
helpviewer_keywords:
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
ms.openlocfilehash: 1fad986b7e7304075cacb0b5ced9feeb8af4664f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753844"
---
# <a name="colelinkingdoc-class"></a>COleLinkingDoc Sınıfı

İçerdikleri katıştırılmış öğelere bağlanmayı destekleyen OLE kapsayıcı belgelerinin taban sınıfı.

## <a name="syntax"></a>Sözdizimi

```
class COleLinkingDoc : public COleDocument
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|Bir `COleLinkingDoc` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleLinkingDoc::Kayıt](#register)|Belgeyi OLE sistemi DL'lerine kaydeder.|
|[COleLinkingDoc::İptal](#revoke)|Belgenin kaydını iptal eder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|Belirtilen katıştılmış öğeyi bulur.|
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|Belirtilen bağlantılı öğeyi bulur.|

## <a name="remarks"></a>Açıklamalar

Katıştırılmış öğelere bağlanmayı destekleyen bir kapsayıcı uygulamasına "bağlantı kapsayıcısı" adı verilir. [OCLIENT](../../overview/visual-cpp-samples.md) örnek uygulaması bir bağlantı kapsayıcısı örneğidir.

Bağlı bir öğenin kaynağı başka bir belgede katıştırılmış bir öğe olduğunda, katıştırılmış öğenin düzenlenebilmesi için belge içeren öğenin yüklenmesi gerekir. Bu nedenle, kullanıcı bağlı bir öğenin kaynağını düzenlemek istediğinde, bir bağlantı kapsayıcısı başka bir kapsayıcı uygulaması tarafından başlatılabilir. Uygulamanız, programlı olarak başlatıldığında belge oluşturabilmesi için [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) sınıfını da kullanmalıdır.

Kapsayıcınızı bir bağlantı kapsayıcısı yapmak için, `COleLinkingDoc` belge sınıfınızı [COleDocument](../../mfc/reference/coledocument-class.md)yerine türetin. Diğer OLE kapsayıcılarında olduğu gibi, uygulamanın yerel verilerinin yanı sıra gömülü veya bağlantılı öğeleri depolamak için sınıfınızı tasarlamanız gerekir. Ayrıca, yerel verilerinizi depolamak için veri yapıları tasarlamanız gerekir. Uygulamanızın yerel `CDocItem`verileri için türetilmiş bir sınıf tanımlarsanız, yerel `COleDocument` verilerinizi ve OLE verilerinizi depolamak için tanımlanan arabirimi kullanabilirsiniz.

Uygulamanızın başka bir kapsayıcı tarafından programlı olarak başlatılmasına izin vermek için, `COleTemplateServer` `CWinApp`bir nesneyi uygulamanızın türetilmiş sınıfının bir üyesi olarak bildirin:

[!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]

Türemiş `InitInstance` sınıfınızın `CWinApp`üye işlevinde bir belge şablonu oluşturun ve türetilmiş sınıfınızı `COleLinkingDoc`belge sınıfı olarak belirtin:

[!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]

Nesnenin `COleTemplateServer` `ConnectTemplate` üye işlevini çağırarak nesnenizi belge şablonlarınıza bağlayın ve tüm sınıf nesnelerini `COleTemplateServer::RegisterAll`OLE sistemine çağırarak kaydedin:

[!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]

Örnekten `CWinApp`türetilmiş sınıf `InitInstance` tanımı ve işlevi için Bkz. OCLIENT. H ve OCLIENT. MFC örnek [OCLIENT](../../overview/visual-cpp-samples.md)CPP .

Kullanma `COleLinkingDoc`hakkında daha fazla bilgi için, makaleler [Kapsayıcılar bakın: Bir Kapsayıcı](../../mfc/containers-implementing-a-container.md) ve [Kapsayıcılar Uygulama: Gelişmiş Özellikler](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cdocument](../../mfc/reference/cdocument-class.md)

[Coledocument](../../mfc/reference/coledocument-class.md)

`COleLinkingDoc`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="colelinkingdoccolelinkingdoc"></a><a name="colelinkingdoc"></a>COleLinkingDoc::COleLinkingDoc

OLE `COleLinkingDoc` sistemi DLs ile iletişim ilerler olmadan bir nesne inşa eder.

```
COleLinkingDoc();
```

### <a name="remarks"></a>Açıklamalar

OLE'ye `Register` belgenin açık olduğunu bildirmek için üye işlevi aramanız gerekir.

## <a name="colelinkingdoconfindembeddeditem"></a><a name="onfindembeddeditem"></a>COleLinkingDoc::OnFindEmbeddedItem

Belgenin belirtilen ada sahip katışımlı bir OLE öğesi bulunup bulunmadığını belirlemek için çerçeve tarafından çağrılır.

```
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
İstenilen katıştı OLE öğesinin adına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğeiçin bir işaretçi; Öğe bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, belirtilen ada sahip bir öğe için katıştırılmış öğelerin listesini arar (ad karşılaştırması büyük/küçük harf duyarlıdır). Katıştırılmış OLE öğelerini depolamak veya adlandırmak için kendi yönteminiz varsa bu işlevi geçersiz kılın.

## <a name="colelinkingdocongetlinkeditem"></a><a name="ongetlinkeditem"></a>COleLinkingDoc::OnGetLinkedItem

Belgenin belirtilen ada sahip bağlantılı bir sunucu öğesi bulunup bulunmadığını denetlemek için çerçeve tarafından çağrılır.

```
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
İstenen bağlantılı OLE öğesinin adını işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğeiçin bir işaretçi; Öğe bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan `COleLinkingDoc` uygulama her zaman NULL döndürür. Bu işlev, belirtilen ada `COleServerDoc` sahip bağlantılı bir öğe için OLE sunucu öğelerinin listesini aramak için türetilmiş sınıfta geçersiz kılınır (ad karşılaştırması büyük/küçük harf duyarlıdır). Bağlı sunucu öğelerini depolama veya alma yöntemini uyguladıysanız bu işlevi geçersiz kılın.

## <a name="colelinkingdocregister"></a><a name="register"></a>COleLinkingDoc::Kayıt

OLE sistemi DLLs'e belgenin açık olduğunu bildirir.

```
BOOL Register(
    COleObjectFactory* pFactory,
    LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*pFactory*<br/>
OLE fabrika nesnesine işaretçi (NULL olabilir).

*lpszPathName*<br/>
Kapsayıcı belgenin tam nitelikli yolunu işaretleyin.

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla kaydedilirse sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belgeyi OLE sistemi DL'lerine kaydetmek için adlandırılmış bir dosya oluştururken veya açarken bu işlevi arayın. Belge katıştırılmış bir öğeyi temsil ediyorsa, bu işlevi çağırmaya gerek yoktur.

Eğer `COleTemplateServer` `Register` uygulamakullanıyorsanız, sizin için 's `COleLinkingDoc`uygulaması tarafından `OnNewDocument` `OnOpenDocument`çağrılır , ve `OnSaveDocument`.

## <a name="colelinkingdocrevoke"></a><a name="revoke"></a>COleLinkingDoc::İptal

OLE sistemi DLLs'e belgenin artık açık olmadığını bildirir.

```cpp
void Revoke();
```

### <a name="remarks"></a>Açıklamalar

Belgenin OLE sistemi DL'lerine kaydını iptal etmek için bu işlevi arayın.

Adlandırılmış bir dosyayı kapatırken bu işlevi aramalısınız, ancak genellikle doğrudan aramanız gerekmez. `Revoke`sizin için '' uygulaması `COleLinkingDoc` `OnCloseDocument`ile `OnNewDocument` `OnOpenDocument`çağrılır , , ve `OnSaveDocument`.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDocument Sınıfı](../../mfc/reference/coledocument-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)
