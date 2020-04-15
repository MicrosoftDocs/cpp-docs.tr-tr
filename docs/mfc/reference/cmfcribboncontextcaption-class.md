---
title: CMFCRibbonContextCaption Sınıfı
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
ms.openlocfilehash: 7aacbe23684914c91129d9962ae847d442cc411b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375213"
---
# <a name="cmfcribboncontextcaption-class"></a>CMFCRibbonContextCaption Sınıfı

Şerit kategorisinin veya bağlam kategorisinin üst kısmında görünen renkli bir resim yazısı uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonContextCaption : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CMFCRibbonContextCaption::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|[CMFCRibbonContextCaption::GetColor](#getcolor)|Başlığın rengini verir.|
|[CMFCRibbonContextCaption::GetRightTabX](#getrighttabx)||
|`CMFCRibbonContextCaption::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf doğrudan anında kullanılamaz. [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) sınıfı, şerit kategorilere renk eklemek için bu sınıfı dahili olarak kullanır.

Şerit kategorileri için renk ayarlamak için [CMFCRibbonKategori::SetTabColor'u](../../mfc/reference/cmfcribboncategory-class.md#settabcolor)arayın. Bağlam kategorileri için renk ayarlamak için [CMFCRibbonBar'ı arayın::Bağlam Kategorisini Ekle.](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonContextCaption](../../mfc/reference/cmfcribboncontextcaption-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonBar.h

## <a name="cmfcribboncontextcaptiongetcolor"></a><a name="getcolor"></a>CMFCRibbonContextCaption::GetColor

Başlığın arka plan rengini verir.

```
AFX_RibbonCategoryColor GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Döndürülen değer aşağıdaki numaralandırılmış değerlerden biri olabilir:

- `AFX_CategoryColor_None`

- `AFX_CategoryColor_Red`

- `AFX_CategoryColor_Orange`

- `AFX_CategoryColor_Yellow`

- `AFX_CategoryColor_Green`

- `AFX_CategoryColor_Blue`

- `AFX_CategoryColor_Indigo`

- `AFX_CategoryColor_Violet`

### <a name="remarks"></a>Açıklamalar

Resim yazısının rengi [CMFCRibbonKategori::SetTabColor](../../mfc/reference/cmfcribboncategory-class.md#settabcolor) veya [CMFCRibbonBar::AddContextCategory](../../mfc/reference/cmfcribbonbar-class.md#addcontextcategory)numaralı çağrıyla ayarlanabilir.

## <a name="cmfcribboncontextcaptiongetrighttabx"></a><a name="getrighttabx"></a>CMFCRibbonContextCaption::GetRightTabX

Kategorinin şerit sekmesinin sağ kenarının konumunu alır.

```
int GetRightTabX() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CMFCRibbonCategory` Nesnenin şerit sekmesinin çevreleyen dikdörtgeninin sağ x değerini veya sekme kesilirse -1 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonKategori Sınıfı](../../mfc/reference/cmfcribboncategory-class.md)<br/>
[CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
