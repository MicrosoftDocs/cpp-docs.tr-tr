---
title: CMFCRibbonCustomizePropertyPage sınıfı
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
ms.openlocfilehash: d36e3a301aa5b861c296b0bb4859e9442dbdb75e
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560887"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage sınıfı

Şerit tabanlı uygulamalarda **Özelleştir** iletişim kutusu için özel bir sayfa uygular.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|Bir `CMFCRibbonCustomizePropertyPage` nesnesi oluşturur.|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCRibbonCustomizePropertyPage:: AddCustomCategory](#addcustomcategory)|**Komutlar** Birleşik giriş kutusuna özel bir kategori ekler.|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCRibbonCustomizePropertyPage:: OnOK](#onok)|Kullanıcı **Özelleştir** Iletişim kutusunda **Tamam** ' a tıkladığında sistem tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

**Özelleştir** iletişim kutusuna özel komutlar eklemek istiyorsanız AFX_WM_ON_RIBBON_CUSTOMIZE iletisini işlemeniz gerekir. İleti işleyicisinde, yığında bir nesne oluşturun `CMFCRibbonCustomizePropertyPage` . Özel komutların bir listesini oluşturun ve ardından `AddCustomCategory` yeni sayfayı **Özelleştir** iletişim kutusuna ekleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu `CMFCRibbonCustomizePropertyPage` ve özel bir kategorinin nasıl ekleneceğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

[CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribboncustomizedialog. h

## <a name="cmfcribboncustomizepropertypageaddcustomcategory"></a><a name="addcustomcategory"></a> CMFCRibbonCustomizePropertyPage:: AddCustomCategory

**Komutlar** Birleşik giriş kutusuna özel bir kategori ekler.

```cpp
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>Parametreler

*lpszName*\
'ndaki Özel kategori adını belirtir.

*lstIDS*\
'ndaki Özel kategoride gösterilecek şerit komut kimliklerini içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, **Komutlar** Birleşik giriş kutusuna *lpszName* adlı bir kategori ekler. Kullanıcı kategoriyi seçtiğinde, *Lstids* 'de belirtilen komutlar komut listesinde görünür.

## <a name="cmfcribboncustomizepropertypagecmfcribboncustomizepropertypage"></a><a name="cmfcribboncustomizepropertypage"></a> CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage

Bir `CMFCRibbonCustomizePropertyPage` nesnesi oluşturur.

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>Parametreler

*Pribbonçubuğu*<br/>
'ndaki Özelleştirilecek seçenekler için şerit denetimine yönelik bir işaretçi.

## <a name="cmfcribboncustomizepropertypageonok"></a><a name="onok"></a> CMFCRibbonCustomizePropertyPage:: OnOK

Kullanıcı **Özelleştir** Iletişim kutusunda **Tamam** ' a tıkladığında sistem tarafından caltald.

```
virtual void OnOK();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, **Özelleştir** iletişim kutusunda seçilen seçenekleri hızlı erişim araç çubuğuna uygular.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
