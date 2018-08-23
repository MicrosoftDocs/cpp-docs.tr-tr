---
title: CMFCRibbonStatusBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddDynamicElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddSeparator
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::Create
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::CreateEx
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindByID
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExtendedArea
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetSpace
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsBottomFrame
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsInformationMode
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RecalcLayout
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveAll
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::SetInformation
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::OnDrawInformation
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonStatusBar [MFC], AddDynamicElement
- CMFCRibbonStatusBar [MFC], AddElement
- CMFCRibbonStatusBar [MFC], AddExtendedElement
- CMFCRibbonStatusBar [MFC], AddSeparator
- CMFCRibbonStatusBar [MFC], Create
- CMFCRibbonStatusBar [MFC], CreateEx
- CMFCRibbonStatusBar [MFC], FindByID
- CMFCRibbonStatusBar [MFC], FindElement
- CMFCRibbonStatusBar [MFC], GetCount
- CMFCRibbonStatusBar [MFC], GetElement
- CMFCRibbonStatusBar [MFC], GetExCount
- CMFCRibbonStatusBar [MFC], GetExElement
- CMFCRibbonStatusBar [MFC], GetExtendedArea
- CMFCRibbonStatusBar [MFC], GetSpace
- CMFCRibbonStatusBar [MFC], IsBottomFrame
- CMFCRibbonStatusBar [MFC], IsExtendedElement
- CMFCRibbonStatusBar [MFC], IsInformationMode
- CMFCRibbonStatusBar [MFC], RecalcLayout
- CMFCRibbonStatusBar [MFC], RemoveAll
- CMFCRibbonStatusBar [MFC], RemoveElement
- CMFCRibbonStatusBar [MFC], SetInformation
- CMFCRibbonStatusBar [MFC], OnDrawInformation
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 378ecc3c02a78bc99fa999090119e75a45dc27a7
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42464971"
---
# <a name="cmfcribbonstatusbar-class"></a>CMFCRibbonStatusBar sınıfı
`CMFCRibbonStatusBar` Sınıfı Şerit öğelerini görüntüleyebilen bir durum çubuğu denetimi uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonStatusBar : public CMFCRibbonBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::AddDynamicElement](#adddynamicelement)|Şerit durum çubuğuna dinamik bir öğe ekler.|  
|[CMFCRibbonStatusBar::AddElement](#addelement)|Şerit durum çubuğuna yeni bir Şerit öğesi ekler.|  
|[CMFCRibbonStatusBar::AddExtendedElement](#addextendedelement)|Şerit durum çubuğuna genişletilmiş bölgesine bir Şerit öğesi ekler.|  
|[CMFCRibbonStatusBar::AddSeparator](#addseparator)|Ayırıcı, Şerit durum çubuğuna ekler.|  
|[CMFCRibbonStatusBar::Create](#create)|Şerit durum çubuğuna oluşturur.|  
|[CMFCRibbonStatusBar::CreateEx](#createex)|Şerit durum çubuğuna bir genişletilmiş stili oluşturur.|  
|[CMFCRibbonStatusBar::FindByID](#findbyid)||  
|[CMFCRibbonStatusBar::FindElement](#findelement)|Belirtilen komut kimliği olan öğeye bir işaretçi döndürür|  
|[CMFCRibbonStatusBar::GetCount](#getcount)|Şerit durum çubuğuna ana alanda bulunan öğelerin sayısını döndürür.|  
|[CMFCRibbonStatusBar::GetElement](#getelement)|Belirtilen dizinde bulunan bir öğeye bir işaretçi döndürür.|  
|[CMFCRibbonStatusBar::GetExCount](#getexcount)|Şerit durum çubuğuna genişletilmiş alanda bulunan öğelerin sayısını döndürür.|  
|[CMFCRibbonStatusBar::GetExElement](#getexelement)|Şerit durum çubuğuna genişletilmiş alanında belirtilen bir dizinden konumundaki öğeye bir işaretçi döndürür.|  
|[CMFCRibbonStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCRibbonStatusBar::GetSpace](#getspace)||  
|[CMFCRibbonStatusBar::IsBottomFrame](#isbottomframe)||  
|[CMFCRibbonStatusBar::IsExtendedElement](#isextendedelement)||  
|[CMFCRibbonStatusBar::IsInformationMode](#isinformationmode)|Bilgi modu için Şerit durum çubuğuna etkin olup olmadığını belirler.|  
|[CMFCRibbonStatusBar::RecalcLayout](#recalclayout)|(Geçersiz kılmaları [CMFCRibbonBar::RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).)|  
|[CMFCRibbonStatusBar::RemoveAll](#removeall)|Şerit durum çubuğunda tüm öğeleri kaldırır.|  
|[CMFCRibbonStatusBar::RemoveElement](#removeelement)|Bir Şerit durum çubuğuna belirtilen komut kimliği olan öğeyi kaldırır.|  
|[CMFCRibbonStatusBar::SetInformation](#setinformation)|Etkinleştirir veya Şerit durum çubuğuna bilgi modunu devre dışı bırakır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::OnDrawInformation](#ondrawinformation)|Şerit durum bilgileri modu etkinleştirildiğinde çubuğunda görüntülenen bilgi dizesi görüntüler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcılar, Şerit durum çubuğuna, Şerit öğelerinin görünürlüğü için Şerit durum çubuğuna yerleşik bağlam menüsünü kullanarak değiştirebilirsiniz. Ekleme veya öğeleri dinamik olarak kaldırın.  
  
 Şerit durum çubuğuna iki alan içerir: bir ana alan ve bir genişletilmiş alan. Genişletilmiş alan Şerit durum çubuğuna sağ tarafında görüntülenir ve ana alan gösterilenden farklı bir renkte görünür.  
  
 Genellikle, durum çubuğunun ana alan durum bildirimleri ve genişletilmiş alan görünüm denetimi görüntüler. Şerit durum çubuğuna kullanıcı yeniden boyutlandırdığında genişletilmiş alan olabildiğince uzun bir süre görünür kalır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCRibbonStatusBar` sınıfı. Örnek yeni bir Şerit öğesi eklemek için Şerit durum çubuğuna, Şerit durum çubuğuna genişletilmiş bölgesine bir Şerit öğesi eklemek nasıl gösterir bir ayırıcı ekleyin ve Şerit durum çubuğuna normal modunu etkinleştirin.  
  
 [!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]  
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
 [CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribbonstatusbar.h  
  
##  <a name="adddynamicelement"></a>  CMFCRibbonStatusBar::AddDynamicElement  
 Şerit durum çubuğuna dinamik bir öğe ekler.  
  
```  
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pElement*  
 Dinamik bir öğe için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Normal öğeleri aksine dinamik öğeleri özelleştirilebilir değildir ve durum çubuğu özelleştirme menüsünü bunları göstermez.  
  
##  <a name="addelement"></a>  CMFCRibbonStatusBar::AddElement  
 Şerit durum çubuğuna yeni bir Şerit öğesi ekler.  
  
```  
void AddElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pElement*  
 Eklenen öğeye bir işaretçi.  
  
 [in] *lpszLabel*  
 Öğesinin metin etiketi.  
  
 [in] *bIsVisible*  
 Öğenin gizli olarak eklemek istiyorsanız öğe olarak görünür, yanlış eklemek istediğiniz TRUE.  
  
##  <a name="addextendedelement"></a>  CMFCRibbonStatusBar::AddExtendedElement  
 Şerit durum çubuğuna genişletilmiş bölgesine bir Şerit öğesi ekler.  
  
```  
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pElement*  
 Eklenen öğeye bir işaretçi.  
  
 [in] *lpszLabel*  
 Öğesinin metin etiketi.  
  
 [in] *bIsVisible*  
 Öğenin gizli olarak eklemek istiyorsanız öğe olarak görünür, yanlış eklemek istediğiniz TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 Durum çubuğu denetiminin sağ tarafında genişletilmiş alanıdır.  
  
##  <a name="addseparator"></a>  CMFCRibbonStatusBar::AddSeparator  
 Ayırıcı, Şerit durum çubuğuna ekler.  
  
```  
void AddSeparator();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Framework ayırıcı sonra yöntem ekler [CMFCRibbonStatusBar::AddElement](#addelement). Son öğe ekler.  
  
##  <a name="create"></a>  CMFCRibbonStatusBar::Create  
 Şerit durum çubuğuna oluşturur.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pParentWnd*  
 Üst penceresine bir işaretçi.  
  
 [in] *dwStyle*  
 Mantıksal OR birleşimi denetim stilleri.  
  
 [in] *nID*  
 Durum çubuğu denetiminin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durum çubuğu başarıyla FALSE aksi oluşturulursa TRUE.  
  
##  <a name="createex"></a>  CMFCRibbonStatusBar::CreateEx  
 Genişletilmiş bir stilde bir Şerit durum çubuğuna oluşturur.  
  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle=0,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parametreler  
 *pParentWnd*  
 Üst penceresine bir işaretçi.  
  
 *dwCtrlStyle*  
 Mantıksal OR birleşimi durum çubuğu nesnesini oluşturmak için ek stilleri.  
  
 *dwStyle*  
 Durum çubuğu denetim stili.  
  
 *nID*  
 Durum çubuğu denetiminin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durum çubuğu başarıyla FALSE aksi oluşturulursa TRUE.  
  
##  <a name="findbyid"></a>  CMFCRibbonStatusBar::FindByID  
 Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiCmdID*  
 [in] *BOOL*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findelement"></a>  CMFCRibbonStatusBar::FindElement  
 Belirtilen komut kimliği olan öğeye bir işaretçi döndürür  
  
```  
CMFCRibbonBaseElement* FindElement(UINT uiID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiID*  
 Öğe kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen komut kimliğine sahip öğe için bir işaretçi Böyle bir öğe yoksa NULL.  
  
##  <a name="getcount"></a>  CMFCRibbonStatusBar::GetCount  
 Şerit durum çubuğuna ana alanda bulunan öğelerin sayısını döndürür.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit durum çubuğuna ana alanda bulunan öğe sayısı.  
  
##  <a name="getelement"></a>  CMFCRibbonStatusBar::GetElement  
 Belirtilen dizinde bulunan bir öğeye bir işaretçi döndürür.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Durum çubuğu denetimi ana alanında bulunan bir öğenin sıfır tabanlı bir dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dizinde bulunan öğesinin işaretçisi. Boş dizin negatiftir ya da durum çubuğunun içindeki öğelerin sayısını aşıyor.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getexcount"></a>  CMFCRibbonStatusBar::GetExCount  
 Şerit durum çubuğuna genişletilmiş alanda bulunan öğelerin sayısını döndürür.  
  
```  
int GetExCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit durum çubuğuna genişletilmiş alanda bulunan öğe sayısı.  
  
##  <a name="getexelement"></a>  CMFCRibbonStatusBar::GetExElement  
 Şerit durum çubuğuna genişletilmiş alanında belirtilen bir dizinden konumundaki öğeye bir işaretçi döndürür. Durum çubuğu denetiminin sağ tarafında genişletilmiş alanıdır.  
  
```  
CMFCRibbonBaseElement* GetExElement(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nIndex*  
 Durum çubuğu denetimi genişletilmiş alanında bulunan bir öğenin sıfır tabanlı dizinini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit durum çubuğuna genişletilmiş alanında belirtilen bir dizinden konumundaki öğeye bir işaretçi. NULL ise *nIndex* negatif veya Şerit durum çubuğuna genişletilmiş alanındaki öğelerin sayısını aşıyor.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getextendedarea"></a>  CMFCRibbonStatusBar::GetExtendedArea  
 Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dikdörtgen*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getspace"></a>  CMFCRibbonStatusBar::GetSpace  
 Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
  
```  
int GetSpace() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isbottomframe"></a>  CMFCRibbonStatusBar::IsBottomFrame  
 Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
  
```  
BOOL IsBottomFrame() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isextendedelement"></a>  CMFCRibbonStatusBar::IsExtendedElement  
 Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
  
```  
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pElement*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isinformationmode"></a>  CMFCRibbonStatusBar::IsInformationMode  
 Bilgi modu için Şerit durum çubuğuna etkin olup olmadığını belirler.  
  
```  
BOOL IsInformationMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Durum çubuğu bilgilerini modunda çalışabilmeniz için TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bilgilerini modunda, durum çubuğu tüm normal bölmeleri gizler ve ileti dizesini görüntüler.  
  
##  <a name="ondrawinformation"></a>  CMFCRibbonStatusBar::OnDrawInformation  
 Şerit durum bilgileri modu etkinleştirildiğinde çubuğunda görüntülenen dizeyi görüntüler.  
  
```  
virtual void OnDrawInformation(
    CDC* pDC,  
    CString& strInfo,  
    CRect rectInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *strInfo*  
 Bilgi dizesi.  
  
 [in] *rectInfo*  
 Dikdörtgen.  
  
### <a name="remarks"></a>Açıklamalar  
 Durum çubuğunda bilgi dizesi görünümünü özelleştirmek istiyorsanız türetilen bir sınıfta bu yöntemi yok sayın. Kullanım [CMFCRibbonStatusBar::SetInformation](#setinformation) durum çubuğu bilgilerini modunda koymak için yöntemi. Bu modda, durum çubuğu tüm bölmeleri gizler ve bilgi dizesi tarafından belirtilen görüntüler *strInfo*.  
  
##  <a name="recalclayout"></a>  CMFCRibbonStatusBar::RecalcLayout  
 Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removeall"></a>  CMFCRibbonStatusBar::RemoveAll  
 Şerit durum çubuğunda tüm öğeleri kaldırır.  
  
```  
void RemoveAll();
```  
  
##  <a name="removeelement"></a>  CMFCRibbonStatusBar::RemoveElement  
 Bir Şerit durum çubuğuna belirtilen komut kimliği olan öğeyi kaldırır.  
  
```  
BOOL RemoveElement(UINT uiID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiID*  
 Durum Çubuğu'ndan kaldırma öğesinin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir öğe, belirtilen TRUE *uiID* kaldırılır. FALSE Aksi takdirde.  
  
##  <a name="setinformation"></a>  CMFCRibbonStatusBar::SetInformation  
 Etkinleştirir veya Şerit durum çubuğuna bilgi modunu devre dışı bırakır.  
  
```  
void SetInformation(LPCTSTR lpszInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszInfo*  
 Bilgi dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Durum çubuğu bilgilerini modunda yerleştirmek için bu yöntemi kullanın. Bu modda, durum çubuğu tüm bölmeleri gizler ve bilgi dizesi tarafından belirtilen görüntüler *lpszInfo*.  
  
 LpszInfo NULL olduğunda, durum çubuğu, normal moduna geri döner.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)   
 [CMFCRibbonBaseElement sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
