---
title: CRichEditCntrItem Sınıfı
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
ms.openlocfilehash: b8158105d09d5cfc7c25512567a98121b194a82a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368283"
---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem Sınıfı

[CRichEditView](../../mfc/reference/cricheditview-class.md) ve [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)ile, MFC'nin belge görünümü mimarisi bağlamında zengin edit denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CRichEditCntrItem : public COleClientItem
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Bir `CRichEditCntrItem` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRichEditCntrItem:SyncToRichEditObject](#synctoricheditobject)|Öğeyi başka bir tür olarak etkinleştirir.|

## <a name="remarks"></a>Açıklamalar

"Zengin bir edit denetimi", kullanıcının metni girip atabildiği bir penceredir. Metin karakter ve paragraf biçimlendirme atanabilir ve katışılmış OLE nesneleri içerebilir. Zengin edit denetimleri metni biçimlendirmek için bir programlama arabirimi sağlar. Ancak, bir uygulama, biçimlendirme işlemlerini kullanıcının kullanımına açmak için gereken kullanıcı arabirimi bileşenlerini uygulamalıdır.

`CRichEditView`metnin metin ve biçimlendirme özelliğini korur. `CRichEditDoc`görünümde bulunan OLE istemci öğelerinin listesini tutar. `CRichEditCntrItem`OLE istemci öğesine kapsayıcı tarafı erişimi sağlar.

Bu Windows Ortak denetimi (ve dolayısıyla [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) yalnızca Windows 95/98 ve Windows NT sürümleri 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Bir MFC uygulamasında zengin edit kapsayıcı öğeleri kullanma örneği için [WORDPAD](../../overview/visual-cpp-samples.md) örnek uygulamasına bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[Coleclientıtem](../../mfc/reference/coleclientitem-class.md)

`CRichEditCntrItem`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrich.h

## <a name="cricheditcntritemcricheditcntritem"></a><a name="cricheditcntritem"></a>CRichEditCntrItem::CRichEditCntrItem

Bir `CRichEditCntrItem` nesne oluşturmak ve kapsayıcı belgeye eklemek için bu işlevi çağırın.

```
CRichEditCntrItem(
    REOBJECT* preo = NULL,
    CRichEditDoc* pContainer = NULL);
```

### <a name="parameters"></a>Parametreler

*preo*<br/>
Bir OLE öğesini açıklayan bir [REOBJECT](/windows/win32/api/richole/ns-richole-reobject) yapısıiçin işaretçi. Yeni `CRichEditCntrItem` nesne bu OLE öğesinin etrafında oluşturulur. *Preo* NULL ise, istemci öğesi boştur.

*pKonteyner*<br/>
Bu öğeyi içerecek kapsayıcı belgeiçin işaretçi. *pContainer* NULL ise, bu istemci öğesini belgeye eklemek için Açıkça [COleDocument::AddItem'i](../../mfc/reference/coledocument-class.md#additem) aramanız gerekir.

### <a name="remarks"></a>Açıklamalar

Bu işlev herhangi bir OLE başlatma gerçekleştirmez.

Daha fazla bilgi için Windows SDK'daki [REOBJECT](/windows/win32/api/richole/ns-richole-reobject) yapısına bakın.

## <a name="cricheditcntritemsynctoricheditobject"></a><a name="synctoricheditobject"></a>CRichEditCntrItem:SyncToRichEditObject

Bu işlevi cihaz yönü, [DVASPECT](/windows/win32/api/wtypes/ne-wtypes-dvaspect), bu `CRichEditCntrltem` *reo*tarafından belirtilen senkronize etmek için arayın.

```
void SyncToRichEditObject(REOBJECT& reo);
```

### <a name="parameters"></a>Parametreler

*Reo*<br/>
Bir OLE öğesini açıklayan bir [REOBJECT](/windows/win32/api/richole/ns-richole-reobject) yapısına başvuru.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [DVASPECT'e](/windows/win32/api/wtypes/ne-wtypes-dvaspect) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[COleClientItem Sınıfı](../../mfc/reference/coleclientitem-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc Sınıfı](../../mfc/reference/cricheditdoc-class.md)<br/>
[CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)
