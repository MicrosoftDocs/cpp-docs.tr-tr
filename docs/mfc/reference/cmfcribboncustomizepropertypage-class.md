---
title: CMFCRibbonCustomizePropertyPage sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 542c34fc02eca1f090072f49b9688d3edd4d78e6
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040681"
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
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|Oluşturan bir `CMFCRibbonCustomizePropertyPage` nesnesi.|  
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|Özel bir kategori ekler **komutları** birleşik giriş kutusu.|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|Sistem tarafından bir kullanıcı tıkladığında adlı **Tamam** üzerinde **Özelleştir** iletişim kutusu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Özel komutlar eklemek istiyorsanız **Özelleştir** iletişim kutusu, AFX_WM_ON_RIBBON_CUSTOMIZE iletiyi işlemesi gerekir. İleti işleyicisi örneği bir `CMFCRibbonCustomizePropertyPage` yığında nesnesi. Özel komutlar listesini oluşturmak ve ardından arama `AddCustomCategory` yeni sayfa eklemek için **Özelleştir** iletişim kutusu.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCRibbonCustomizePropertyPage` nesne ve özel bir kategori eklemek için.  
  
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
 Özel bir kategori ekler **komutları** birleşik giriş kutusu.  
  
```  
void AddCustomCategory(
    LPCTSTR lpszName,  
    const CList<UINT, UINT>& lstIDS);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] *lpszName*|Özel kategori adı belirtir.|  
|[in] *lstIDS*|Özel kategoride gösterilecek Şerit komut kimlikleri içeriyor.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem adlı bir kategori ekler *lpszName* için **komutları** birleşik giriş kutusu. Komutları kullanıcı kategorisini seçtiğinde, belirtilen *lstIDS* komutu listede görüntülenir.  
  
##  <a name="cmfcribboncustomizepropertypage"></a>  CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage  
 Oluşturan bir `CMFCRibbonCustomizePropertyPage` nesnesi.  
  
```  
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pRibbonBar*  
 Kendisi için bir Şerit denetimi için bir işaretçi özelleştirmek için seçenekleri.  
  
##  <a name="onok"></a>  CMFCRibbonCustomizePropertyPage::OnOK  
 Bir kullanıcı tıkladığında sistem tarafından Calleld **Tamam** üzerinde **Özelleştir** iletişim kutusu.  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama seçili seçeneklerini uygular **Özelleştir** hızlı erişim araç iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
