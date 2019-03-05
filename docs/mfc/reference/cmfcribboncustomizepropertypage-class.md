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
ms.openlocfilehash: 8c790ca249f34a3c9b36d1bd77dafdc4a91bd352
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288915"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage sınıfı

Özel bir sayfa için uygulayan **Özelleştir** Şerit tabanlı uygulamalarda iletişim kutusu.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|Oluşturur bir `CMFCRibbonCustomizePropertyPage` nesne.|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|Ekler için özel bir kategori **komutları** birleşik giriş kutusu.|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|Sistem tarafından bir kullanıcı tıkladığında çağrılır **Tamam** üzerinde **Özelleştir** iletişim kutusu.|

## <a name="remarks"></a>Açıklamalar

Özel komutları eklemek istiyorsanız **Özelleştir** iletişim kutusu, AFX_WM_ON_RIBBON_CUSTOMIZE iletiyi işlemesi gerekir. İleti işleyicisi örneği bir `CMFCRibbonCustomizePropertyPage` yığında nesne. Özel komutların bir listesini oluşturun ve ardından çağırın `AddCustomCategory` yeni sayfasına eklenecek **Özelleştir** iletişim kutusu.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCRibbonCustomizePropertyPage` nesne ve özel bir kategori eklemek için.

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

**Başlık:** afxribboncustomizedialog.h

##  <a name="addcustomcategory"></a>  CMFCRibbonCustomizePropertyPage::AddCustomCategory

Ekler için özel bir kategori **komutları** birleşik giriş kutusu.

```
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*lpszName*|[in] Özel kategori adını belirtir.|
|*lstIDS*|[in] Özel kategoride gösterilecek Şerit komut kimlikleri içeriyor.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem olarak adlandırılmış kategorisi ekler *lpszName* için **komutları** birleşik giriş kutusu. Komutlar kullanıcı kategorisini seçtiğinde, belirtilen *lstIDS* komut listede görünür.

##  <a name="cmfcribboncustomizepropertypage"></a>  CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage

Oluşturur bir `CMFCRibbonCustomizePropertyPage` nesne.

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>Parametreler

*pRibbonBar*<br/>
[in] Bir Şerit denetimi kendisi için bir işaretçi özelleştirmek için seçenek.

##  <a name="onok"></a>  CMFCRibbonCustomizePropertyPage::OnOK

Kullanıcı tıkladığında sistem tarafından Calleld **Tamam** üzerinde **Özelleştir** iletişim kutusu.

```
virtual void OnOK();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, seçilen seçeneklerin geçerlidir **Özelleştir** hızlı erişim araç çubuğu iletişim kutusu.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
