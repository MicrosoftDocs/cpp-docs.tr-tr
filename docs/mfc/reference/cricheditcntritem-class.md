---
title: Cricheditcntridıtem sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
ms.openlocfilehash: b333cbbe33b42709614376cf98be01111be967a2
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916817"
---
# <a name="cricheditcntritem-class"></a>Cricheditcntridıtem sınıfı

[CRichEditView](../../mfc/reference/cricheditview-class.md) ve [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)ile, MFC 'nin belge görünümü mimarisinin bağlamı içinde zengin düzenleme denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CRichEditCntrItem : public COleClientItem
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cricheditcntridıtem:: Cricheditcntridıtem](#cricheditcntritem)|Bir `CRichEditCntrItem` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cricheditcntridıtem:: SyncToRichEditObject](#synctoricheditobject)|Öğeyi başka bir tür olarak etkinleştirir.|

## <a name="remarks"></a>Açıklamalar

"Zengin düzenleme denetimi", kullanıcının metin girebileceği ve düzenleyebileceği bir penceredir. Metne karakter ve paragraf biçimlendirme atanabilir ve katıştırılmış OLE nesneleri dahil edilebilir. Zengin düzenleme denetimleri, metin biçimlendirme için bir programlama arabirimi sağlar. Ancak, bir uygulamanın biçimlendirme işlemlerini Kullanıcı için kullanılabilir hale getirmek için gereken herhangi bir kullanıcı arabirimi bileşenini uygulaması gerekir.

`CRichEditView`metnin metin ve biçimlendirme özelliklerini korur. `CRichEditDoc`görünümdeki OLE istemci öğelerinin listesini tutar. `CRichEditCntrItem`OLE istemci öğesine kapsayıcı tarafı erişimi sağlar.

Bu Windows ortak denetimi (ve bu nedenle [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) yalnızca Windows 95/98 ve Windows NT sürümleri 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Bir MFC uygulamasında zengin düzenleme kapsayıcı öğelerinin kullanılmasına ilişkin bir örnek için bkz. [WordPad](../../overview/visual-cpp-samples.md) örnek uygulaması.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`CRichEditCntrItem`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrich. h

##  <a name="cricheditcntritem"></a>Cricheditcntridıtem:: Cricheditcntridıtem

Bir `CRichEditCntrItem` nesne oluşturmak ve kapsayıcı belgeye eklemek için bu işlevi çağırın.

```
CRichEditCntrItem(
    REOBJECT* preo = NULL,
    CRichEditDoc* pContainer = NULL);
```

### <a name="parameters"></a>Parametreler

*Preo*<br/>
Bir OLE öğesini açıklayan bir [reobject](/windows/desktop/api/richole/ns-richole-reobject) yapısına yönelik işaretçi. Yeni `CRichEditCntrItem` nesne bu ole öğesi etrafında oluşturulur. *Preo* null ise, istemci öğesi boştur.

*pContainer*<br/>
Bu öğeyi içerecek kapsayıcı belgesi işaretçisi. *PContainer* null ise, bu istemci öğesini bir belgeye eklemek Için [Cotadocument:: AddItem](../../mfc/reference/coledocument-class.md#additem) öğesini açıkça çağırmanız gerekir.

### <a name="remarks"></a>Açıklamalar

Bu işlev herhangi bir OLE başlatması gerçekleştirmez.

Daha fazla bilgi için Windows SDK [reobject](/windows/desktop/api/richole/ns-richole-reobject) yapısına bakın.

##  <a name="synctoricheditobject"></a>Cricheditcntridıtem:: SyncToRichEditObject

Bu işlevi, bunun `CRichEditCntrltem` , [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect)olan cihaz yönünü, *REO*tarafından belirtilen şekilde eşitleyecek şekilde çağırın.

```
void SyncToRichEditObject(REOBJECT& reo);
```

### <a name="parameters"></a>Parametreler

*yeniden oluştur*<br/>
OLE öğesini açıklayan bir [reobject](/windows/desktop/api/richole/ns-richole-reobject) yapısına başvuru.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK bkz. [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect) .

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc Sınıfı](../../mfc/reference/cricheditdoc-class.md)<br/>
[CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
