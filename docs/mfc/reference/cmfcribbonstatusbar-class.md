---
title: "CMFCRibbonStatusBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "37"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd6322b372a9cfb6ef75875d183d1b3e0a3e79c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcribbonstatusbar-class"></a>CMFCRibbonStatusBar sınıfı
`CMFCRibbonStatusBar` Sınıfı Şerit öğeleri görüntülemek bir durum çubuğu denetimi uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonStatusBar : public CMFCRibbonBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::AddDynamicElement](#adddynamicelement)|Dinamik bir öğe için Şerit durum çubuğu ekler.|  
|[CMFCRibbonStatusBar::AddElement](#addelement)|Şerit durum çubuğuna yeni bir Şerit öğesi ekler.|  
|[CMFCRibbonStatusBar::AddExtendedElement](#addextendedelement)|Şerit durum çubuğu genişletilmiş bölgesine bir Şerit öğesi ekler.|  
|[CMFCRibbonStatusBar::AddSeparator](#addseparator)|Ayırıcı için Şerit durum çubuğu ekler.|  
|[CMFCRibbonStatusBar::Create](#create)|Şerit durum çubuğu oluşturur.|  
|[CMFCRibbonStatusBar::CreateEx](#createex)|Şerit durum çubuğu genişletilmiş stili ile oluşturur.|  
|[CMFCRibbonStatusBar::FindByID](#findbyid)||  
|[CMFCRibbonStatusBar::FindElement](#findelement)|Belirtilen komut kimliğine sahip öğe için bir işaretçi döndürür|  
|[CMFCRibbonStatusBar::GetCount](#getcount)|Şerit durum çubuğu ana alanda bulunan öğe sayısını döndürür.|  
|[CMFCRibbonStatusBar::GetElement](#getelement)|Belirtilen bir dizinde bulunan öğe için bir işaretçi döndürür.|  
|[CMFCRibbonStatusBar::GetExCount](#getexcount)|Şerit durum çubuğu genişletilmiş alanda bulunan öğe sayısını döndürür.|  
|[CMFCRibbonStatusBar::GetExElement](#getexelement)|Şerit durum çubuğu genişletilmiş alanında belirtilen dizininde bulunan öğe için bir işaretçi döndürür.|  
|[CMFCRibbonStatusBar::GetExtendedArea](#getextendedarea)||  
|[CMFCRibbonStatusBar::GetSpace](#getspace)||  
|[CMFCRibbonStatusBar::IsBottomFrame](#isbottomframe)||  
|[CMFCRibbonStatusBar::IsExtendedElement](#isextendedelement)||  
|[CMFCRibbonStatusBar::IsInformationMode](#isinformationmode)|Bilgi modu için Şerit durum çubuğunu etkin olup olmadığını belirler.|  
|[CMFCRibbonStatusBar::RecalcLayout](#recalclayout)|(Geçersiz kılmaları [CMFCRibbonBar::RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).)|  
|[CMFCRibbonStatusBar::RemoveAll](#removeall)|Şerit Durum Çubuğu'ndan tüm öğeleri kaldırır.|  
|[CMFCRibbonStatusBar::RemoveElement](#removeelement)|Belirtilen komut kimliği Şerit durum çubuğunda olan öğeyi kaldırır.|  
|[CMFCRibbonStatusBar::SetInformation](#setinformation)|Etkinleştirir veya Şerit durum çubuğu bilgilerini modunu devre dışı bırakır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonStatusBar::OnDrawInformation](#ondrawinformation)|Şerit durum bilgileri modu etkinleştirildiğinde çubuğunda görüntülenen bilgi dizesi görüntüler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcılar için Şerit durum çubuğunu yerleşik bağlam menüsünü kullanarak bir Şerit durum çubuğunda Şerit öğelerinin görünürlüğü değiştirebilirsiniz. Ekleme veya öğeleri dinamik olarak kaldırın.  
  
 Şerit durum çubuğu iki alan vardır: ana alanı ve genişletilmiş bir alanı. Genişletilmiş alan Şerit durum çubuğu sağ tarafta görüntülenir ve ana alanı daha farklı renkte görüntülenir.  
  
 Genellikle, durum çubuğunun ana alanı durumu bildirimleri ve genişletilmiş alanı görünümü denetimleri görüntüler. Şerit durum çubuğu kullanıcı göre yeniden boyutlandırır genişletilmiş alan mümkün olan en kısa sürece görünür kalır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCRibbonStatusBar` sınıfı. Bir ayırıcı ekleyin örnek Şerit durum çubuğuna yeni bir Şerit öğesi eklemek, bir Şerit öğesi Şerit durum çubuğu genişletilmiş bölgesine eklemek nasıl gösterir ve normal modu Şerit durum çubuğu için etkinleştirin.  
  
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
  
##  <a name="adddynamicelement"></a>CMFCRibbonStatusBar::AddDynamicElement  
 Dinamik bir öğe için Şerit durum çubuğu ekler.  
  
```  
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pElement`  
 Dinamik bir öğe için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Normal öğeleri aksine dinamik öğelerin özelleştirilebilir değildir ve durum çubuğunun Özelleştir menüsünde bunları görüntülemez.  
  
##  <a name="addelement"></a>CMFCRibbonStatusBar::AddElement  
 Şerit durum çubuğuna yeni bir Şerit öğesi ekler.  
  
```  
void AddElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pElement`  
 Eklenen öğesi için bir işaretçi.  
  
 [in]`lpszLabel`  
 Öğesinin metin etiketi.  
  
 [in]`bIsVisible`  
 `TRUE`öğe olarak görünür, eklemek istiyorsanız `FALSE` öğesi olarak eklemek istiyorsanız gizli.  
  
##  <a name="addextendedelement"></a>CMFCRibbonStatusBar::AddExtendedElement  
 Şerit durum çubuğu genişletilmiş bölgesine bir Şerit öğesi ekler.  
  
```  
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,  
    LPCTSTR lpszLabel,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pElement`  
 Eklenen öğesi için bir işaretçi.  
  
 [in]`lpszLabel`  
 Öğesinin metin etiketi.  
  
 [in]`bIsVisible`  
 `TRUE`öğe olarak görünür, eklemek istiyorsanız `FALSE` öğesi olarak eklemek istiyorsanız gizli.  
  
### <a name="remarks"></a>Açıklamalar  
 Durum çubuğu denetimi sağ tarafta genişletilmiş bir alandır.  
  
##  <a name="addseparator"></a>CMFCRibbonStatusBar::AddSeparator  
 Ayırıcı için Şerit durum çubuğu ekler.  
  
```  
void AddSeparator();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sonraki yöntemin bir ayırıcı framework ekler [CMFCRibbonStatusBar::AddElement](#addelement). Son öğe ekler.  
  
##  <a name="create"></a>CMFCRibbonStatusBar::Create  
 Şerit durum çubuğu oluşturur.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pParentWnd`  
 Üst pencere için bir işaretçi.  
  
 [in]`dwStyle`  
 Mantıksal OR birleşimi denetim stilleri.  
  
 [in]`nID`  
 Durum çubuğu denetiminin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Durum çubuğu başarıyla oluşturulduysa `FALSE` Aksi takdirde.  
  
##  <a name="createex"></a>CMFCRibbonStatusBar::CreateEx  
 Genişletilmiş bir stilde bir Şerit durum çubuğu oluşturur.  
  
```  
BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle=0,  
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,  
    UINT nID=AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentWnd`  
 Üst pencere için bir işaretçi.  
  
 `dwCtrlStyle`  
 Mantıksal OR birleşimi durum çubuğu nesnesi oluşturmak için ek stilleri.  
  
 `dwStyle`  
 Durum çubuğu denetim stili.  
  
 `nID`  
 Durum çubuğu denetiminin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Durum çubuğu başarıyla oluşturulduysa `FALSE` Aksi takdirde.  
  
##  <a name="findbyid"></a>CMFCRibbonStatusBar::FindByID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCmdID`  
 [in]`BOOL`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findelement"></a>CMFCRibbonStatusBar::FindElement  
 Belirtilen komut kimliğine sahip öğe için bir işaretçi döndürür  
  
```  
CMFCRibbonBaseElement* FindElement(UINT uiID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiID`  
 Öğenin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen komut kimliğine sahip öğe için bir işaretçi `NULL`Böyle bir öğe varsa.  
  
##  <a name="getcount"></a>CMFCRibbonStatusBar::GetCount  
 Şerit durum çubuğu ana alanda bulunan öğe sayısını döndürür.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit durum çubuğu ana alanda bulunan öğe sayısı.  
  
##  <a name="getelement"></a>CMFCRibbonStatusBar::GetElement  
 Belirtilen bir dizinde bulunan öğe için bir işaretçi döndürür.  
  
```  
CMFCRibbonBaseElement* GetElement(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nIndex`  
 Durum çubuğu denetimi ana alanında bulunan bir öğenin sıfır tabanlı bir dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dizinde bulunan öğe için bir işaretçi. `NULL`Dizin negatif veya durum çubuğunda öğe sayısını aşıyor.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getexcount"></a>CMFCRibbonStatusBar::GetExCount  
 Şerit durum çubuğu genişletilmiş alanda bulunan öğe sayısını döndürür.  
  
```  
int GetExCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit durum çubuğu genişletilmiş alanda bulunan öğe sayısı.  
  
##  <a name="getexelement"></a>CMFCRibbonStatusBar::GetExElement  
 Şerit durum çubuğu genişletilmiş alanında belirtilen dizininde bulunan öğe için bir işaretçi döndürür. Durum çubuğu denetimi sağ tarafta genişletilmiş bir alandır.  
  
```  
CMFCRibbonBaseElement* GetExElement(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nIndex`  
 Durum çubuğu denetimi genişletilmiş alanında bulunan bir öğenin sıfır tabanlı dizini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şerit durum çubuğu genişletilmiş alanında belirtilen dizininde bulunan öğe için bir işaretçi. `NULL`varsa `nIndex` negatif veya genişletilmiş alanının Şerit durum çubuğu öğelerinin sayısını aşıyor.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getextendedarea"></a>CMFCRibbonStatusBar::GetExtendedArea  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL GetExtendedArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`rect`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getspace"></a>CMFCRibbonStatusBar::GetSpace  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetSpace() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isbottomframe"></a>CMFCRibbonStatusBar::IsBottomFrame  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsBottomFrame() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isextendedelement"></a>CMFCRibbonStatusBar::IsExtendedElement  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pElement`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isinformationmode"></a>CMFCRibbonStatusBar::IsInformationMode  
 Bilgi modu için Şerit durum çubuğunu etkin olup olmadığını belirler.  
  
```  
BOOL IsInformationMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Durum çubuğu bilgilerini modda çalışabilir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bilgi modunda, durum çubuğu tüm normal bölmeleri gizler ve ileti dizesi görüntüler.  
  
##  <a name="ondrawinformation"></a>CMFCRibbonStatusBar::OnDrawInformation  
 Görünen dize bilgi modu etkinleştirildiğinde çubuğu Şerit durumunu görüntüler.  
  
```  
virtual void OnDrawInformation(
    CDC* pDC,  
    CString& strInfo,  
    CRect rectInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in]`strInfo`  
 Bilgi dizesi.  
  
 [in]`rectInfo`  
 Sınırlayıcı dikdörtgenini.  
  
### <a name="remarks"></a>Açıklamalar  
 Durum çubuğu üzerinde bilgi dize görünümünü özelleştirmek istiyorsanız bir türetilmiş sınıfta bu yöntemi geçersiz kılın. Kullanım [CMFCRibbonStatusBar::SetInformation](#setinformation) durum çubuğu bilgilerini moduna yöntemi. Bu mod, durum çubuğu, tüm bölmeleri gizler ve tarafından belirtilen bilgi dizesi görüntüler `strInfo`.  
  
##  <a name="recalclayout"></a>CMFCRibbonStatusBar::RecalcLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removeall"></a>CMFCRibbonStatusBar::RemoveAll  
 Şerit Durum Çubuğu'ndan tüm öğeleri kaldırır.  
  
```  
void RemoveAll();
```  
  
##  <a name="removeelement"></a>CMFCRibbonStatusBar::RemoveElement  
 Belirtilen komut kimliği Şerit durum çubuğunda olan öğeyi kaldırır.  
  
```  
BOOL RemoveElement(UINT uiID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiID`  
 Durum Çubuğu'ndan kaldırma öğenin kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`bir öğe, belirtilen `uiID` kaldırılır. `FALSE`Aksi takdirde.  
  
##  <a name="setinformation"></a>CMFCRibbonStatusBar::SetInformation  
 Etkinleştirir veya Şerit durum çubuğu bilgilerini modunu devre dışı bırakır.  
  
```  
void SetInformation(LPCTSTR lpszInfo);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszInfo`  
 Bilgi dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Durum çubuğu bilgilerini moduna için bu yöntemi kullanın. Bu mod, durum çubuğu, tüm bölmeleri gizler ve tarafından belirtilen bilgi dizesi görüntüler `lpszInfo`.  
  
 LpszInfo olduğunda `NULL`, durum çubuğu normal moduna geri döner.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)   
 [CMFCRibbonBaseElement sınıfı](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
