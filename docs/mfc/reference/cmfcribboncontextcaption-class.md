---
title: CMFCRibbonContextCaption sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5726605af6b9a0d63c15cb232a094d48dd2f95a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405883"
---
# <a name="cmfcribboncontextcaption-class"></a>CMFCRibbonContextCaption sınıfı

Şerit kategorisinin veya bağlam kategorisinin üst kısmında görünen renkli bir başlık uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonContextCaption : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonContextCaption::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|[CMFCRibbonContextCaption::GetColor](#getcolor)|Başlık rengi döndürür.|
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||
|`CMFCRibbonContextCaption::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf doğrudan başlatılamaz. [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md) sınıfı bu sınıfı dahili olarak renk Şerit kategorileri eklemek için kullanır.

Şerit kategorisi rengini ayarlamak için çağrı [CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor). Bağlam kategorisi rengini ayarlamak için çağrı [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxRibbonBar.h

##  <a name="getcolor"></a>  CMFCRibbonContextCaption::GetColor

Başlık arka plan rengini döndürür.

```
AFX_RibbonCategoryColor GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Döndürülen değer, aşağıdaki numaralandırılmış değerlerden biri olabilir:

- `AFX_CategoryColor_None`

- `AFX_CategoryColor_Red`

- `AFX_CategoryColor_Orange`

- `AFX_CategoryColor_Yellow`

- `AFX_CategoryColor_Green`

- `AFX_CategoryColor_Blue`

- `AFX_CategoryColor_Indigo`

- `AFX_CategoryColor_Violet`

### <a name="remarks"></a>Açıklamalar

Çağırarak başlık rengi ayarlanabilir [CMFCRibbonCategory::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) veya [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory).

##  <a name="getrighttabx"></a>  CMFCRibbonContextCaption::GetRightTabX

Kategori Şerit sekmesinin sağ kenarı konumunu alır.

```
int GetRightTabX() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sağ taraftaki X değeri çevreleyen dikdörtgen döndürür `CMFCRibbonCategory` nesnenin şerit sekmesinden veya sekme kesilirse -1 değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonCategory Sınıfı](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
