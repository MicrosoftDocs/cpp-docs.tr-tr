---
description: 'Daha fazla bilgi edinin: CMFCTasksPaneTask sınıfı'
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
ms.openlocfilehash: 8dad8520c938cae655143464189897d216a5f3ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306774"
---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask sınıfı

`CMFCTasksPaneTask`Sınıfı, görev bölmesi denetimine yönelik görevleri temsil eden bir yardımcı sınıftır ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)). Görev nesnesi, görev grubundaki bir öğeyi temsil eder ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). Her görev, bir kullanıcı görevi tıklattığında ve görev adının solunda görüntülenen bir simgenin bulunduğu bir komuta sahip olabilir.

## <a name="syntax"></a>Syntax

```
class CMFCTasksPaneTask : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTask:: CMFCTasksPaneTask](#cmfctaskspanetask)|Bir nesne oluşturur ve başlatır `CMFCTasksPaneTask` .|
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTask:: SetACCData](#setaccdata)|Geçerli görev için erişilebilirlik verilerini belirler.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTask:: m_bAutoDestroyWindow](#m_bautodestroywindow)|Görev penceresinin otomatik olarak yok edilip edilmeyeceğini belirler.|
|[CMFCTasksPaneTask:: m_bIsBold](#m_bisbold)|Çerçevenin kalın metinde bir görev etiketi çizip çizmediğini belirler.|
|[CMFCTasksPaneTask:: m_dwUserData](#m_dwuserdata)|Framework 'ün görevle ilişkilendiğini Kullanıcı tanımlı verileri içerir. Görevin ilişkili verileri yoksa sıfır olarak ayarlayın.|
|[CMFCTasksPaneTask:: m_hwndTask](#m_hwndtask)|Görev penceresine yönelik bir tanıtıcı.|
|[CMFCTasksPaneTask:: m_nIcon](#m_nicon)|Çerçevenin, görevin yanında gösterdiği görüntünün görüntü listesindeki dizin.|
|[CMFCTasksPaneTask:: m_nWindowHeight](#m_nwindowheight)|Görev penceresinin yüksekliği. Görevin görev penceresi yoksa, bu değer sıfırdır.|
|[CMFCTasksPaneTask:: m_pGroup](#m_pgroup)|`CMFCTasksPaneTaskGroup`Bu görevin ait olduğu bir işaretçi.|
|[CMFCTasksPaneTask:: m_rect](#m_rect)|Görevin sınırlayıcı dikdörtgenini belirtir.|
|[CMFCTasksPaneTask:: m_strName](#m_strname)|Görevin adı.|
|[CMFCTasksPaneTask:: m_uiCommandID](#m_uicommandid)|Kullanıcı göreve tıkladığında Framework 'ün çalıştırdığı komutun komut KIMLIĞINI belirtir. Bu değer geçerli bir komut KIMLIĞI değilse, görev basit bir etiket olarak değerlendirilir.|

## <a name="remarks"></a>Açıklamalar

Aşağıdaki çizimde üç görev içeren bir görev grubu gösterilmektedir:

![Görev grubu, genişletilmiş](../../mfc/reference/media/nexttaskgrpexpand.png "Görev grubu, genişletilmiş")

> [!NOTE]
> Bir görevin geçerli bir komut KIMLIĞI yoksa, bu bir basit etiket olarak kabul edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxTasksPane. h

## <a name="cmfctaskspanetaskcmfctaskspanetask"></a><a name="cmfctaskspanetask"></a> CMFCTasksPaneTask:: CMFCTasksPaneTask

Bir nesne oluşturur ve başlatır `CMFCTasksPaneTask` .

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
Görevin ait olduğu [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) öğesini belirtir.

*lpszName*<br/>
Görevin adını belirtir.

*Nıcon*<br/>
Görüntü listesindeki görevin görüntüsünün dizinini belirtir.

*Uııommandıd*<br/>
Görev tıklandığında yürütülen komutun komut KIMLIĞINI belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı veriler.

*hwndTask*<br/>
Görev penceresine yönelik tanıtıcıyı belirtir.

*Bautodestroyıwindow*<br/>
TRUE ise, görev penceresi otomatik olarak yok edilir.

*nWindowHeight*<br/>
Görev penceresinin yüksekliğini belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetaskm_bautodestroywindow"></a><a name="m_bautodestroywindow"></a> CMFCTasksPaneTask:: m_bAutoDestroyWindow

Görev penceresinin otomatik olarak yok edilip edilmeyeceğini belirler.

```
BOOL m_bAutoDestroyWindow;
```

### <a name="remarks"></a>Açıklamalar

Görev penceresinin ( [CMFCTasksPaneTask:: m_hwndTask](#m_hwndtask)) otomatik olarak yok edilmesi gerektiğini BELIRTMEK için true olarak ayarlayın; Aksi takdirde, FALSE.

## <a name="cmfctaskspanetaskm_bisbold"></a><a name="m_bisbold"></a> CMFCTasksPaneTask:: m_bIsBold

Bir görev etiketinin kalın metinde çizilip çizilmeyeceğini belirler.

```
BOOL m_bIsBold;
```

### <a name="remarks"></a>Açıklamalar

Görev etiketi için kalın metin göstermek için bu üyeyi TRUE olarak ayarlayın.

## <a name="cmfctaskspanetaskm_dwuserdata"></a><a name="m_dwuserdata"></a> CMFCTasksPaneTask:: m_dwUserData

Görevle ilişkili kullanıcı tanımlı verileri içerir. Görevle ilişkili bir veri yoksa sıfır olarak ayarlayın.

```
DWORD m_dwUserData;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetaskm_hwndtask"></a><a name="m_hwndtask"></a> CMFCTasksPaneTask:: m_hwndTask

Görev penceresine yönelik bir tanıtıcı.

```
HWND m_hwndTask;
```

### <a name="remarks"></a>Açıklamalar

Bir görev penceresi eklemek için [CMFCTasksPane:: AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow)komutunu çağırın.

## <a name="cmfctaskspanetaskm_nicon"></a><a name="m_nicon"></a> CMFCTasksPaneTask:: m_nIcon

Belirtilen görevin yanında görüntülenen bir görüntüyü tanımlayan bir görüntü listesindeki dizin konumu.

```
int m_nIcon;
```

### <a name="remarks"></a>Açıklamalar

Görüntü listesi [CMFCTasksPane:: SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist)tarafından ayarlanır.

`m_nIcon`Görevi bir görüntü olmadan göstermek istiyorsanız-1 olarak ayarlayın.

## <a name="cmfctaskspanetaskm_nwindowheight"></a><a name="m_nwindowheight"></a> CMFCTasksPaneTask:: m_nWindowHeight

Görev penceresinin yüksekliği. Görevin görev penceresi yoksa, bu değer sıfırdır.

```
int m_nWindowHeight;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetaskm_pgroup"></a><a name="m_pgroup"></a> CMFCTasksPaneTask:: m_pGroup

Bu görevin ait olduğu [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) işaretçisi.

```
CMFCTasksPaneTaskGroup* m_pGroup;
```

### <a name="remarks"></a>Açıklamalar

Her görevin bir üst grubu olması gerekir. Bir görev bölmesine [CMFCTasksPane:: AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)çağırarak gruplar eklersiniz.

## <a name="cmfctaskspanetaskm_rect"></a><a name="m_rect"></a> CMFCTasksPaneTask:: m_rect

Görevin sınırlayıcı dikdörtgenini belirtir.

```
CRect m_rect;
```

### <a name="remarks"></a>Açıklamalar

Bu değer, görev çizildiğinde Framework tarafından hesaplanır.

## <a name="cmfctaskspanetaskm_strname"></a><a name="m_strname"></a> CMFCTasksPaneTask:: m_strName

Görevin adı.

```
CString m_strName;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetaskm_uicommandid"></a><a name="m_uicommandid"></a> CMFCTasksPaneTask:: m_uiCommandID

Kullanıcı göreve tıkladığında yürütülen komutun komut KIMLIĞINI belirtir. Bu değer geçerli bir komut KIMLIĞI değilse, görev basit bir etiket olarak değerlendirilir.

```
UINT m_uiCommandID;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetasksetaccdata"></a><a name="setaccdata"></a> CMFCTasksPaneTask:: SetACCData

Geçerli görev için erişilebilirlik verilerini belirler.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
'ndaki Geçerli görevin üst penceresini temsil eder.

*data*<br/>
dışı `CAccessibilityData` Geçerli görevin erişilebilirlik verileriyle doldurulan türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

*Veri* parametresi geçerli görevin erişilebilirlik verileriyle başarıyla DOLDURULDıYSA true. Aksi takdirde, FALSE.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)
