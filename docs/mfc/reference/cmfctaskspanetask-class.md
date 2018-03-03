---
title: "CMFCTasksPaneTask sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTask::m_bAutoDestroyWindow
- AFXTASKSPANE/CMFCTasksPaneTask::m_bIsBold
- AFXTASKSPANE/CMFCTasksPaneTask::m_dwUserData
- AFXTASKSPANE/CMFCTasksPaneTask::m_hwndTask
- AFXTASKSPANE/CMFCTasksPaneTask::m_nIcon
- AFXTASKSPANE/CMFCTasksPaneTask::m_nWindowHeight
- AFXTASKSPANE/CMFCTasksPaneTask::m_pGroup
- AFXTASKSPANE/CMFCTasksPaneTask::m_rect
- AFXTASKSPANE/CMFCTasksPaneTask::m_strName
- AFXTASKSPANE/CMFCTasksPaneTask::m_uiCommandID
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTask [MFC], CMFCTasksPaneTask
- CMFCTasksPaneTask [MFC], SetACCData
- CMFCTasksPaneTask [MFC], m_bAutoDestroyWindow
- CMFCTasksPaneTask [MFC], m_bIsBold
- CMFCTasksPaneTask [MFC], m_dwUserData
- CMFCTasksPaneTask [MFC], m_hwndTask
- CMFCTasksPaneTask [MFC], m_nIcon
- CMFCTasksPaneTask [MFC], m_nWindowHeight
- CMFCTasksPaneTask [MFC], m_pGroup
- CMFCTasksPaneTask [MFC], m_rect
- CMFCTasksPaneTask [MFC], m_strName
- CMFCTasksPaneTask [MFC], m_uiCommandID
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b64f1efd16a1ac372f6e8ce9ea9e0781046f1892
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask sınıfı
`CMFCTasksPaneTask` Sınıftır görev bölmesi denetimi için görevleri temsil eden bir yardımcı sınıfı ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)). Görev nesnesini görev grubundaki bir öğeyi temsil eder ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). Her görev, bir kullanıcı görev ve görev adı solunda görüntülenen simge tıkladığında framework yürüten bir komutu olabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|Oluşturur ve başlatır bir `CMFCTasksPaneTask` nesnesi.|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|Geçerli görev için erişilebilirlik verileri belirler.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|Görev penceresi otomatik olarak yok olup olmadığını belirler.|  
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|Framework kalın metin olarak görev etiketi çizer olup olmadığını belirler.|  
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|Çerçeve olan görev ilişkilendirir kullanıcı tanımlı veri içerir. Görev ilişkili veri varsa sıfır olarak ayarlayın.|  
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|Görev penceresi için bir tanıtıcı.|  
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|Görev yanındaki framework görüntüler görüntünün görüntü listesinde dizini.|  
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|Görev penceresi yüksekliği. Görev görev pencere varsa, bu değer sıfır olur.|  
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|Bir işaretçi `CMFCTasksPaneTaskGroup` bu görevin ait olduğu.|  
|[CMFCTasksPaneTask::m_rect](#m_rect)|Görevin sınırlayıcı dikdörtgenini belirtir.|  
|[CMFCTasksPaneTask::m_strName](#m_strname)|Görev adı.|  
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|Kullanıcı görevi tıklattığında framework yürütür komutu komut Kimliğini belirtir. Bu değer geçerli bir komut kimliği değilse, görev basit bir etiket olarak kabul edilir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki çizim üç görevler içeren bir görev grubu gösterir:  
  
 ![Görev grubu, Genişletilmiş](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")  
  
> [!NOTE]
>  Bir görev geçerli bir komut kimliği sahip değilse basit bir etiket olarak kabul edilir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxTasksPane.h  
  
##  <a name="cmfctaskspanetask"></a>CMFCTasksPaneTask::CMFCTasksPaneTask  
 Oluşturur ve başlatır bir `CMFCTasksPaneTask` nesnesi.  
  
```  
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,  
    LPCTSTR lpszName,  
    int nIcon,  
    UINT uiCommandID,  
    DWORD dwUserData = 0,  
    HWND hwndTask = NULL,  
    BOOL bAutoDestroyWindow = FALSE,  
    int nWindowHeight = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `pGroup`  
 Belirtir [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) görevin ait olduğu.  
  
 `lpszName`  
 Görev adını belirtir.  
  
 `nIcon`  
 Görüntü listesinde görevin görüntünün dizinini belirtir.  
  
 `uiCommandID`  
 Görev tıklatıldığında çalıştırılan komut komut Kimliğini belirtir.  
  
 `dwUserData`  
 Kullanıcı tanımlı veri.  
  
 `hwndTask`  
 Görev penceresi tanıtıcısını belirtir.  
  
 `bAutoDestroyWindow`  
 Varsa `TRUE`, görev penceresi otomatik olarak yok.  
  
 `nWindowHeight`  
 Görev penceresinin yüksekliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_bautodestroywindow"></a>CMFCTasksPaneTask::m_bAutoDestroyWindow  
 Görev penceresi otomatik olarak yok olup olmadığını belirler.  
  
```  
BOOL m_bAutoDestroyWindow;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kümesine `TRUE` belirtmek için görev penceresi ( [CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)) yok edilmesi otomatik olarak; tersi durumda, `FALSE`.  
  
##  <a name="m_bisbold"></a>CMFCTasksPaneTask::m_bIsBold  
 Bir görev etiketi kalın metin olarak çizilip çizilmeyeceğini belirler.  
  
```  
BOOL m_bIsBold;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye kümesine `TRUE` kalın metin görev etiketi için görüntülenecek.  
  
##  <a name="m_dwuserdata"></a>CMFCTasksPaneTask::m_dwUserData  
 Görev ile ilişkili kullanıcı tanımlı veri içerir. Hiçbir veri görev ile ilişkili ise sıfır olarak ayarlayın.  
  
```  
DWORD m_dwUserData;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_hwndtask"></a>CMFCTasksPaneTask::m_hwndTask  
 Görev penceresi için bir tanıtıcı.  
  
```  
HWND m_hwndTask;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir görev pencere eklemek için arama [CMFCTasksPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow).  
  
##  <a name="m_nicon"></a>CMFCTasksPaneTask::m_nIcon  
 Belirtilen görev yanında görüntülenen görüntünün tanımlayan bir resim listesi dizin konumu.  
  
```  
int m_nIcon;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Resim listesi belirlediği [CMFCTasksPane::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist).  
  
 Ayarlama `m_nIcon` görüntü olmadan görevi görüntülemek istiyorsanız,-1.  
  
##  <a name="m_nwindowheight"></a>CMFCTasksPaneTask::m_nWindowHeight  
 Görev penceresi yüksekliği. Görev görev pencere varsa, bu değer sıfır olur.  
  
```  
int m_nWindowHeight;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_pgroup"></a>CMFCTasksPaneTask::m_pGroup  
 İşaretçi [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) bu görevin ait olduğu.  
  
```  
CMFCTasksPaneTaskGroup* m_pGroup;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her görev, bir üst grubu olmalıdır. Çağırarak grupları için bir görev bölmesi ekleme [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).  
  
##  <a name="m_rect"></a>CMFCTasksPaneTask::m_rect  
 Görevin sınırlayıcı dikdörtgenini belirtir.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer, görev çizildiğinde çerçevesi tarafından hesaplanır.  
  
##  <a name="m_strname"></a>CMFCTasksPaneTask::m_strName  
 Görev adı.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_uicommandid"></a>CMFCTasksPaneTask::m_uiCommandID  
 Kullanıcı görevi tıklattığında çalıştırılan komut komut Kimliğini belirtir. Bu değer geçerli bir komut kimliği değilse, görev basit bir etiket olarak kabul edilir.  
  
```  
UINT m_uiCommandID;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setaccdata"></a>CMFCTasksPaneTask::SetACCData  
 Geçerli görev için erişilebilirlik verileri belirler.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pParent`  
 Geçerli görevin üst pencere temsil eder.  
  
 [out]`data`  
 Türünde bir nesne `CAccessibilityData` geçerli görev erişilebilirlik verilerle doldurulur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa `data` parametresi başarıyla geçerli görevin erişilebilirlik verilerle doldurulan; Aksi takdirde `FALSE`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CObject Sınıfı](../../mfc/reference/cobject-class.md)
