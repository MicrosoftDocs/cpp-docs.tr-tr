---
title: CMFCPropertyPage sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b552417af72b24cddae9055d436a56f771c48743
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203453"
---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage sınıfı
`CMFCPropertyPage` Sınıfı, bir özellik sayfasında açılır menülerin görüntülenmesini destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|Oluşturur bir `CMFCPropertyPage` nesne.|  
|`CMFCPropertyPage::~CMFCPropertyPage`|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCPropertyPage::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|  
|`CMFCPropertyPage::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|  
|`CMFCPropertyPage::OnSetActive`|Sayfa kullanıcı tarafından seçilir ve etkin sayfa olur, bu üye işlevi framework tarafından çağırılır. (Geçersiz kılmaları [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|  
|`CMFCPropertyPage::PreTranslateMessage`|Pencere iletileri için dağıtılmadan önce çevirir [TranslateMessage](https://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](https://msdn.microsoft.com/library/windows/desktop/ms644934) Windows işlevleri. Daha fazla bilgi ve yöntem sözdizimi için bkz. [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz kılmaları `CPropertyPage::PreTranslateMessage`.)|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCPropertyPage` Sınıfı, aksi takdirde bir sekme iletişim kutusu bilinen bir özellik sayfası, her bir sayfayı temsil eder.  
  
 Kullanım `CMFCPropertyPage` ile birlikte sınıfı [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) sınıfı. Bir özellik sayfasında menüleri kullanmak için tüm oluşumlarını değiştirin `CPropertyPage` sınıfıyla `CMFCPropertyPage` sınıfı.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpropertypage.h  
  
##  <a name="cmfcpropertypage"></a>  CMFCPropertyPage::CMFCPropertyPage  
 Oluşturur bir `CMFCPropertyPage` nesne.  
  
```  
CMFCPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption=0);

 
CMFCPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption=0);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDTemplate*  
 Bu sayfa şablonu kaynak kimliği.  
  
 *nIDCaption*  
 Bu sayfa için sekmesinde koymak için etiketin kaynak kimliği. 0 ise, bu sayfa için iletişim kutusu şablonundan adı elde edilir. Varsayılan değer 0’dır.  
  
 *lpszTemplateName*  
 Bu sayfa şablonunun adını işaret. NULL olamaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu parametreler hakkında daha fazla bilgi için bkz. [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertySheet Sınıfı](../../mfc/reference/cmfcpropertysheet-class.md)
