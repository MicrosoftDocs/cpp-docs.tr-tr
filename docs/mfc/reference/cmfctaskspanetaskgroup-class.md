---
title: "CMFCTasksPaneTaskGroup sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTaskGroup [MFC], CMFCTasksPaneTaskGroup
- CMFCTasksPaneTaskGroup [MFC], SetACCData
- CMFCTasksPaneTaskGroup [MFC], m_bIsBottom
- CMFCTasksPaneTaskGroup [MFC], m_bIsCollapsed
- CMFCTasksPaneTaskGroup [MFC], m_bIsSpecial
- CMFCTasksPaneTaskGroup [MFC], m_lstTasks
- CMFCTasksPaneTaskGroup [MFC], m_rect
- CMFCTasksPaneTaskGroup [MFC], m_rectGroup
- CMFCTasksPaneTaskGroup [MFC], m_strName
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 34bd53dec328ebf94e8bb9eb6f72aae1e8a90bc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup sınıfı
`CMFCTasksPaneTaskGroup` Bir yardımcı sınıfı tarafından kullanılan bir sınıftır [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) denetim. Nesne türü `CMFCTasksPaneTaskGroup` temsil eden bir *görev grubu*. Framework Daralt düğmesi ayrı bir kutuya görüntüler öğeleri listesi görev grubudur. Kutunun isteğe bağlı bir başlıkla (grup adı) olabilir. Bir grup daraltılmışsa, görevlerin listesi görünür değil.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCTasksPaneTaskGroup : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Oluşturan bir `CMFCTasksPaneTaskGroup` nesnesi.|  
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|Geçerli görev grubunu erişilebilirlik verileri belirler.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|Görev grubu görev bölmesinde denetim altına hizalanır olup olmadığını belirler.|  
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|Görev grubu daraltılmış olup olmadığını belirler.|  
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|Görev grubu olup olmadığını belirleyen *özel.* Framework rengi farklı bir özel resim yazıları görüntüler.|  
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|Görevleri iç listesini içerir.|  
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|Grup başlığını sınırlayıcı dikdörtgenini belirtir.|  
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|Sınırlayıcı dikdörtgenini grubunun belirtir.|  
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|Grubun adını belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki çizimde bir genişletilmiş görev grubu gösterir:  
  
 ![Görev grubu, Genişletilmiş](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")  
  
 Aşağıdaki çizimde bir daraltılmış görev grubu gösterir:  
  
 ![Daraltılmış görev grubu](../../mfc/reference/media/nexttaskgrpcollapse.png "nexttaskgrpcollapse")  
  
 Aşağıdaki resimde bir resim yazısı olmadan bir görev grubu gösterilmektedir:  
  
 ![Görev grubunun resim yazısı olmadan](../../mfc/reference/media/nexttaskgrpnocapt.png "nexttaskgrpnocapt")  
  
 Aşağıdaki çizimde iki görev gruplarını gösterir. İlk görev grubu ayarlayarak özel olarak işaretlenmiş `m_bIsSpecial` bayrağını `TRUE`, ikinci görev grubu özel değil. İlk görev grubu için resim yazısı nasıl ikinci görev grubu koyu olduğuna dikkat edin:  
  
 ![Özel görev grubu](../../mfc/reference/media/nexttaskgrpspecial.png "nexttaskgrpspecial")  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxTasksPane.h  
  
##  <a name="cmfctaskspanetaskgroup"></a>CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup  
 Oluşturan bir `CMFCTasksPaneTaskGroup` nesnesi.  
  
```  
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,  
    BOOL bIsBottom,  
    BOOL bIsSpecial=FALSE,  
    BOOL bIsCollapsed=FALSE,  
    CMFCTasksPanePropertyPage* pPage=NULL,  
    HICON hIcon=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Grup başlığını grubun adını belirtir.  
  
 `bIsBottom`  
 Grup görev bölmesinde denetim altına hizalanır olup olmadığını belirtir.  
  
 `bIsSpecial`  
 Grup olarak belirlenmiş olup olmadığını belirtir *özel* ve bu nedenle, Grup başlığını farklı bir renkle olup doldurulur.  
  
 `bIsCollapsed`  
 Grup daraltılmış olup olmadığını belirtir.  
  
 `pPage`  
 Bu görev grubun ait olduğu özellik sayfası belirtir.  
  
 `hIcon`  
 Grup başlığını görüntüler simge belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_bisbottom"></a>CMFCTasksPaneTaskGroup::m_bIsBottom  
 Görev grubu görev bölmesinde denetim altına hizalanır olup olmadığını belirler.  
  
```  
BOOL m_bIsBottom;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca bir grup görev bölmesinde denetim altına hizalanabilir. Bu görev grubu son eklenmesi gerekir. Daha fazla bilgi için bkz: [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).  
  
##  <a name="m_biscollapsed"></a>CMFCTasksPaneTaskGroup::m_bIsCollapsed  
 Görev grubu daraltılmış olup olmadığını belirler.  
  
```  
BOOL m_bIsCollapsed;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Etkinleştirmek veya grupları çağırarak görev bölmesinde daraltmak için özelliğini devre dışı [CMFCTasksPane::EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse).  
  
##  <a name="m_bisspecial"></a>CMFCTasksPaneTaskGroup::m_bIsSpecial  
 Görev grubu olup olmadığını belirleyen *özel* ve bir özel görev grubu için resim yazısı tarafından farklı bir renk tanımlanması.  
  
```  
BOOL m_bIsSpecial;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızı Windows XP görsel tema kullanıyorsa ve `m_bIsSpecial` olan `FALSE`, framework çağrıları `DrawThemeBackground` ile `EBP_NORMALGROUPBACKGROUND` bayrağı. Varsa `m_bIsSpecial` olan `TRUE`, framework çağrıları `DrawThemeBackground` ile `EBP_SPECIALGROUPBACKGROUND` bayrağı.  
  
##  <a name="m_lsttasks"></a>CMFCTasksPaneTaskGroup::m_lstTasks  
 Görevleri iç listesini içerir.  
  
```  
CObList m_lstTasks;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu listeyi doldurmak için arama [CMFCTasksPane::AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask).  
  
##  <a name="m_rect"></a>CMFCTasksPaneTaskGroup::m_rect  
 Grup başlığını sınırlayıcı dikdörtgenini belirtir.  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer çerçevesi tarafından otomatik olarak hesaplanır.  
  
##  <a name="m_rectgroup"></a>CMFCTasksPaneTaskGroup::m_rectGroup  
 Sınırlayıcı dikdörtgenini grubunun belirtir.  
  
```  
CRect m_rectGroup;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer çerçevesi tarafından otomatik olarak hesaplanır.  
  
##  <a name="m_strname"></a>CMFCTasksPaneTaskGroup::m_strName  
 Grubun adını belirtir.  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer boş ise, Grup başlığını görüntülenmez ve Grup daraltılamaz.  
  
##  <a name="setaccdata"></a>CMFCTasksPaneTaskGroup::SetACCData  
 Geçerli görev grubunu erişilebilirlik verileri belirler.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pParent`  
 Geçerli görev grubunun üst pencere temsil eder.  
  
 [out]`data`  
 Türünde bir nesne `CAccessibilityData` geçerli görev grubunu erişilebilirlik verilerle doldurulur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`varsa `data` parametresi başarıyla geçerli görev grubunun erişilebilirlik verilerle doldurulan; Aksi takdirde `FALSE`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCTasksPane sınıfı](../../mfc/reference/cmfctaskspane-class.md)   
 [CMFCTasksPaneTask sınıfı](../../mfc/reference/cmfctaskspanetask-class.md)   
 [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CObject Sınıfı](../../mfc/reference/cobject-class.md)
