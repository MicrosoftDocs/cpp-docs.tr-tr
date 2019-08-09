---
title: CRichEditDoc sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
ms.openlocfilehash: d296185fe2ea2216f4abe17b191f71b6fa36e1f9
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916716"
---
# <a name="cricheditdoc-class"></a>CRichEditDoc sınıfı

[CRichEditView](../../mfc/reference/cricheditview-class.md) ve [Cricheditcntridıtem](../../mfc/reference/cricheditcntritem-class.md)ile, MFC 'nin belge görünümü mimarisinin bağlamı içinde zengin düzenleme denetiminin işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditDoc:: Createclientıtem](#createclientitem)|Belgeyi temizleme işlemini gerçekleştirmek için çağırılır.|
|[CRichEditDoc:: GetStreamFormat](#getstreamformat)|Akış girişi ve çıkışının biçimlendirme bilgilerini içerip içermediğini belirtir.|
|[CRichEditDoc:: GetView](#getview)|Asssocilandırılmış [CRichEditView](../../mfc/reference/cricheditview-class.md) nesnesini alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditDoc:: m_bRTF](#m_brtf)|Akış g/ç 'nin biçimlendirme içerip içermediğini belirtir.|

## <a name="remarks"></a>Açıklamalar

"Zengin düzenleme denetimi", kullanıcının metin girebileceği ve düzenleyebileceği bir penceredir. Metne karakter ve paragraf biçimlendirme atanabilir ve katıştırılmış OLE nesneleri dahil edilebilir. Zengin düzenleme denetimleri, metin biçimlendirme için bir programlama arabirimi sağlar. Ancak, bir uygulamanın biçimlendirme işlemlerini Kullanıcı için kullanılabilir hale getirmek için gereken herhangi bir kullanıcı arabirimi bileşenini uygulaması gerekir.

`CRichEditView`metnin metin ve biçimlendirme özelliklerini korur. `CRichEditDoc`görünümdeki istemci öğelerinin listesini tutar. `CRichEditCntrItem`OLE istemci öğelerine kapsayıcı tarafı erişimi sağlar.

Bu Windows ortak denetimi (ve bu nedenle [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) yalnızca Windows 95/98 ve Windows NT sürümleri 3,51 ve üzeri sürümlerde çalışan programlar için kullanılabilir.

Bir MFC uygulamasında zengin düzenleme belgesi kullanmanın bir örneği için bkz. [WordPad](../../overview/visual-cpp-samples.md) örnek uygulaması.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[Colet belgesi](../../mfc/reference/coledocument-class.md)

[Cotalinkingdoc](../../mfc/reference/colelinkingdoc-class.md)

[Cotaserverdoc](../../mfc/reference/coleserverdoc-class.md)

`CRichEditDoc`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrich. h

##  <a name="createclientitem"></a>CRichEditDoc:: Createclientıtem

Bir `CRichEditCntrItem` nesne oluşturmak ve bu belgeye eklemek için bu işlevi çağırın.

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>Parametreler

*Preo*<br/>
Bir OLE öğesini açıklayan bir [reobject](/windows/desktop/api/richole/ns-richole-reobject) yapısına yönelik işaretçi. Yeni `CRichEditCntrItem` nesne bu ole öğesi etrafında oluşturulur. *Preo* null ise, yeni istemci öğesi boştur.

### <a name="return-value"></a>Dönüş Değeri

Bu belgeye eklenen yeni bir [Cricheditcntridıtem](../../mfc/reference/cricheditcntritem-class.md) nesnesine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev herhangi bir OLE başlatması gerçekleştirmez.

Daha fazla bilgi için Windows SDK [reobject](/windows/desktop/api/richole/ns-richole-reobject) yapısına bakın.

##  <a name="getstreamformat"></a>CRichEditDoc:: GetStreamFormat

Zengin düzenlemenin içeriğini akışa alma metin biçimini öğrenmek için bu işlevi çağırın.

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki bayraklardan biri:

- SF_TEXT, zengin düzenleme denetiminin biçimlendirme bilgilerini korumadığını gösterir.

- SF_RTF, zengin düzenleme denetiminin biçimlendirme bilgilerini korudığını gösterir.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri [m_bRTF](#m_brtf) veri üyesine göre belirlenir. Bu işlev true ise SF_RTF `m_bRTF` döndürür; Aksi durumda, SF_TEXT.

##  <a name="getview"></a>CRichEditDoc:: GetView

Bu`CRichEditDoc` nesneyle ilişkili [CRichEditView](../../mfc/reference/cricheditview-class.md) nesnesine erişmek için bu işlevi çağırın.

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgeyle ilişkili nesne işaretçisi. `CRichEditView`

### <a name="remarks"></a>Açıklamalar

Metin ve biçimlendirme bilgileri `CRichEditView` nesnenin içinde yer alır. `CRichEditDoc` Nesnesi serileştirme için OLE öğelerini tutar. `CRichEditView` Her`CRichEditDoc`biri için yalnızca bir tane olmalıdır.

##  <a name="m_brtf"></a>CRichEditDoc:: m_bRTF

DOĞRU olduğunda, [CRichEditCtrl:: StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) ve [CRichEditCtrl:: StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) 'ın paragraf ve karakter biçimlendirme özelliklerini depolaması gerektiğini gösterir.

```
BOOL m_bRTF;
```

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)<br/>
[CRichEditCntrItem Sınıfı](../../mfc/reference/cricheditcntritem-class.md)<br/>
[COleDocument Sınıfı](../../mfc/reference/coledocument-class.md)<br/>
[CRichEditCtrl Sınıfı](../../mfc/reference/cricheditctrl-class.md)
