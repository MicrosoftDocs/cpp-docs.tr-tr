---
title: CRichEditCntrItem Class
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
ms.openlocfilehash: 674937df9b4ecef0d159a47a45a716d1175ad5d9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773846"
---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem Class

İle [CRichEditView](../../mfc/reference/cricheditview-class.md) ve [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), MFC'nin belge görüntüleme mimarisi bağlamında zengin düzenleme denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CRichEditCntrItem : public COleClientItem
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Oluşturur bir `CRichEditCntrItem` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Öğe, başka bir tür olarak etkinleştirir.|

## <a name="remarks"></a>Açıklamalar

"Zengin düzenleme denetimi" kullanıcı girin ve metin düzenleme bir penceredir. Metnin karakteri ve paragraf biçimlendirme atanabilir ve katıştırılmış OLE nesnelerine içerebilir. Zengin düzenleme denetimleri, metin biçimlendirmesi için bir programlama arabirimi sağlar. Ancak, bir uygulamanın tüm biçimlendirme işlemlerini kullanıcı tarafından kullanılabilir hale getirmek için gerekli olan kullanıcı arabirimi bileşenleri uygulamalıdır.

`CRichEditView` metin biçimlendirme özelliği ve metin tutar. `CRichEditDoc` OLE istemci Görünümü'nde olan öğelerin listesini tutar. `CRichEditCntrItem` bir OLE istemci öğesi kapsayıcı tarafı erişim sağlar.

Bu Windows ortak denetimi (ve bu nedenle [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) ve üzeri yalnızca Windows 95/98 ve Windows NT sürümler 3.51 altında çalışan programlar için kullanılabilir.

Zengin düzenleme kapsayıcı öğeleri bir MFC uygulamasında kullanma örneği için bkz: [WORDPAD](../../overview/visual-cpp-samples.md) örnek uygulama.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[Cdocıtem](../../mfc/reference/cdocitem-class.md)

[Coleclientıtem](../../mfc/reference/coleclientitem-class.md)

`CRichEditCntrItem`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrich.h

##  <a name="cricheditcntritem"></a>  CRichEditCntrItem::CRichEditCntrItem

Oluşturmak için bu işlevi çağırın bir `CRichEditCntrItem` nesne ve kapsayıcının belgeye ekleyin.

```
CRichEditCntrItem(
    REOBJECT* preo = NULL,
    CRichEditDoc* pContainer = NULL);
```

### <a name="parameters"></a>Parametreler

*preo*<br/>
İşaretçi bir [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) OLE öğesini tanımlayan yapısı. Yeni `CRichEditCntrItem` nesne bu OLE öğesini yapılandırılmıştır. Varsa *preo* NULL ise istemci öğesi boş.

*Implement_serıalıze*<br/>
Bu öğeyi içeren kapsayıcı belge işaretçisi. Varsa *Implement_serıalıze* null, açıkça çağırmalıdır [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) belge bu istemci öğesi eklemek için.

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm OLE başlatma gerçekleştirmez.

Daha fazla bilgi için [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) Windows SDK'sındaki yapısı.

##  <a name="synctoricheditobject"></a>  CRichEditCntrItem::SyncToRichEditObject

Cihaz yönü eşitlemek için bu işlevi çağırın [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect), bu `CRichEditCntrltem` tarafından belirtilen için *yeniden a*.

```
void SyncToRichEditObject(REOBJECT& reo);
```

### <a name="parameters"></a>Parametreler

*yeniden a*<br/>
Başvuru bir [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) OLE öğesini tanımlayan yapısı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect) Windows SDK.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[Coleclientıtem sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc Class](../../mfc/reference/cricheditdoc-class.md)<br/>
[CRichEditView sınıfı](../../mfc/reference/cricheditview-class.md)
