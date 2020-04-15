---
title: CMFCTasksPaneTask Sınıfı
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
ms.openlocfilehash: 49fccdf161da7deb1fd88a12a107df40bafdae92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375863"
---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask Sınıfı

Sınıf, `CMFCTasksPaneTask` görev bölmedenetimi [(CMFCTasksPane)](../../mfc/reference/cmfctaskspane-class.md)görevlerini temsil eden yardımcı sınıftır. Görev nesnesi görev grubundaki bir öğeyi temsil eder ( [CMFCTasksPaneTaskGroup).](../../mfc/reference/cmfctaskspanetaskgroup-class.md) Her görev, bir kullanıcı görevi tıklattığında çerçevenin yürüttüğü bir komuta ve görev adının solunda görünen bir simgeye sahip olabilir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCTasksPaneTask : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|Bir `CMFCTasksPaneTask` nesne oluşturur ve başharfe bleştirir.|
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|Geçerli görevin erişilebilirlik verilerini belirler.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|Görev penceresinin otomatik olarak yok edilip edilemeyeceğini belirler.|
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|Çerçevenin kalın metinde görev etiketi çizip çizmeyeceğini belirler.|
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|Çerçevenin görevle ilişkilendirdiği kullanıcı tanımlı verileri içerir. Görevin ilişkili verisi yoksa sıfırolarak ayarlayın.|
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|Görev penceresine bir tanıtıcı.|
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|Çerçevenin görevin yanında görüntülenebilen görüntü listesindeki dizin.|
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|Görev penceresinin yüksekliği. Görev penceresi yoksa, bu değer sıfırdır.|
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|Bu görevin `CMFCTasksPaneTaskGroup` ait olduğu işaretçi.|
|[CMFCTasksPaneTask::m_rect](#m_rect)|Görevin sınırlayıcı dikdörtgenini belirtir.|
|[CMFCTasksPaneTask::m_strName](#m_strname)|Görevin adı.|
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|Kullanıcı görevi tıklattığında çerçevenin yürüttüğü komutun komut kimliğini belirtir. Bu değer geçerli bir komut kimliği değilse, görev basit bir etiket olarak kabul edilir.|

## <a name="remarks"></a>Açıklamalar

Aşağıdaki resimde üç görev içeren bir görev grubu gösterilmektedir:

![Görev grubu, genişletilmiş](../../mfc/reference/media/nexttaskgrpexpand.png "Görev grubu, genişletilmiş")

> [!NOTE]
> Bir görevin geçerli bir komut kimliği yoksa, basit bir etiket olarak kabul edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxTasksPane.h

## <a name="cmfctaskspanetaskcmfctaskspanetask"></a><a name="cmfctaskspanetask"></a>CMFCTasksPaneTask::CMFCTasksPaneTask

Bir `CMFCTasksPaneTask` nesne oluşturur ve başharfe bleştirir.

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
Görevin ait olduğu [CMFCTasksPaneTaskGroup'u](../../mfc/reference/cmfctaskspanetaskgroup-class.md) belirtir.

*Lpszname*<br/>
Görevin adını belirtir.

*nIcon*<br/>
Resim listesinde görevin resminin dizinini belirtir.

*uiCommandID*<br/>
Görev tıklatıldığında yürütülen komutun komut kimliğini belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı veriler.

*hwndTask*<br/>
Tutamacı görev penceresine belirtir.

*bAutoDestroyWindow*<br/>
TRUE ise, görev penceresi otomatik olarak yok edilir.

*nWindowHeight*<br/>
Görev penceresinin yüksekliğini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetaskm_bautodestroywindow"></a><a name="m_bautodestroywindow"></a>CMFCTasksPaneTask::m_bAutoDestroyWindow

Görev penceresinin otomatik olarak yok edilip edilemeyeceğini belirler.

```
BOOL m_bAutoDestroyWindow;
```

### <a name="remarks"></a>Açıklamalar

Görev penceresinin [(CMFCTasksPaneTask::m_hwndTask)](#m_hwndtask)otomatik olarak yok edilmesi gerektiğini belirtmek için TRUE olarak ayarlayın; aksi takdirde, YANLIŞ.

## <a name="cmfctaskspanetaskm_bisbold"></a><a name="m_bisbold"></a>CMFCTasksPaneTask::m_bIsBold

Görev etiketinin kalın metinde çizilip çizilmediğini belirler.

```
BOOL m_bIsBold;
```

### <a name="remarks"></a>Açıklamalar

Görev etiketi için kalın metin görüntülemek için bu üyeyi TRUE olarak ayarlayın.

## <a name="cmfctaskspanetaskm_dwuserdata"></a><a name="m_dwuserdata"></a>CMFCTasksPaneTask::m_dwUserData

Görevle ilişkili kullanıcı tanımlı verileri içerir. Görevle ilişkili veri yoksa sıfıra ayarlayın.

```
DWORD m_dwUserData;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetaskm_hwndtask"></a><a name="m_hwndtask"></a>CMFCTasksPaneTask::m_hwndTask

Görev penceresine bir tanıtıcı.

```
HWND m_hwndTask;
```

### <a name="remarks"></a>Açıklamalar

Görev penceresi eklemek için [CMFCTasksPane'yi arayın::AddWindow.](../../mfc/reference/cmfctaskspane-class.md#addwindow)

## <a name="cmfctaskspanetaskm_nicon"></a><a name="m_nicon"></a>CMFCTasksPaneTask::m_nIcon

Belirtilen görevin yanında görüntülenen bir görüntüyü tanımlayan bir resim listesindeki dizin konumu.

```
int m_nIcon;
```

### <a name="remarks"></a>Açıklamalar

Resim listesi [CMFCTasksPane tarafından ayarlanır::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist).

Görevi `m_nIcon` görüntü olmadan görüntülemek istiyorsanız -1 olarak ayarlayın.

## <a name="cmfctaskspanetaskm_nwindowheight"></a><a name="m_nwindowheight"></a>CMFCTasksPaneTask::m_nWindowHeight

Görev penceresinin yüksekliği. Görev penceresi yoksa, bu değer sıfırdır.

```
int m_nWindowHeight;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetaskm_pgroup"></a><a name="m_pgroup"></a>CMFCTasksPaneTask::m_pGroup

Bu görevin ait olduğu [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) işaretçisi.

```
CMFCTasksPaneTaskGroup* m_pGroup;
```

### <a name="remarks"></a>Açıklamalar

Her görevin bir üst grubu olmalıdır. [CMFCTasksPane:AddGroup'u](../../mfc/reference/cmfctaskspane-class.md#addgroup)arayarak görev bölmesine gruplar eklersiniz.

## <a name="cmfctaskspanetaskm_rect"></a><a name="m_rect"></a>CMFCTasksPaneTask::m_rect

Görevin sınırlayıcı dikdörtgenini belirtir.

```
CRect m_rect;
```

### <a name="remarks"></a>Açıklamalar

Bu değer, görev çizildiğinde çerçeve tarafından hesaplanır.

## <a name="cmfctaskspanetaskm_strname"></a><a name="m_strname"></a>CMFCTasksPaneTask::m_strName

Görevin adı.

```
CString m_strName;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetaskm_uicommandid"></a><a name="m_uicommandid"></a>CMFCTasksPaneTask::m_uiCommandID

Kullanıcı görevi tıklattığında çalıştırılan komutun komut kimliğini belirtir. Bu değer geçerli bir komut kimliği değilse, görev basit bir etiket olarak kabul edilir.

```
UINT m_uiCommandID;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetasksetaccdata"></a><a name="setaccdata"></a>CMFCTasksPaneTask::SetACCData

Geçerli görevin erişilebilirlik verilerini belirler.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
[içinde] Geçerli görevin üst penceresini temsil eder.

*Veri*<br/>
[çıkış] Geçerli görevin `CAccessibilityData` erişilebilirlik verileriyle doldurulan tür nesnesi.

### <a name="return-value"></a>Dönüş Değeri

*Veri* parametresi geçerli görevin erişilebilirlik verileriyle başarıyla doldurulduysa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)
