---
title: CRichEditDoc sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
dev_langs:
- C++
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1343b2bffa86f04200e1f8c5451640345c58c73b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420354"
---
# <a name="cricheditdoc-class"></a>CRichEditDoc sınıfı

İle [CRichEditView](../../mfc/reference/cricheditview-class.md) ve [Cricheditcntrıtem](../../mfc/reference/cricheditcntritem-class.md), MFC'nin belge görüntüleme mimarisi bağlamında zengin düzenleme denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRichEditDoc::CreateClientItem](#createclientitem)|Belgenin temizleme işlemini gerçekleştirmek için çağrılır.|
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Stream giriş ve çıkışı biçimlendirme bilgileri içerip içermeyeceğini belirtir.|
|[CRichEditDoc::GetView](#getview)|Asssociated alır [CRichEditView](../../mfc/reference/cricheditview-class.md) nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Serileştiriyorsanız](#m_brtf)|Akış g/ç biçimlendirme içerip içermeyeceğini belirtir.|

## <a name="remarks"></a>Açıklamalar

"Zengin düzenleme denetimi" kullanıcı girin ve metin düzenleme bir penceredir. Metnin karakteri ve paragraf biçimlendirme atanabilir ve katıştırılmış OLE nesnelerine içerebilir. Zengin düzenleme denetimleri, metin biçimlendirmesi için bir programlama arabirimi sağlar. Ancak, bir uygulamanın tüm biçimlendirme işlemlerini kullanıcı tarafından kullanılabilir hale getirmek için gerekli olan kullanıcı arabirimi bileşenleri uygulamalıdır.

`CRichEditView` metin biçimlendirme özelliği ve metin tutar. `CRichEditDoc` Görünüm olan istemci öğeleri listesini tutar. `CRichEditCntrItem` OLE istemci öğeleri kapsayıcı tarafı erişim sağlar.

Bu Windows ortak denetimi (ve bu nedenle [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) ve üzeri yalnızca Windows 95/98 ve Windows NT sürümler 3.51 altında çalışan programlar için kullanılabilir.

Bir MFC uygulamasında bir zengin düzenleme belge kullanma örneği için bkz: [WORDPAD](../../visual-cpp-samples.md) örnek uygulama.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)

`CRichEditDoc`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxrich.h

##  <a name="createclientitem"></a>  CRichEditDoc::CreateClientItem

Oluşturmak için bu işlevi çağırın bir `CRichEditCntrItem` nesne ve bu belgeye ekleyin.

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>Parametreler

*preo*<br/>
İşaretçi bir [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) OLE öğesini tanımlayan yapısı. Yeni `CRichEditCntrItem` nesne bu OLE öğesini yapılandırılmıştır. Varsa *preo* null, yeni istemci öğesi boş.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir işaretçi [Cricheditcntrıtem](../../mfc/reference/cricheditcntritem-class.md) bu belgeye eklenmiş olan nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm OLE başlatma gerçekleştirmez.

Daha fazla bilgi için [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) Windows SDK'sındaki yapısı.

##  <a name="getstreamformat"></a>  CRichEditDoc::GetStreamFormat

Zengin düzenleme içeriğini akış için metin biçimini belirlemek için bu işlevi çağırın.

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki bayraklar biri:

- Zengin düzenleme denetiminden SF_TEXT gösterir, biçimlendirme bilgilerini korumaz.

- Zengin düzenleme denetiminden SF_RTF gösterir, biçimlendirme bilgilerini koruyun.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri dayanır [m_bRTF](#m_brtf) veri üyesi. Bu işlev SF_RTF döndürür `m_bRTF` TRUE; Aksi takdirde, SF_TEXT.

##  <a name="getview"></a>  CRichEditDoc::GetView

Erişim için bu işlevi çağırın [CRichEditView](../../mfc/reference/cricheditview-class.md) bununla ilişkili nesne `CRichEditDoc` nesne.

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçi `CRichEditView` belgeyle ilişkili nesne.

### <a name="remarks"></a>Açıklamalar

Metin ve biçimlendirme bilgileri bulunan `CRichEditView` nesne. `CRichEditDoc` Nesne seri hale getirme için OLE öğeleri tutar. Bulunmamalıdır tek `CRichEditView` her `CRichEditDoc`.

##  <a name="m_brtf"></a>  Serileştiriyorsanız

TRUE olduğunda belirten [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) ve [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) paragraf ve karakter biçimlendirme özelliklerine depolamanız gerekir.

```
BOOL m_bRTF;
```

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek WORDPAD](../../visual-cpp-samples.md)<br/>
[COleServerDoc Sınıfı](../../mfc/reference/coleserverdoc-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRichEditView Sınıfı](../../mfc/reference/cricheditview-class.md)<br/>
[CRichEditCntrItem Sınıfı](../../mfc/reference/cricheditcntritem-class.md)<br/>
[COleDocument Sınıfı](../../mfc/reference/coledocument-class.md)<br/>
[CRichEditCtrl Sınıfı](../../mfc/reference/cricheditctrl-class.md)
