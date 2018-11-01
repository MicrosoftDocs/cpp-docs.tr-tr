---
title: CMFCTasksPaneTaskGroup sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 25e714aa617cdccc4e02e288f1a24f636e05cb0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539613"
---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup sınıfı

`CMFCTasksPaneTaskGroup` Bir yardımcı sınıfı tarafından kullanılan [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) denetimi. Türündeki nesneler `CMFCTasksPaneTaskGroup` temsil eden bir *görev grubu*. Görev grubu, framework Daralt düğmesi olan ayrı bir kutuda görüntülediği öğelerin listesidir. Kutu isteğe bağlı bir başlık (grup adı) olabilir. Bir grup daraltılmışsa, görevlerin listesi görünür değil.

## <a name="syntax"></a>Sözdizimi

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Oluşturur bir `CMFCTasksPaneTaskGroup` nesne.|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|Geçerli görev grubu için erişilebilirlik verileri belirler.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|Görev grubu görev bölmesi denetimi altına hizalanıp hizalanmayacağını belirler.|
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|Görev grubu daraltılmış olup olmadığını belirler.|
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|Görev grubu olup olmadığını belirler *özel.* Framework özel açıklamalı alt yazılar farklı bir renkte görüntülenir.|
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|İç Görevler listesini içerir.|
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|Sınırlayıcı dikdörtgenini Grup başlığını belirtir.|
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|Grup sınırlayıcı dikdörtgenini belirtir.|
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|Grubun adını belirtir.|

## <a name="remarks"></a>Açıklamalar

Aşağıdaki çizim bir genişletilmiş görev grubunu gösterir:

![Görev grubu, Genişletilmiş](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")

Daraltılmış görev grubu aşağıda gösterilmiştir:

![Daraltılmış görev grubu](../../mfc/reference/media/nexttaskgrpcollapse.png "nexttaskgrpcollapse")

Bir görev grubunun resim yazısı olmadan aşağıda gösterilmiştir:

![Görev grubu olmadan bir açıklamalı alt yazı](../../mfc/reference/media/nexttaskgrpnocapt.png "nexttaskgrpnocapt")

Aşağıdaki çizimde, iki görev gruplarını gösterir. İlk görev grubu ayarlayarak özel olarak işaretlenmiş `m_bIsSpecial` bayrağı TRUE olarak ikinci görev grubunun özel değil. İlk görev grubu için açıklama yazısını nasıl ikinci görev grubu koyu olduğunu unutmayın:

![Özel görev grubu](../../mfc/reference/media/nexttaskgrpspecial.png "nexttaskgrpspecial")

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxTasksPane.h

##  <a name="cmfctaskspanetaskgroup"></a>  CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup

Oluşturur bir `CMFCTasksPaneTaskGroup` nesne.

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

*lpszName*<br/>
Grup başlığı grubunun adını belirtir.

*bIsBottom*<br/>
Görev bölmesi denetimi altına grubu hizalanıp hizalanmayacağını belirtir.

*bIsSpecial*<br/>
Grup olarak belirlenmiş olup olmadığını belirtir *özel* ve bu nedenle, Grup başlığını farklı bir renkle olup doldurulur.

*bIsCollapsed*<br/>
Grup daraltılmış olup olmadığını belirtir.

*fsayfa*<br/>
Bu görev grubuna ait özellik sayfası belirtir.

*hIcon*<br/>
Grup başlığı görüntüler simgeyi belirtir.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_bisbottom"></a>  CMFCTasksPaneTaskGroup::m_bIsBottom

Görev grubu görev bölmesi denetimi altına hizalanıp hizalanmayacağını belirler.

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>Açıklamalar

Yalnızca bir grup görev bölmesi denetimi altına hizalanabilir. Bu görev grubu son eklenmesi gerekir. Daha fazla bilgi için [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).

##  <a name="m_biscollapsed"></a>  CMFCTasksPaneTaskGroup::m_bIsCollapsed

Görev grubu daraltılmış olup olmadığını belirler.

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>Açıklamalar

Etkinleştirebilir veya çağırarak görev bölmesinde grupları Daralt özelliğini devre dışı [CMFCTasksPane::EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse).

##  <a name="m_bisspecial"></a>  CMFCTasksPaneTaskGroup::m_bIsSpecial

Görev grubu olup olmadığını belirler *özel* ve bir özel görev grubu için açıklama yazısını farklı bir renk ile tanımlanması gerektiğini.

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>Açıklamalar

Uygulamanızı Windows XP görsel temasını kullanıp kullanmadığını ve `m_bIsSpecial` yanlış, framework çağrıları `DrawThemeBackground` EBP_NORMALGROUPBACKGROUND bayrağı. Varsa `m_bIsSpecial` true, framework çağrıları `DrawThemeBackground` EBP_SPECIALGROUPBACKGROUND bayrağı.

##  <a name="m_lsttasks"></a>  CMFCTasksPaneTaskGroup::m_lstTasks

İç Görevler listesini içerir.

```
CObList m_lstTasks;
```

### <a name="remarks"></a>Açıklamalar

Bu listeyi doldurmak için çağrı [CMFCTasksPane::AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask).

##  <a name="m_rect"></a>  CMFCTasksPaneTaskGroup::m_rect

Sınırlayıcı dikdörtgenini Grup başlığını belirtir.

```
CRect m_rect;
```

### <a name="remarks"></a>Açıklamalar

Bu değer, çerçeve tarafından otomatik olarak hesaplanır.

##  <a name="m_rectgroup"></a>  CMFCTasksPaneTaskGroup::m_rectGroup

Grup sınırlayıcı dikdörtgenini belirtir.

```
CRect m_rectGroup;
```

### <a name="remarks"></a>Açıklamalar

Bu değer, çerçeve tarafından otomatik olarak hesaplanır.

##  <a name="m_strname"></a>  CMFCTasksPaneTaskGroup::m_strName

Grubun adını belirtir.

```
CString m_strName;
```

### <a name="remarks"></a>Açıklamalar

Bu değer boş ise Grup başlığını görüntülenmez ve grubun daraltılamaz.

##  <a name="setaccdata"></a>  CMFCTasksPaneTaskGroup::SetACCData

Geçerli görev grubu için erişilebilirlik verileri belirler.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
[in] Geçerli görev grubunun ana pencereyi temsil eder.

*Veri*<br/>
[out] Bir nesne türü `CAccessibilityData` geçerli görev grubunun erişilebilirlik verilerle doldurulur.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise *veri* parametre başarıyla geçerli görev grubunun erişilebilirlik verilerle doldurulmuş; Aksi takdirde FALSE.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTasksPane Sınıfı](../../mfc/reference/cmfctaskspane-class.md)<br/>
[CMFCTasksPaneTask Sınıfı](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)
