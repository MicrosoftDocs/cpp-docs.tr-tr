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
ms.openlocfilehash: b91bc8fec3eebba5f3037633b5840d9b1abca731
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371734"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl sınıfı
`CMFCLinkCtrl` Sınıfı düğmesine tıklandığında bağlantının hedef çağırır ve bir düğme köprü olarak görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|Belirtilen URL düğme metni görüntüler.|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|Örtük Protokolü ayarlar (örneğin, "http:") URL'si.|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Düğme metni veya bit eşlem içeren için düğmesini yeniden boyutlandırır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Düğmenin odak dikdörtgeni çizilmeden önce çerçevesi tarafından çağrılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Türetilmiş bir düğmeyi tıkladığınızda `CMFCLinkCtrl` sınıfı, framework geçirir düğmesi URL'sini parametre olarak `ShellExecute` yöntemi. Ardından `ShellExecute` yöntemi açılır URL hedefi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek boyutunu ayarlamak nasıl gösteren bir `CMFCLinkCtrl` nesne ve bir url ve bir araç ipucunda nasıl ayarlanacağını bir `CMFCLinkCtrl` nesnesi. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
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
 Düğmenin odak dikdörtgeni çizilmeden önce çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rectClient`  
 Bağlantı denetimi bounds dikdörtgen.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğmenin odak dikdörtgen çizmek için kendi kodunuzu kullanmak istediğinizde bu yöntemi geçersiz kılın.  
  
##  <a name="seturl"></a>  CMFCLinkCtrl::SetURL  
 Belirtilen URL düğme metni görüntüler.  
  
```  
void SetURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszURL`  
 Görüntülenecek düğme metni.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="seturlprefix"></a>  CMFCLinkCtrl::SetURLPrefix  
 Örtük Protokolü ayarlar (örneğin, "http:") URL'si.  
  
```  
void SetURLPrefix(LPCTSTR lpszPrefix);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszPrefix`  
 URL protokolü öneki.  
  
### <a name="remarks"></a>Açıklamalar  
 URL öneki ayarlamak için bu yöntemi kullanın. Önek düğme yüzü üzerinde görüntülenmez, ancak URL'nin hedefe Gözat yardımcı olması için kullanın.  
  
##  <a name="sizetocontent"></a>  CMFCLinkCtrl::SizeToContent  
 Düğme metni veya bit eşlem içeren için düğmesini yeniden boyutlandırır.  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bVCenter`  
 `TRUE` Düğme metni ve dikey olarak üst ve alt bağlantı denetimi arasında bit eşlem center için; Aksi takdirde `FALSE`. Varsayılan değer `FALSE` şeklindedir.  
  
 [in] `bHCenter`  
 `TRUE` Düğme metni ve bit eşlem yatay sol ve sağ kenarlarının bağlantı denetimi arasında center için; Aksi takdirde `FALSE`. Varsayılan değer `FALSE` şeklindedir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) bağlantı denetimi yeni boyutunu içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl sınıfı](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton Sınıfı](../../mfc/reference/cmfcbutton-class.md)
