---
title: CRichEditDoc Sınıfı
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
ms.openlocfilehash: 587cf65543e24e586fb8b2336481d6e841473134
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368258"
---
# <a name="cricheditdoc-class"></a>CRichEditDoc Sınıfı

[CRichEditView](../../mfc/reference/cricheditview-class.md) ve [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)ile, MFC'nin belge görünümü mimarisi bağlamında zengin edit denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRichEditDoc::CreateClientItem](#createclientitem)|Belgenin temizlenmesini gerçekleştirmek için çağrıldı.|
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Akış girişi ve çıktının biçimlendirme bilgilerini içerip içermeyeceğini gösterir.|
|[CRichEditDoc::GetView](#getview)|Associated [CRichEditView](../../mfc/reference/cricheditview-class.md) nesnesini alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CRichEditDoc::m_bRTF](#m_brtf)|Akış G/Ç'nin biçimlendirme yi içerip içermeyeceğini gösterir.|

## <a name="remarks"></a>Açıklamalar

"Zengin bir edit denetimi", kullanıcının metni girip atabildiği bir penceredir. Metin karakter ve paragraf biçimlendirme atanabilir ve katışılmış OLE nesneleri içerebilir. Zengin edit denetimleri metni biçimlendirmek için bir programlama arabirimi sağlar. Ancak, bir uygulama, biçimlendirme işlemlerini kullanıcının kullanımına açmak için gereken kullanıcı arabirimi bileşenlerini uygulamalıdır.

`CRichEditView`metnin metin ve biçimlendirme özelliğini korur. `CRichEditDoc`görünümde bulunan istemci öğelerin listesini tutar. `CRichEditCntrItem`OLE istemci öğelerine kapsayıcı tarafı erişimi sağlar.

Bu Windows Ortak denetimi (ve dolayısıyla [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) yalnızca Windows 95/98 ve Windows NT sürümleri 3.51 ve sonraki sürümler altında çalışan programlar için kullanılabilir.

Bir MFC uygulamasında zengin bir edit belgesi kullanma örneği için [WORDPAD](../../overview/visual-cpp-samples.md) örnek uygulamasına bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cdocument](../../mfc/reference/cdocument-class.md)

[Coledocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

[Coleserverdoc](../../mfc/reference/coleserverdoc-class.md)

`CRichEditDoc`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrich.h

## <a name="cricheditdoccreateclientitem"></a><a name="createclientitem"></a>CRichEditDoc::CreateClientItem

Bir `CRichEditCntrItem` nesne oluşturmak ve bu belgeye eklemek için bu işlevi çağırın.

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>Parametreler

*preo*<br/>
Bir OLE öğesini açıklayan bir [REOBJECT](/windows/win32/api/richole/ns-richole-reobject) yapısıiçin işaretçi. Yeni `CRichEditCntrItem` nesne bu OLE öğesinin etrafında oluşturulur. *Preo* NULL ise, yeni istemci öğesi boştur.

### <a name="return-value"></a>Dönüş Değeri

Bu belgeye eklenen yeni bir [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev herhangi bir OLE başlatma gerçekleştirmez.

Daha fazla bilgi için Windows SDK'daki [REOBJECT](/windows/win32/api/richole/ns-richole-reobject) yapısına bakın.

## <a name="cricheditdocgetstreamformat"></a><a name="getstreamformat"></a>CRichEditDoc::GetStreamFormat

Zengin editin içeriğini aktarmak için metin biçimini belirlemek için bu işlevi arayın.

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki bayraklardan biri:

- SF_TEXT Zengin edit denetiminin biçimlendirme bilgilerini korumadığını gösterir.

- SF_RTF Zengin edit denetiminin biçimlendirme bilgilerini koruduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

İade değeri [m_bRTF](#m_brtf) veri üyesine dayanır. Bu işlev DOĞRU `m_bRTF` ise SF_RTF döndürür; aksi takdirde, SF_TEXT.

## <a name="cricheditdocgetview"></a><a name="getview"></a>CRichEditDoc::GetView

Bu `CRichEditDoc` nesneyle ilişkili [CRichEditView](../../mfc/reference/cricheditview-class.md) nesnesine erişmek için bu işlevi arayın.

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgeyle `CRichEditView` ilişkili nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Metin ve biçimlendirme bilgileri nesnenin `CRichEditView` içinde bulunur. Nesne `CRichEditDoc` serileştirme için OLE öğelerini korur. Her biri `CRichEditDoc`için `CRichEditView` sadece bir tane olmalı.

## <a name="cricheditdocm_brtf"></a><a name="m_brtf"></a>CRichEditDoc::m_bRTF

TRUE olduğunda, [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) ve [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) paragraf ve karakter biçimlendirme özelliklerini depolamalıdır gösterir.

```
BOOL m_bRTF;
```

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)<br/>
[CRichEditCntrItem Sınıfı](../../mfc/reference/cricheditcntritem-class.md)<br/>
[COleDocument Sınıfı](../../mfc/reference/coledocument-class.md)<br/>
[CRichEditCtrl Sınıfı](../../mfc/reference/cricheditctrl-class.md)
