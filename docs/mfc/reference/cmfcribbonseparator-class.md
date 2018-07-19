---
title: CMFCRibbonSeparator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12f4b9019a79b6ff57da6905b6ad9329788b4ec9
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849775"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator sınıfı
Şerit ayırıcı uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|Oluşturur bir `CMFCRibbonSeparator` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|Ekler için ayırıcı **komutları** listesinde **Özelleştir** iletişim kutusu. (Geçersiz kılmaları [CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|  
|`CMFCRibbonSeparator::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|  
|`CMFCRibbonSeparator::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|Ayırıcı'nın üyesi başka bir nesneden değişkenleri ayarlayan bir kopyalama yöntemi.|  
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|Ayırıcı boyutunu döndürür.|  
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|Bu ayırıcı olup olmadığını gösterir.|  
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|Bu sekme durağı olup olmadığını gösterir.|  
|[CMFCRibbonSeparator::OnDraw](#ondraw)|Şerit veya hızlı erişim araç çubuğu ayırıcı çizmek için sistem tarafından çağrılır.|  
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|Ayırıcı çizilecek sistem tarafından çağrılan **komutları** listesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir Şerit ayırıcı mantıksal olarak ayırır öğeleri Şerit, dikey veya yatay bir çizgi var. Ayırıcı, Şerit denetimi, ana uygulama menüsünde, Şerit durum çubuğuna ve hızlı erişim araç çubuğu üzerinde kurulabilir.  
  
 Ayırıcı, uygulamanızda kullanmak için yeni bir nesne oluşturmak ve burada gösterildiği gibi ana uygulama menüsüne ekleyin:  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```  
Çağrı [CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) ayırıcılar için Şerit Panel eklemek için. Ayırıcılar ayrılan ve tarafından dahili olarak eklenen `AddSeparator` yöntemi.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxbaseribbonelement.h  
  
##  <a name="addtolistbox"></a>  CMFCRibbonSeparator::AddToListBox  
 Ekler için ayırıcı **komutları** listesinde **Özelleştir** iletişim kutusu.  
  
```  
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,  
    BOOL bDeep);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndListBox*  
 Bir işaretçi **komutları** liste ayırıcı burada eklenir.  
  
 [in] *bDeep*  
 Yoksayıldı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır tabanlı dizin dizesi tarafından belirtilen liste kutusunda *pWndListBox*.  
  
##  <a name="cmfcribbonseparator"></a>  CMFCRibbonSeparator::CMFCRibbonSeparator  
 Oluşturur bir `CMFCRibbonSeparator` nesne.  
  
```  
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bIsHoriz*  
 TRUE ise ayırıcı yatay; FALSE ise, ayırıcı dikeydir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yatay ayırıcısı uygulama menülerde kullanılır. Dikey ayırıcısı, araç çubuklarını kullanılır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCRibbonSeparator` sınıfı.  
  
 [!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]  
  
##  <a name="copyfrom"></a>  CMFCRibbonSeparator::CopyFrom  
 Ayırıcı'nın üyesi başka bir nesneden değişkenleri ayarlayan bir kopyalama yöntemi.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *Src*  
 Kopyalanacak kaynak Şerit öğesi.  
  
##  <a name="getregularsize"></a>  CMFCRibbonSeparator::GetRegularSize  
 Ayırıcı boyutunu döndürür.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz içeriği için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirli bir cihaz bağlamı ayırıcı boyutu.  
  
##  <a name="isseparator"></a>  CMFCRibbonSeparator::IsSeparator  
 Bu ayırıcı olup olmadığını gösterir.  
  
```  
virtual BOOL IsSeparator() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu sınıf için her zaman TRUE.  
  
##  <a name="istabstop"></a>  CMFCRibbonSeparator::IsTabStop  
 Bu sekme durağı olup olmadığını gösterir.  
  
```  
virtual BOOL IsTabStop() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu sınıf için her zaman FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir Şerit ayırıcı sekme durağı değil.  
  
##  <a name="ondraw"></a>  CMFCRibbonSeparator::OnDraw  
 Şerit veya hızlı erişim araç çubuğu ayırıcı çizmek için sistem tarafından çağrılır.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonSeparator::OnDrawOnList  
 Ayırıcı çizilecek sistem tarafından çağrılan **komutları** listesi.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] *pDC*|Bir cihaz bağlamı için bir işaretçi.|  
|[in] *strText*|Listede görüntülenecek metin.|  
|[in] *nTextOffset*|Metin ile sol tarafındaki dikdörtgen arasındaki boşluk.|  
|[in] *dikdörtgen*|Sınırlayıcı dikdörtgeni belirtir.|  
|[in] *bIsSelected*|Yoksayıldı.|  
|[in] *bHighlighted*|Yoksayıldı.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
