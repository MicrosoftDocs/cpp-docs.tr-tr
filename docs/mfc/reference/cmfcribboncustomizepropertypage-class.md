---
title: CMFCRibbonCustomizePropertyPage Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
ms.openlocfilehash: 57fbd1e1f574beebff8baab014e7ab615f56333f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754167"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage Sınıfı

Şerit tabanlı uygulamalarda **Özelleştir** iletişim kutusu için özel bir sayfa uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|[CMFCRibbonCustomizeÖzellikPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|Bir `CMFCRibbonCustomizePropertyPage` nesne inşa eder.|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCRibbonCustomizeÖzellikPage::AddCustomCategory](#addcustomcategory)|**Komutlar** açılan kutusuna özel bir kategori ekler.|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCRibbonCustomizeÖzellikSayfası::OnOK](#onok)|Bir kullanıcı **Özelleştir** iletişim kutusunda **Tamam'ı** tıklattığında sistem tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

**Özelleştir** iletişim kutusuna özel komutlar eklemek istiyorsanız, AFX_WM_ON_RIBBON_CUSTOMIZE iletisini işlemeniz gerekir. İleti işleyicisinde, yığındaki bir `CMFCRibbonCustomizePropertyPage` nesneyi anında anons edin. Özel komutların bir listesini oluşturun `AddCustomCategory` ve ardından yeni sayfayı **Özelleştir** iletişim kutusuna eklemek için arayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCRibbonCustomizePropertyPage` nesnenin nasıl oluşturup özel bir kategori ekleyeceğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[Cpropertypage](../../mfc/reference/cpropertypage-class.md)

[CMFCÖzellik Sayfası](../../mfc/reference/cmfcpropertypage-class.md)

[CMFCRibbonCustomizeÖzellik Sayfası](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribboncustomizedialog.h

## <a name="cmfcribboncustomizepropertypageaddcustomcategory"></a><a name="addcustomcategory"></a>CMFCRibbonCustomizeÖzellikPage::AddCustomCategory

**Komutlar** açılan kutusuna özel bir kategori ekler.

```cpp
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*Lpszname*|[içinde] Özel kategori adını belirtir.|
|*lstIDS*|[içinde] Özel kategoride gösterilecek şerit komut iT'lerini içerir.|

### <a name="remarks"></a>Açıklamalar

Bu **yöntem, Komutlar** açılan kutusuna *lpszName* adlı bir kategori ekler. Kullanıcı kategoriyi seçtiğinde, *lstIDS'de* belirtilen komutlar komut listesinde görünür.

## <a name="cmfcribboncustomizepropertypagecmfcribboncustomizepropertypage"></a><a name="cmfcribboncustomizepropertypage"></a>CMFCRibbonCustomizeÖzellikPage::CMFCRibbonCustomizePropertyPage

Bir `CMFCRibbonCustomizePropertyPage` nesne inşa eder.

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>Parametreler

*pRibbonBar*<br/>
[içinde] Seçenekleri özelleştirmek için şerit denetimi için bir işaretçi.

## <a name="cmfcribboncustomizepropertypageonok"></a><a name="onok"></a>CMFCRibbonCustomizeÖzellikSayfası::OnOK

Kullanıcı **Özelleştir** iletişim kutusunda **Tamam'ı** tıklattığında sistem tarafından çağrılabilir.

```
virtual void OnOK();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, Hızlı Erişim Araç Çubuğu'na **Özelleştir** iletişim kutusunda seçilen seçenekleri uygular.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
