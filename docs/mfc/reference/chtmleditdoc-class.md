---
description: 'Daha fazla bilgi edinin: CHtmlEditDoc Class'
title: CHtmlEditDoc sınıfı
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
ms.openlocfilehash: 5fb8187ff7925efc5bdfa6a0079a8ec4b186ae63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115319"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc sınıfı

[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)Ile, MFC belge görünümü mimarisinin bağlamı içinde WebBrowser düzenlemesi platformunun işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class AFX_NOVTABLE CHtmlEditDoc : public CDocument
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|Bir `CHtmlEditDoc` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHtmlEditDoc:: GetView](#getview)|`CHtmlEditView`Bu belgeye eklenmiş nesneyi alır.|
|[CHtmlEditDoc:: IsModified](#ismodified)|İlişkili görünümün WebBrowser denetiminin Kullanıcı tarafından değiştirilmiş bir belge içerip içermediğini döndürür.|
|[CHtmlEditDoc:: OpenURL](#openurl)|Bir URL açar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxhtml. h

## <a name="chtmleditdocchtmleditdoc"></a><a name="chtmleditdoc"></a> CHtmlEditDoc::CHtmlEditDoc

Bir `CHtmlEditDoc` nesnesi oluşturur.

```
CHtmlEditDoc();
```

## <a name="chtmleditdocgetview"></a><a name="getview"></a> CHtmlEditDoc:: GetView

Bu belgeye iliştirilmiş [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) nesnesini alır.

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin nesnesine bir işaretçi döndürür `CHtmlEditView` .

## <a name="chtmleditdocismodified"></a><a name="ismodified"></a> CHtmlEditDoc:: IsModified

İlişkili görünümün WebBrowser denetiminin Kullanıcı tarafından değiştirilmiş bir belge içerip içermediğini döndürür.

```
virtual BOOL IsModified();
```

## <a name="chtmleditdocopenurl"></a><a name="openurl"></a> CHtmlEditDoc:: OpenURL

Bir URL açar.

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Parametreler

*lpszURL*<br/>
Açılacak URL.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[HTMLEdit örneği](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
