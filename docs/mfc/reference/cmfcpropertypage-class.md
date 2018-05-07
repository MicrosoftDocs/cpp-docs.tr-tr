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
ms.openlocfilehash: b3352841b1b495d1718ffa6be034239ecd7e50c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage sınıfı
`CMFCPropertyPage` Sınıfı, bir özellik sayfasında açılır menüler görüntülemeyi destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|Oluşturan bir `CMFCPropertyPage` nesnesi.|  
|`CMFCPropertyPage::~CMFCPropertyPage`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCPropertyPage::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|`CMFCPropertyPage::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|`CMFCPropertyPage::OnSetActive`|Sayfa kullanıcı tarafından seçilir ve etkin sayfa haline gelir, bu üye işlevi çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|  
|`CMFCPropertyPage::PreTranslateMessage`|Pencere iletileri için gönderilen önce çevirir [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır. Daha fazla bilgi ve yöntem sözdizimi için bkz: [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Geçersiz kılmaları `CPropertyPage::PreTranslateMessage`.)|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCPropertyPage` Sınıfı, aksi takdirde bir sekme iletişim kutusu olarak bilinen bir özellik sayfası, her bir sayfayı temsil eder.  
  
 Kullanım `CMFCPropertyPage` ile birlikte sınıf [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) sınıfı. Özellik sayfasında menüleri kullanmak için tüm oluşumlarını Değiştir `CPropertyPage` ile sınıfı `CMFCPropertyPage` sınıfı.  
  
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
 Oluşturan bir `CMFCPropertyPage` nesnesi.  
  
```  
CMFCPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption=0);

 
CMFCPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption=0);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDTemplate`  
 Bu sayfa için şablonu kaynak kimliği.  
  
 `nIDCaption`  
 Bu sayfa için sekmesindeki koymak için kaynak kimliği etiketi. 0 ise bu sayfa için iletişim kutusu şablondan adı elde edilir. Varsayılan değer 0’dır.  
  
 `lpszTemplateName`  
 Bu sayfa için şablonun noktaları adı. Olamaz `NULL`.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu parametreleri hakkında daha fazla bilgi için bkz: [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertySheet Sınıfı](../../mfc/reference/cmfcpropertysheet-class.md)
