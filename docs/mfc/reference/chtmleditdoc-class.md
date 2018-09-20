---
title: CHtmlEditDoc sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77219f4cac64faf2604c427a2c4abf3babfd26a3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425378"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc sınıfı

İle [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), MFC belge görüntüleme mimarisi bağlamında WebBrowser düzenleme platformu işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CHtmlEditDoc : public CDocument
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|Oluşturur bir `CHtmlEditDoc` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHtmlEditDoc::GetView](#getview)|Alır `CHtmlEditView` nesne bu belgeye iliştirilmiş.|
|[CHtmlEditDoc::IsModified](#ismodified)|İlişkili Görünüm'ün WebBrowser denetimi kullanıcı tarafından değiştirildi bir belge içerip içermediğini döndürür.|
|[CHtmlEditDoc::OpenURL](#openurl)|Bir URL açılır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxhtml.h

##  <a name="chtmleditdoc"></a>  CHtmlEditDoc::CHtmlEditDoc

Oluşturur bir `CHtmlEditDoc` nesne.

```
CHtmlEditDoc();
```

##  <a name="getview"></a>  CHtmlEditDoc::GetView

Alır [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) nesne bu belgeye iliştirilmiş.

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belgenin bir işaretçi döndürür `CHtmlEditView` nesne.

##  <a name="ismodified"></a>  CHtmlEditDoc::IsModified

İlişkili Görünüm'ün WebBrowser denetimi kullanıcı tarafından değiştirildi bir belge içerip içermediğini döndürür.

```
virtual BOOL IsModified();
```

##  <a name="openurl"></a>  CHtmlEditDoc::OpenURL

Bir URL açılır.

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Parametreler

*lpszURL*<br/>
Açmak için URL.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

## <a name="see-also"></a>Ayrıca Bkz.

[HTMLEdit örnek](../../visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

