---
title: CHtmlEditDoc Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
ms.openlocfilehash: 8b500f651da1a73040fdb0469f2f023babe25e85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352170"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc Sınıfı

[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)ile, MFC belge görünümü mimarisi bağlamında WebBrowser düzenleme platformunun işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CHtmlEditDoc : public CDocument
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|Bir `CHtmlEditDoc` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CHtmlEditDoc::GetView](#getview)|Bu belgeye `CHtmlEditView` iliştirilen nesneyi alır.|
|[CHtmlEditDoc::Modifiye](#ismodified)|İlişkili görünümün WebBrowser denetiminin kullanıcı tarafından değiştirilen bir belge yi içerip içermediğini verir.|
|[CHtmlEditDoc::OpenURL](#openurl)|Url'yi açar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cdocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxhtml.h

## <a name="chtmleditdocchtmleditdoc"></a><a name="chtmleditdoc"></a>CHtmlEditDoc::CHtmlEditDoc

Bir `CHtmlEditDoc` nesne inşa eder.

```
CHtmlEditDoc();
```

## <a name="chtmleditdocgetview"></a><a name="getview"></a>CHtmlEditDoc::GetView

Bu belgeye iliştirilen [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) nesnesini alır.

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin `CHtmlEditView` nesnesine bir işaretçi döndürür.

## <a name="chtmleditdocismodified"></a><a name="ismodified"></a>CHtmlEditDoc::Modifiye

İlişkili görünümün WebBrowser denetiminin kullanıcı tarafından değiştirilen bir belge yi içerip içermediğini verir.

```
virtual BOOL IsModified();
```

## <a name="chtmleditdocopenurl"></a><a name="openurl"></a>CHtmlEditDoc::OpenURL

Url'yi açar.

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Parametreler

*Lpszurl*<br/>
Açılacak URL.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

## <a name="see-also"></a>Ayrıca bkz.

[HTMLEdit Örneği](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
