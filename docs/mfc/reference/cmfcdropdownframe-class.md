---
title: "CMFCDropDownFrame sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01b3e5b56621d7bf8d42aad12e216208338bbacd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame sınıfı
Aşağı açılan araç çubukları ve aşağı açılır düğmeler aşağı açılan çerçeve penceresi işlevsellik sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`CMFCDropDownFrame::CMFCDropDownFrame`|Varsayılan Oluşturucu.|  
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCDropDownFrame::Create](#create)|Oluşturur bir `CMFCDropDownFrame` nesnesi.|  
|`CMFCDropDownFrame::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|Ana menü çubuğu açılır çerçevesinin alır.|  
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|Üst açılır menüyü aşağı açılan çerçevesinin alır.|  
|`CMFCDropDownFrame::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|Aşağı açılan çerçeve yeniden konumlandırır.|  
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|Alt açılan araç penceresi otomatik olarak yok olup olmadığını belirler.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
 Çerçeve davranışı sağlamak için bu sınıf çerçevesi kullanır `CMFCDropDownToolbar` ve `CMFCDropDownToolbarButton` sınıfları. Bu sınıfları hakkında daha fazla bilgi için bkz: [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md) ve [CMFCDropDownToolbarButton sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir işaretçi almak gösterilmiştir bir `CMFCDropDownFrame` nesnesinin bir `CFrameWnd` sınıfı ve alt açılan araç penceresi otomatik olarak yok edilmesi için ayarlama.  
  
 [!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdropdowntoolbar.h  
  
##  <a name="create"></a>CMFCDropDownFrame::Create  
 Oluşturur bir `CMFCDropDownFrame` nesnesi.  
  
```  
virtual BOOL Create(
    CWnd* pWndParent,  
    int x,  
    int y,  
    CMFCDropDownToolBar* pWndOriginToolbar);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`pWndParent`|Aşağı açılan çerçeve üst pencere.|  
|[in]`x`|Açılır çerçeve konumunu yatay Ekran koordinatı.|  
|[in]`y`|Açılır çerçeve konumunu dikey Ekran koordinatı.|  
|[in]`pWndOriginToolbar`|Bu yöntem yeni açılan çerçeve nesnesi doldurmak için kullanır aşağı açılır düğmeler sahip araç çubuğu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`aşağı açılan çerçeve başarıyla oluşturulduysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel bu yöntemi çağırır [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) ile açılan çerçeve penceresi oluşturmak için yöntemi `WS_POPUP` stili. Belirtilen ekran koordinatlarda aşağı açılan çerçeve penceresi görüntülenir. Bu yöntem başarısız olursa [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) yöntemi döndürür `FALSE`.  
  
 `CMFCDropDownFrame` Sınıfı oluşturur sağlanan bir kopyasını `CMFCDropDownToolBar` parametresi. Bu yöntem düğme resimlerini ve düğmesi durumlar kopyalar `pWndOriginToolbar` parametresi `m_pWndOriginToolbar` veri üyesi.  
  
##  <a name="getparentmenubar"></a>CMFCDropDownFrame::GetParentMenuBar  
 Ana menü çubuğu açılır çerçevesinin alır.  
  
```  
CMFCMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ana menü çubuğu açılır çerçevenin gösteren bir işaretçi veya `NULL` çerçeve üst öğeye sahipse.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem üst düğmesinden üst menü çubuğu alır. Bu yöntem `NULL` açılan çerçeve üst düğmesi ya hiç üst menü çubuğu üst düğmesi bulunur.  
  
##  <a name="getparentpopupmenu"></a>CMFCDropDownFrame::GetParentPopupMenu  
 Üst açılır menüyü aşağı açılan çerçevesinin alır.  
  
```  
CMFCDropDownFrame* GetParentPopupMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üst açılır menü açılan çerçeve işaretçisi veya `NULL` çerçeve üst öğeye sahipse.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem üst düğmesinden üst menü alır. Bu yöntem `NULL` açılan çerçeve üst düğmesi ya hiç üst menüsünde üst düğmesi vardır.  
  
##  <a name="recalclayout"></a>CMFCDropDownFrame::RecalcLayout  
 Aşağı açılan çerçeve yeniden konumlandırır.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`bNotify`|Kullanılmayan.|  
  
### <a name="remarks"></a>Açıklamalar  
 Framework açılan çerçeve oluşturulduğunda veya üst pencere boyutlandırılır bu yöntemi çağırır. Bu yöntem, üst pencere boyutunu ve konumunu kullanarak açılan çerçevesinin boyutunu ve konumunu hesaplar.  
  
##  <a name="setautodestroy"></a>CMFCDropDownFrame::SetAutoDestroy  
 Alt açılan araç penceresi otomatik olarak yok olup olmadığını belirler.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bAutoDestroy`  
 `TRUE`otomatik olarak ilişkili açılan araç penceresi yok etmek için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bAutoDestroy` olan `TRUE`, sonra `CMFCDropDownFrame` yıkıcı ilişkili açılan araç penceresi yok eder. Varsayılan değer `TRUE` şeklindedir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar sınıfı](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCDropDownToolbarButton Sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
