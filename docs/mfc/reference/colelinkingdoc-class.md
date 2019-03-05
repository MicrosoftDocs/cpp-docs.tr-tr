---
title: COleLinkingDoc sınıfı
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
ms.openlocfilehash: 275119b2343c4d13b6a32f939fc8c3b2b5d5890c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57300417"
---
# <a name="colelinkingdoc-class"></a>COleLinkingDoc sınıfı

İçerdikleri katıştırılmış öğelere bağlamayı destekleyen OLE kapsayıcı belgeleri için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class COleLinkingDoc : public COleDocument
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|Oluşturur bir `COleLinkingDoc` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleLinkingDoc::Register](#register)|Belge OLE sistem DLL'lerini kaydeder.|
|[COleLinkingDoc::Revoke](#revoke)|Belgenin kaydı iptal eder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|Belirtilen gömülü bir öğe bulur.|
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|Belirtilen bağlantılı öğe bulur.|

## <a name="remarks"></a>Açıklamalar

Katıştırılmış öğelere bağlamayı destekleyen bir kapsayıcı uygulama "bağlantı kapsayıcı." adı verilir [OCLIENT](../../visual-cpp-samples.md) örnek uygulamanın bir bağlantı kapsayıcı örneği verilmiştir.

Bir bağlantılı öğenin kaynak başka bir belgede gömülü bir öğe olduğunda, gömülü öğenin düzenlenmesi sırayla içeren belge yüklenmesi gerekir. Bu nedenle, bir bağlantı kapsayıcı bir bağlantılı öğenin kaynağını düzenlemek kullanıcı istediği zaman başka bir kapsayıcı uygulama tarafından başlatılması mümkün olması gerekir. Uygulamanızı de kullanmanız gerekir [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) başlatıldığında program aracılığıyla belgeleri oluşturabilmesi sınıfı.

Kapsayıcı bağlantı kapsayıcı yapmak için belge sınıfından türetilen `COleLinkingDoc` yerine [COleDocument](../../mfc/reference/coledocument-class.md). Herhangi diğer OLE kapsayıcısı ile gibi uygulamanın yerel veri yanı sıra gömülü veya bağlantılı öğeleri depolamak için kendi sınıfınızı tasarlamanız gerekir. Ayrıca, yerel verilerinizi depolamak için veri yapıları tasarlamanız gerekir. Tanımlarsanız bir `CDocItem`-türetilmiş sınıf için uygulamanızı yerel veri tarafından tanımlanan arabirimi kullanabilir `COleDocument` OLE verilerinizi yanı sıra yerel verilerinizi depolamak için.

Uygulamanızın, program aracılığıyla başka bir kapsayıcı tarafından başlatılması için bildirin bir `COleTemplateServer` nesnesi, uygulamanızın bir üyesi olarak `CWinApp`-türetilmiş sınıf:

[!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]

İçinde `InitInstance` üye işlevini, `CWinApp`-türetilmiş sınıf, bir belge şablonu oluşturun ve belirtin, `COleLinkingDoc`-türetilmiş sınıf belge sınıfı:

[!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]

Bağlanma, `COleTemplateServer` nesnenin çağırarak belge şablonlarınızı nesnesine `ConnectTemplate` üye işlevine ve tüm sınıfı nesnelerini OLE sistemiyle çağırarak kayıt `COleTemplateServer::RegisterAll`:

[!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]

Bir örnek için `CWinApp`-türetilmiş sınıf tanımı ve `InitInstance` işlev, OCLIENT bakın. H ve OCLIENT. MFC örnekteki CPP [OCLIENT](../../visual-cpp-samples.md).

Kullanma hakkında daha fazla bilgi için `COleLinkingDoc`, makalelere göz atın [kapsayıcıları: Bir kapsayıcı uygulama](../../mfc/containers-implementing-a-container.md) ve [kapsayıcıları: Gelişmiş Özellikler](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

`COleLinkingDoc`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="colelinkingdoc"></a>  COleLinkingDoc::COleLinkingDoc

Oluşturur bir `COleLinkingDoc` iletişimleri OLE sistem DLL'lerini ile başlayan olmadan nesne.

```
COleLinkingDoc();
```

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız `Register` OLE belge açık olduğunu bildirmek için üye işlevi.

##  <a name="onfindembeddeditem"></a>  COleLinkingDoc::OnFindEmbeddedItem

Belgenin belirtilen ada sahip katıştırılmış bir OLE öğesini içerip içermediğini belirlemek için framework tarafından çağırılır.

```
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
Öğe istenen katıştırılmış OLE adına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe için bir işaretçi; Öğe bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama (adı karşılaştırma büyük/küçük harfe duyarlı) belirtilen ada sahip bir öğe için katıştırılmış öğeleri listesini arar. Depolama veya katıştırılmış OLE öğeleri adlandırma kendi yöntemi varsa, bu işlev geçersiz kılar.

##  <a name="ongetlinkeditem"></a>  COleLinkingDoc::OnGetLinkedItem

Belgenin belirtilen ada sahip bir bağlantılı sunucu öğe içerip içermediğini denetlemek için framework tarafından çağırılır.

```
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
Öğe istenen bağlı OLE adına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğe için bir işaretçi; Öğe bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Varsayılan `COleLinkingDoc` uygulama her zaman NULL döndürür. Bu işlev, türetilmiş sınıf içinde geçersiz kılınmış `COleServerDoc` (adı karşılaştırma büyük/küçük harfe duyarlı) belirtilen ada sahip bir bağlantılı öğe için OLE sunucu öğeleri listesi aramak için. Bu işlev, depolama veya bağlantılı sunucu öğeleri alınıyor kendi yönteminizi uyguladıysanız geçersiz kılar.

##  <a name="register"></a>  COleLinkingDoc::Register

OLE sistem DLL'lerini belge açık olduğunu bildirir.

```
BOOL Register(
    COleObjectFactory* pFactory,
    LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*pFactory*<br/>
(NULL olabilir) bir OLE Fabrika nesnesine işaretçi.

*lpszPathName*<br/>
Kapsayıcı belgesinin tam yolunun işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla kaydettirildi olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Oluştururken ya da OLE sistem DLL'lerini belgeyi kaydetmek için adlandırılmış bir dosyayı açmayı bu işlevi çağırın. Gömülü bir öğe belgeyi temsil ediyorsa, bu işlevi çağırmak için gerek yoktur.

Kullanıyorsanız `COleTemplateServer` , uygulamanızda `Register` sizin tarafınızdan için adlı `COleLinkingDoc`'s uygulaması `OnNewDocument`, `OnOpenDocument`, ve `OnSaveDocument`.

##  <a name="revoke"></a>  COleLinkingDoc::Revoke

OLE sistem DLL'lerini belge artık açık olduğunu bildirir.

```
void Revoke();
```

### <a name="remarks"></a>Açıklamalar

OLE sistem DLL'lerini belgenin kaydı iptal etmek için bu işlevi çağırın.

Adlandırılmış dosya kapatıldığında bu işlevi çağırmanız gerekir, ancak genellikle doğrudan çağırmanız gerekmez. `Revoke` sizin tarafınızdan için adlı `COleLinkingDoc`'s uygulaması `OnCloseDocument`, `OnNewDocument`, `OnOpenDocument`, ve `OnSaveDocument`.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek OCLIENT](../../visual-cpp-samples.md)<br/>
[COleDocument Sınıfı](../../mfc/reference/coledocument-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)
