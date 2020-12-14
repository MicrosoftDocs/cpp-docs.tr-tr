---
description: 'Daha fazla bilgi edinin: Cotalinkingdoc sınıfı'
title: Cotalinkingdoc sınıfı
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
ms.openlocfilehash: 10cf9bb81c4cbbd324b95a13dc2fa44548266583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226915"
---
# <a name="colelinkingdoc-class"></a>Cotalinkingdoc sınıfı

İçerdikleri katıştırılmış öğelere bağlamayı destekleyen OLE kapsayıcı belgelerinin temel sınıfı.

## <a name="syntax"></a>Syntax

```
class COleLinkingDoc : public COleDocument
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copalinkingdoc:: Cotalinkingdoc](#colelinkingdoc)|Bir `COleLinkingDoc` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotalinkingdoc:: Register](#register)|Belgeyi OLE sistem dll 'Leriyle kaydeder.|
|[Cotalinkingdoc:: Revoke](#revoke)|Belgenin kaydını iptal eder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotalinkingdoc:: OnFindEmbeddedItem](#onfindembeddeditem)|Belirtilen katıştırılmış öğeyi bulur.|
|[Cotalinkingdoc:: OnGetLinkedItem](#ongetlinkeditem)|Belirtilen bağlantılı öğeyi bulur.|

## <a name="remarks"></a>Açıklamalar

Katıştırılmış öğelere bağlamayı destekleyen bir kapsayıcı uygulaması "bağlantı kapsayıcısı" olarak adlandırılır. [Oclient](../../overview/visual-cpp-samples.md) örnek uygulaması, bir bağlantı kapsayıcısına örnektir.

Bağlı bir öğenin kaynağı başka bir belgedeki katıştırılmış bir öğe olduğunda, katıştırılmış öğenin düzenlenmesi için belgeyi içeren belgenin yüklenmesi gerekir. Bu nedenle, bir bağlantı kapsayıcısının, Kullanıcı bağlantılı öğenin kaynağını düzenlemek istediğinde başka bir kapsayıcı uygulaması tarafından başlatılabilmelidir. Uygulamanız, program aracılığıyla başlatıldığında belge oluşturabilmek için [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) sınıfını da kullanmalıdır.

Kapsayıcınızı bir bağlantı kapsayıcısı yapmak için, belge sınıfınızı `COleLinkingDoc` [Cotadocument](../../mfc/reference/coledocument-class.md)yerine ' den türetebilirsiniz. Diğer OLE kapsayıcılarda olduğu gibi, uygulamanızın yerel verilerinin yanı sıra gömülü veya bağlantılı öğelerin depolanması için de sınıfınızı tasarlamanız gerekir. Ayrıca, yerel verilerinizi depolamak için veri yapıları tasarlamanız gerekir. `CDocItem`Uygulamanızın yerel verileri için bir türetilmiş sınıf tanımlarsanız, `COleDocument` Yerel VERILERINIZI ve OLE verilerinizi depolamak için tarafından tanımlanan arabirimi kullanabilirsiniz.

Uygulamanızın başka bir kapsayıcı tarafından programlı olarak başlatılmasını sağlamak için, bir `COleTemplateServer` nesneyi uygulamanızın türetilmiş sınıfının bir üyesi olarak bildirin `CWinApp` :

[!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]

`InitInstance` `CWinApp` Türetilmiş sınıfınızın üye işlevinde bir belge şablonu oluşturun ve `COleLinkingDoc` belge sınıfı olarak türetilmiş sınıfınızı belirtin:

[!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]

Nesnenin `COleTemplateServer` `ConnectTemplate` üye işlevini çağırarak ve tüm sınıf nesnelerini ole sistemiyle kaydederek, şunu çağırarak nesnelerinizi belge şablonlarına bağlayın `COleTemplateServer::RegisterAll` :

[!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]

Örnek türetilmiş bir `CWinApp` sınıf tanımı ve işlevi için `InitInstance` bkz. oclient. H ve OCLIENT. MFC örnek [Oistemcisindeki](../../overview/visual-cpp-samples.md)cpp.

Kullanma hakkında daha fazla bilgi için `COleLinkingDoc` bkz. Makale [kapsayıcıları: kapsayıcı](../../mfc/containers-implementing-a-container.md) ve kapsayıcılar uygulama [: Gelişmiş Özellikler](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[Colet belgesi](../../mfc/reference/coledocument-class.md)

`COleLinkingDoc`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="colelinkingdoccolelinkingdoc"></a><a name="colelinkingdoc"></a> Copalinkingdoc:: Cotalinkingdoc

`COleLinkingDoc`OLE sistem dll 'leriyle iletişime başlamadan bir nesne oluşturur.

```
COleLinkingDoc();
```

### <a name="remarks"></a>Açıklamalar

`Register`OLE 'nin belgenin açık olduğunu bildirmek için üye işlevini çağırmanız gerekir.

## <a name="colelinkingdoconfindembeddeditem"></a><a name="onfindembeddeditem"></a> Cotalinkingdoc:: OnFindEmbeddedItem

Belgenin, belirtilen ada sahip gömülü bir OLE öğesi içerip içermediğini anlamak için bu çerçeve tarafından çağırılır.

```
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
İstenen katıştırılmış OLE öğesi adına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğeye yönelik bir işaretçi; Öğe bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, belirtilen ada sahip bir öğe için katıştırılmış öğelerin listesini arar (ad karşılaştırma büyük/küçük harfe duyarlıdır). Katıştırılmış OLE öğelerini depolama veya adlandırma yönteminiz varsa, bu işlevi geçersiz kılın.

## <a name="colelinkingdocongetlinkeditem"></a><a name="ongetlinkeditem"></a> Cotalinkingdoc:: OnGetLinkedItem

Belgenin belirtilen ada sahip bağlı bir sunucu öğesi içerip içermediğini denetlemek için Framework tarafından çağırılır.

```
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Parametreler

*lpszItemName*<br/>
İstenen bağlantılı OLE öğesi adına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen öğeye yönelik bir işaretçi; Öğe bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

Varsayılan `COleLinkingDoc` uygulama her zaman null değerini döndürür. Bu işlev, `COleServerDoc` belirtilen ada sahip bağlantılı bir öğe IÇIN OLE sunucusu öğelerinin listesini aramak üzere türetilmiş sınıfta geçersiz kılındı (ad karşılaştırma büyük/küçük harfe duyarlıdır). Bağlı sunucu öğelerini depolama veya alma yönteminizi uyguladıysanız, bu işlevi geçersiz kılın.

## <a name="colelinkingdocregister"></a><a name="register"></a> Cotalinkingdoc:: Register

OLE sistem dll 'Lerine belgenin açık olduğunu bildirir.

```
BOOL Register(
    COleObjectFactory* pFactory,
    LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Parametreler

*pFactory*<br/>
OLE Factory nesnesine yönelik işaretçi (NULL olabilir).

*lpszPathName*<br/>
Kapsayıcı belgesinin tam yolunu gösteren işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belge başarıyla kaydedilmişse sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Belgeyi OLE sistem dll 'Leriyle kaydetmek için adlandırılmış bir dosya oluştururken veya açarken bu işlevi çağırın. Belge gömülü bir öğeyi temsil ediyorsa bu işlevi çağırmaya gerek yoktur.

Uygulamanızda kullanıyorsanız,, `COleTemplateServer` `Register` ve uygulaması tarafından sizin için çağırılır `COleLinkingDoc` `OnNewDocument` `OnOpenDocument` `OnSaveDocument` .

## <a name="colelinkingdocrevoke"></a><a name="revoke"></a> Cotalinkingdoc:: Revoke

OLE sistem dll 'Lerine belgenin artık açık olmadığını bildirir.

```cpp
void Revoke();
```

### <a name="remarks"></a>Açıklamalar

Belge kaydını OLE sistem dll 'Leriyle iptal etmek için bu işlevi çağırın.

Adlandırılmış bir dosyayı kapatırken bu işlevi çağırmanız gerekir, ancak genellikle doğrudan çağırmanız gerekmez. `Revoke` ,, `COleLinkingDoc` ve ' nin uygulamasına göre çağırılır `OnCloseDocument` `OnNewDocument` `OnOpenDocument` `OnSaveDocument` .

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Cotadocument sınıfı](../../mfc/reference/coledocument-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)
