---
title: "CMFCMenuButton sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuButton [MFC], CMFCMenuButton
- CMFCMenuButton [MFC], PreTranslateMessage
- CMFCMenuButton [MFC], SizeToContent
- CMFCMenuButton [MFC], m_bOSMenu
- CMFCMenuButton [MFC], m_bRightArrow
- CMFCMenuButton [MFC], m_bStayPressed
- CMFCMenuButton [MFC], m_hMenu
- CMFCMenuButton [MFC], m_nMenuResult
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fac8fe59fe5dbfb101ec0881dbf17925cf048caa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton sınıfı
Açılır menü görüntüler ve kullanıcının menü seçimlere raporları bir düğme.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|Oluşturan bir `CMFCMenuButton` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|Bunlar gönderilir önce pencere iletileri çevirmek için çerçevesi tarafından çağrılır. (Geçersiz kılmaları `CMFCButton::PreTranslateMessage`.)|  
|[CMFCMenuButton::SizeToContent](#sizetocontent)|Metin ve görüntü boyutuna göre düğmesi boyutunu değiştirir.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|Varsayılan sistem açılır menüsünü görüntüleme mi, yoksa kullanılacağını belirtir [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).|  
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|Açılır menüsünün altında veya düğmesinin görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|Kullanıcı düğmesi yayımlandıktan sonra menü düğmesi durumuna değişikliklerinin olup olmadığını belirtir.|  
|[CMFCMenuButton::m_hMenu](#m_hmenu)|Ekli Windows menüsü için bir tanıtıcı.|  
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|Seçilen kullanıcı açılır menüden hangi öğeyi belirten bir tanımlayıcı.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCMenuButton` Sınıfı türetilir [CMFCButton sınıfı](../../mfc/reference/cmfcbutton-class.md) buna karşılık, türetilen [CButton sınıfı](../../mfc/reference/cbutton-class.md). Bu nedenle, kullanabileceğiniz `CMFCMenuButton` kodunuzda kullandığınız aynı gibi `CButton`.  
  
 Oluştururken bir `CMFCMenuButton`, ilişkili açılır menü için bir tanıtıcı geçmesi gerekir. Ardından, bir işlevi çağırmak `CMFCMenuButton::SizeToContent`. `CMFCMenuButton::SizeToContent`düğme boyutu nerede açılır pencere - yani, altında veya düğmesinin görüneceğini konumuna işaret eden bir ok dahil etmek yeterli olup olmadığını denetler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, düğmesine iliştirilmiş menü tanıtıcısı, düğme metin ve görüntü boyutuna göre yeniden boyutlandır ve çerçevesi tarafından görüntülenen açılır menüde ayarlayın gösterilmiştir. Bu kod parçacığını parçası olan [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmenubutton.h  
  
##  <a name="cmfcmenubutton"></a>CMFCMenuButton::CMFCMenuButton  
 Yeni bir oluşturur [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) nesnesi.  
  
```  
CMFCMenuButton();
```  
  
##  <a name="m_bosmenu"></a>CMFCMenuButton::m_bOSMenu  
 Hangi açılır menü gösteren bir Boole üye değişkeni framework görüntüler.  
  
```  
BOOL m_bOSMenu;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `m_bOSMenu` olan `TRUE`, framework devralınan çağırması `TrackPopupMenu` bu nesne için yöntem. Aksi takdirde, framework çağırması [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).  
  
##  <a name="m_brightarrow"></a>CMFCMenuButton::m_bRightArrow  
 Açılır menü konumunu belirten bir Boolean üye değişkeni.  
  
```  
BOOL m_bRightArrow;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı menü düğmesi bastığında uygulama açılır menü gösterir. Framework açılır menü düğmesinin altındaki veya düğmesinin sağa görüntüler. Düğme da açılan menüden nerede görüneceğini belirtir küçük bir ok sahiptir. Varsa `m_bRightArrow` olan `TRUE`, framework açılır menü düğmesinin sağa görüntüler. Aksi takdirde, bu açılır menü düğmesinin altındaki görüntüler.  
  
##  <a name="m_bstaypressed"></a>CMFCMenuButton::m_bStayPressed  
 Kullanıcı açılır menüsünden bir seçim olmasını sağlarken menü düğmesi görünür olup olmadığını gösteren bir Boole üye değişkeni basılı.  
  
```  
BOOL m_bStayPressed;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `m_bStayPressed` üye `FALSE`, menü düğmesi ne zaman basılı hale değil kullandığı düğmesine tıklar. Bu durumda, framework yalnızca açılır menüsünü görüntüler.  
  
 Varsa `m_bStayPressed` üye `TRUE`, kullanıcı düğmesini tıklattığında menü düğmesine basıldığında haline gelir. Kullanıcı açılır menüsünde, bir seçim yaparak veya iptal etme kapandıktan sonra kadar basılı kalır.  
  
##  <a name="m_hmenu"></a>CMFCMenuButton::m_hMenu  
 Ekli menüsüne işleci.  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Framework'te kullanıcı menü düğmesine tıkladığında bu üye değişkeni tarafından belirtilen menüsünü görüntüler.  
  
##  <a name="m_nmenuresult"></a>CMFCMenuButton::m_nMenuResult  
 Hangi öğeyi belirten bir tamsayı, açılır menüden kullanıcı seçer.  
  
```  
int m_nMenuResult;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye değişkeni sıfır seçim yapmadan kullanıcı menü iptal ederse veya bir hata oluşursa değeri.  
  
##  <a name="pretranslatemessage"></a>CMFCMenuButton::PreTranslateMessage  
 Bunlar gönderilir önce pencere iletileri çevirmek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pMsg`  
 İşaret eden bir [MSG](../../mfc/reference/msg-structure1.md) işlemek için ileti içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti çevrilmiştir ve değil dağıtılması, sıfır olmayan; 0 ileti değil çevrilmiştir ve dağıtılması.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sizetocontent"></a>CMFCMenuButton::SizeToContent  
 Görüntü boyutu ve metin boyutu göre düğmesi boyutunu değiştirir.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bCalcOnly`  
 Bu yöntem düğmesini yeniden boyutlandırır olup olmadığını gösteren bir Boole parametresi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) nesne düğme için yeni boyutunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev çağırırsanız ve `bCalcOnly` olan `TRUE`, `SizeToContent` düğmenin yalnızca yeni boyutunu hesaplar.  
  
 Düğmenin yeni boyutunu düğmesi metin, görüntü ve ok uyacak şekilde hesaplanır. Framework da yatay bir kenar için 10 piksel ve 5 piksel dikey bir kenar için önceden tanımlanmış kenar boşluklarını ekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCButton Sınıfı](../../mfc/reference/cmfcbutton-class.md)
