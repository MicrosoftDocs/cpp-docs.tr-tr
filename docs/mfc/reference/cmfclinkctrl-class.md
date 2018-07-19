---
title: CMFCLinkCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
dev_langs:
- C++
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13f411f9f50b1a498dba718b41245f8fbb7c6e79
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851593"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl sınıfı
`CMFCLinkCtrl` Sınıfı bir düğmeyi köprü olarak görüntüler ve düğme tıklandığında bağlantı hedefini çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|Belirtilen URL düğme metnini görüntüler.|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|Örtük Protokolü ayarlar (örneğin, "http:") URL'si.|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Düğme metni ya da bit eşlem içerecek şekilde düğmeyi yeniden boyutlandırır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Düğme odak dikdörtgenini çizilmeden önce framework tarafından çağırılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Türetilen bir düğmeye tıkladığınızda `CMFCLinkCtrl` sınıfı framework geçirir düğmenin URL parametresi olarak `ShellExecute` yöntemi. Ardından `ShellExecute` yöntemi URL hedefi açılır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek boyutunu ayarlama yapmayı gösteren bir `CMFCLinkCtrl` nesnesi ve bir url ve bir araç ipucunda nasıl ayarlanacağını bir `CMFCLinkCtrl` nesne. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxlinkctrl.h  
  
##  <a name="ondrawfocusrect"></a>  CMFCLinkCtrl::OnDrawFocusRect  
 Düğme odak dikdörtgenini çizilmeden önce framework tarafından çağırılır.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *rectClient*  
 Bağlantı denetimi sınırların bir dikdörtgen.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme odak dikdörtgenini çizmek için kendi kodunuzu kullanmak istediğinizde bu yöntemi yok sayın.  
  
##  <a name="seturl"></a>  CMFCLinkCtrl::SetURL  
 Belirtilen URL düğme metnini görüntüler.  
  
```  
void SetURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszURL*  
 Görüntülenecek düğme metni.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="seturlprefix"></a>  CMFCLinkCtrl::SetURLPrefix  
 Örtük Protokolü ayarlar (örneğin, "http:") URL'si.  
  
```  
void SetURLPrefix(LPCTSTR lpszPrefix);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszPrefix*  
 URL protokolü öneki.  
  
### <a name="remarks"></a>Açıklamalar  
 URL öneki ayarlamak için bu yöntemi kullanın. Önek düğmenin yüzüne görüntülenmez, ancak URL'nin hedefine Gözat yardımcı olması için kullanın.  
  
##  <a name="sizetocontent"></a>  CMFCLinkCtrl::SizeToContent  
 Düğme metni ya da bit eşlem içerecek şekilde düğmeyi yeniden boyutlandırır.  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bVCenter*  
 Düğme metni ve dikey olarak üst ve alt bağlantı denetimi arasındaki bit eşlem merkezi için TRUE; Aksi takdirde FALSE. Varsayılan değer FALSE olur.  
  
 [in] *bHCenter*  
 Düğme metni ve bit eşlem ve bağlantı denetimin sol tarafında arasındaki yatay olarak ortalamak için TRUE; Aksi takdirde FALSE. Varsayılan değer FALSE olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) yeni bağlantı denetiminin boyutunu içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl sınıfı](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton Sınıfı](../../mfc/reference/cmfcbutton-class.md)
