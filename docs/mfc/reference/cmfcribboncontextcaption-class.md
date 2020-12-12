---
description: 'Daha fazla bilgi edinin: CMFCRibbonContextCaption sınıfı'
title: CMFCRibbonContextCaption sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetColor
- AFXRIBBONBAR/CMFCRibbonContextCaption::GetRightTabX
helpviewer_keywords:
- CMFCRibbonContextCaption [MFC], GetColor
- CMFCRibbonContextCaption [MFC], GetRightTabX
ms.assetid: cce2c0a2-8370-4266-997e-f8d0eeb3d616
ms.openlocfilehash: fa4134b89055274e4f44bef1150518207e06143e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293631"
---
# <a name="cmfcribboncontextcaption-class"></a>CMFCRibbonContextCaption sınıfı

Şerit kategorisinin veya bağlam kategorisinin üst kısmında görünen renkli bir başlık uygular.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonContextCaption : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonContextCaption::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|[CMFCRibbonContextCaption:: GetColor](#getcolor)|Açıklamalı alt yazısının rengini döndürür.|
|[CMFCRibbonContextCaption:: GetRightTabX](#getrighttabx)||
|`CMFCRibbonContextCaption::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf doğrudan başlatılamaz. [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) sınıfı, şerit kategorilerine renk eklemek için bu sınıfı dahili olarak kullanır.

Şerit kategorilerinin rengini ayarlamak için [CMFCRibbonCategory:: SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)çağırın. Bağlam kategorilerinin rengini ayarlamak için [CMFCRibbonBar:: AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbondüğmesi](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonBar. h

## <a name="cmfcribboncontextcaptiongetcolor"></a><a name="getcolor"></a> CMFCRibbonContextCaption:: GetColor

Başlığın arka plan rengini döndürür.

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

Açıklamalı alt yazısının rengi [CMFCRibbonCategory:: SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) veya [CMFCRibbonBar:: AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)çağırarak ayarlanabilir.

## <a name="cmfcribboncontextcaptiongetrighttabx"></a><a name="getrighttabx"></a> CMFCRibbonContextCaption:: GetRightTabX

Kategorinin Şerit sekmesinin sağ kenarının konumunu alır.

```
int GetRightTabX() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin Şerit sekmesinin çevreleyen dikdörtgeninin sağ X değerini `CMFCRibbonCategory` veya sekme kesilmişse-1 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonCategory sınıfı](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
