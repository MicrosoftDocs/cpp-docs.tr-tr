---
title: CMFCTasksPaneTask sınıfı
ms.date: 11/19/2018
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
ms.openlocfilehash: 95a2e4f2a1f2e3344936af33fb2258b496b1be93
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279256"
---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask sınıfı

`CMFCTasksPaneTask` Görev bölmesi denetimi için görevleri temsil eden bir yardımcı sınıfı ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)). Görev nesnesi görev grubundaki bir öğeyi temsil eder ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). Her görev bir kullanıcı görevi ve görev adının solunda görüntülenen simge tıkladığında framework yürüten bir komut içerebilir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCTasksPaneTask : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|Oluşturur ve başlatır bir `CMFCTasksPaneTask` nesne.|
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|Geçerli görev için erişilebilirlik verileri belirler.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|Görev penceresi otomatik olarak edildiğinde olup olmadığını belirler.|
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|Framework kalın metin olarak görev etiketi çizer olup olmadığını belirler.|
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|Framework görev ile ilişkilendirir ve kullanıcı tanımlı veri içerir. Görevin ilişkili veri yoksa sıfır olarak ayarlayın.|
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|Görev penceresi için bir tanıtıcı.|
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|Görüntü listesi framework yanındaki görev görüntüler görüntünün dizin.|
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|Görev penceresi yüksekliği. Görev hiçbir görev penceresi varsa, bu değeri sıfırdır.|
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|Bir işaretçi `CMFCTasksPaneTaskGroup` bu görevin ait olduğu.|
|[CMFCTasksPaneTask::m_rect](#m_rect)|Görev sınırlayıcı dikdörtgenini belirtir.|
|[CMFCTasksPaneTask::m_strName](#m_strname)|Görev adı.|
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|Kullanıcı görevi tıkladığında framework yürütür komutu komut Kimliğini belirtir. Bu değer, geçerli komut kimliği değil, görev basit bir etiket olarak kabul edilir.|

## <a name="remarks"></a>Açıklamalar

Aşağıdaki çizim üç görev içeren bir görev grubunu gösterir:

![Görev grubu, Genişletilmiş](../../mfc/reference/media/nexttaskgrpexpand.png "görev grubu, genişletilmiş")

> [!NOTE]
> Bir görev geçerli komut kimliği yoksa, basit bir etiket olarak kabul edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxTasksPane.h

##  <a name="cmfctaskspanetask"></a>  CMFCTasksPaneTask::CMFCTasksPaneTask

Oluşturur ve başlatır bir `CMFCTasksPaneTask` nesne.

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

*pGroup*<br/>
Belirtir [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) görevin ait olduğu.

*lpszName*<br/>
Görev adını belirtir.

*nIcon*<br/>
Görüntü listesinden görevin görüntünün dizinini belirtir.

*uiCommandID*<br/>
Görev tıklandığında çalıştırılan komut komut Kimliğini belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı veri.

*hwndTask*<br/>
Görev penceresi için bir tanıtıcı belirtir.

*bAutoDestroyWindow*<br/>
TRUE ise görev penceresi otomatik olarak yok edilir.

*nWindowHeight*<br/>
Görev pencerenin yüksekliğini belirtir.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_bautodestroywindow"></a>  CMFCTasksPaneTask::m_bAutoDestroyWindow

Görev penceresi otomatik olarak edildiğinde olup olmadığını belirler.

```
BOOL m_bAutoDestroyWindow;
```

### <a name="remarks"></a>Açıklamalar

Görev penceresi belirtmek için TRUE olarak ayarlayın ( [CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)) yok otomatik olarak; Aksi takdirde FALSE.

##  <a name="m_bisbold"></a>  CMFCTasksPaneTask::m_bIsBold

Bir görev etiketi kalın metin olarak çizilip çizilmeyeceğini belirler.

```
BOOL m_bIsBold;
```

### <a name="remarks"></a>Açıklamalar

Görev etiket metnini görüntüle true kalın bu üyeyi ayarlayın.

##  <a name="m_dwuserdata"></a>  CMFCTasksPaneTask::m_dwUserData

Görev ile ilişkili kullanıcı tanımlı veri içerir. Veri görev ile ilişkili ise sıfır olarak ayarlayın.

```
DWORD m_dwUserData;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_hwndtask"></a>  CMFCTasksPaneTask::m_hwndTask

Görev penceresi için bir tanıtıcı.

```
HWND m_hwndTask;
```

### <a name="remarks"></a>Açıklamalar

Bir görev penceresi eklemek için arama [CMFCTasksPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow).

##  <a name="m_nicon"></a>  CMFCTasksPaneTask::m_nIcon

Belirtilen görev yanında görüntülenen görüntüyü tanımlayan bir görüntü listesi dizin konumu.

```
int m_nIcon;
```

### <a name="remarks"></a>Açıklamalar

Görüntü listesi belirlediği [CMFCTasksPane::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist).

Ayarlama `m_nIcon` görevi görüntü olmadan görüntülemek istiyorsanız,-1.

##  <a name="m_nwindowheight"></a>  CMFCTasksPaneTask::m_nWindowHeight

Görev penceresi yüksekliği. Görev hiçbir görev penceresi varsa, bu değeri sıfırdır.

```
int m_nWindowHeight;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_pgroup"></a>  CMFCTasksPaneTask::m_pGroup

İşaretçi [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) bu görevin ait olduğu.

```
CMFCTasksPaneTaskGroup* m_pGroup;
```

### <a name="remarks"></a>Açıklamalar

Her görev, bir üst grubu olmalıdır. Çağırarak grup için bir görev bölmesi ekleme [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).

##  <a name="m_rect"></a>  CMFCTasksPaneTask::m_rect

Görev sınırlayıcı dikdörtgenini belirtir.

```
CRect m_rect;
```

### <a name="remarks"></a>Açıklamalar

Bu değer, görev çizildiğinde framework tarafından hesaplanır.

##  <a name="m_strname"></a>  CMFCTasksPaneTask::m_strName

Görev adı.

```
CString m_strName;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="m_uicommandid"></a>  CMFCTasksPaneTask::m_uiCommandID

Kullanıcı görevi tıkladığında çalıştırılan komut komut Kimliğini belirtir. Bu değer, geçerli komut kimliği değil, görev basit bir etiket olarak kabul edilir.

```
UINT m_uiCommandID;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="setaccdata"></a>  CMFCTasksPaneTask::SetACCData

Geçerli görev için erişilebilirlik verileri belirler.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
[in] Geçerli görevin ana pencereyi temsil eder.

*Veri*<br/>
[out] Bir nesne türü `CAccessibilityData` geçerli görev erişilebilirlik verilerle doldurulur.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise *veri* parametre başarıyla geçerli görevin erişilebilirlik verilerle doldurulmuş; Aksi takdirde FALSE.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)
