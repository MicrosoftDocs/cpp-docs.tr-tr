---
title: CMFCTasksPaneTaskGroup Sınıfı
ms.date: 11/19/2018
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
ms.openlocfilehash: 4c24eba646bede462a5f3cfb85715278cfa7daee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366262"
---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup Sınıfı

Sınıf `CMFCTasksPaneTaskGroup` [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) denetimi tarafından kullanılan bir yardımcı sınıftır. Tür `CMFCTasksPaneTaskGroup` nesneleri bir *görev grubunu*temsil eder. Görev grubu, çerçevenin daraltdüğmesi olan ayrı bir kutuda görüntülenebilen öğelerin listesidir. Kutuda isteğe bağlı bir resim yazısı (grup adı) olabilir. Bir grup daraltılırsa, görev listesi görünmez.

## <a name="syntax"></a>Sözdizimi

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Bir `CMFCTasksPaneTaskGroup` nesne inşa eder.|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|Geçerli görev grubunun erişilebilirlik verilerini belirler.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|Görev grubunun görev bölmedenetiminin altına hizalanıp hizalanmayacağını belirler.|
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|Görev grubunun daraltılıp çökmediğini belirler.|
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|Görev grubunun özel olup olmadığını *belirler.* Çerçeve, farklı renkte özel altyazılar görüntüler.|
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|Dahili görev listesini içerir.|
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|Grup başlığının sınırlayıcı dikdörtgenini belirtir.|
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|Grubun sınırlayıcı dikdörtgenini belirtir.|
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|Grubun adını belirtir.|

## <a name="remarks"></a>Açıklamalar

Aşağıdaki resimde genişletilmiş bir görev grubu gösterilmektedir:

![Görev grubu, genişletilmiş](../../mfc/reference/media/nexttaskgrpexpand.png "Görev grubu, genişletilmiş")

Aşağıdaki resimde daraltılmış bir görev grubu gösterilmektedir:

![Daraltılmış görev grubu](../../mfc/reference/media/nexttaskgrpcollapse.png "Daraltılmış görev grubu")

Aşağıdaki resimde resim yazısı olmayan bir görev grubu gösterilmektedir:

![Resim yazısı olmayan görev grubu](../../mfc/reference/media/nexttaskgrpnocapt.png "Resim yazısı olmayan görev grubu")

Aşağıdaki resimde iki görev grubu gösterilmektedir. İlk görev `m_bIsSpecial` grubu, bayrağı TRUE olarak ayarlayarak özel olarak işaretlenirken, ikinci görev grubu özel değildir. İlk görev grubu için alt yazının ikinci görev grubundan nasıl daha koyu olduğuna dikkat edin:

![Özel görev grubu](../../mfc/reference/media/nexttaskgrpspecial.png "Özel görev grubu")

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cmfctaskspanetaskgroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxTasksPane.h

## <a name="cmfctaskspanetaskgroupcmfctaskspanetaskgroup"></a><a name="cmfctaskspanetaskgroup"></a>CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup

Bir `CMFCTasksPaneTaskGroup` nesne inşa eder.

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

*Lpszname*<br/>
Grup başlığında grubun adını belirtir.

*bIsBottom*<br/>
Grubun görev bölmedenetiminin altına hizalanıp hizalanmayacağını belirtir.

*bIsSpecial*<br/>
Grubun *özel* olarak belirlenip belirtmediğini ve böylece grup başlığının farklı bir renkle doldurulup doldurulmadığını belirtir.

*bIsCollapsed*<br/>
Grubun çöküp çökmediğini belirtir.

*pPage*<br/>
Bu görev grubunun ait olduğu özellik sayfasını belirtir.

*Hıcon*<br/>
Grup başlığında görüntüleyen simgeyi belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetaskgroupm_bisbottom"></a><a name="m_bisbottom"></a>CMFCTasksPaneTaskGroup::m_bIsBottom

Görev grubunun görev bölmedenetiminin altına hizalanıp hizalanmayacağını belirler.

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>Açıklamalar

Görev bölmedenetiminin altına yalnızca bir grup hizalanabilir. Bu görev grubu en son eklenmelidir. Daha fazla bilgi için [cmfctasksPane::AddGroup'a](../../mfc/reference/cmfctaskspane-class.md#addgroup)bakın.

## <a name="cmfctaskspanetaskgroupm_biscollapsed"></a><a name="m_biscollapsed"></a>CMFCTasksPaneTaskGroup::m_bIsCollapsed

Görev grubunun daraltılıp çökmediğini belirler.

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>Açıklamalar

[CMFCTasksPane::EnableGroupCollapse'i](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse)arayarak görev bölmesindeki grupları daraltma yeteneğini etkinleştirebilir veya devre dışı kullanabilirsiniz.

## <a name="cmfctaskspanetaskgroupm_bisspecial"></a><a name="m_bisspecial"></a>CMFCTasksPaneTaskGroup::m_bIsSpecial

Görev grubunun *özel* olup olmadığını ve özel bir görev grubunun alt yazısının farklı bir renkle tanımlanıp tanımlanmayacağını belirler.

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>Açıklamalar

Uygulamanız Windows XP görsel teonu `m_bIsSpecial` kullanıyorsa ve `DrawThemeBackground` FALSE ise, çerçeve EBP_NORMALGROUPBACKGROUND bayrağıyla birlikte çağırır. `m_bIsSpecial` Doğruysa, çerçeve EBP_SPECIALGROUPBACKGROUND `DrawThemeBackground` bayrağıyla birlikte çağırır.

## <a name="cmfctaskspanetaskgroupm_lsttasks"></a><a name="m_lsttasks"></a>CMFCTasksPaneTaskGroup::m_lstTasks

Dahili görev listesini içerir.

```
CObList m_lstTasks;
```

### <a name="remarks"></a>Açıklamalar

Bu listeyi doldurmak için [CMFCTasksPane'yi arayın::AddTask.](../../mfc/reference/cmfctaskspane-class.md#addtask)

## <a name="cmfctaskspanetaskgroupm_rect"></a><a name="m_rect"></a>CMFCTasksPaneTaskGroup::m_rect

Grup başlığının sınırlayıcı dikdörtgenini belirtir.

```
CRect m_rect;
```

### <a name="remarks"></a>Açıklamalar

Bu değer çerçeve tarafından otomatik olarak hesaplanır.

## <a name="cmfctaskspanetaskgroupm_rectgroup"></a><a name="m_rectgroup"></a>CMFCTasksPaneTaskGroup::m_rectGroup

Grubun sınırlayıcı dikdörtgenini belirtir.

```
CRect m_rectGroup;
```

### <a name="remarks"></a>Açıklamalar

Bu değer çerçeve tarafından otomatik olarak hesaplanır.

## <a name="cmfctaskspanetaskgroupm_strname"></a><a name="m_strname"></a>CMFCTasksPaneTaskGroup::m_strName

Grubun adını belirtir.

```
CString m_strName;
```

### <a name="remarks"></a>Açıklamalar

Bu değer boşsa, grup başlığı görüntülenmez ve grup daraltılamaz.

## <a name="cmfctaskspanetaskgroupsetaccdata"></a><a name="setaccdata"></a>CMFCTasksPaneTaskGroup::SetACCData

Geçerli görev grubunun erişilebilirlik verilerini belirler.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
[içinde] Geçerli görev grubunun üst penceresini temsil eder.

*Veri*<br/>
[çıkış] Geçerli görev `CAccessibilityData` grubunun erişilebilirlik verileriyle doldurulan tür nesnesi.

### <a name="return-value"></a>Dönüş Değeri

*Veri* parametresi geçerli görev grubunun erişilebilirlik verileriyle başarıyla doldurulduysa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTasksPane Sınıfı](../../mfc/reference/cmfctaskspane-class.md)<br/>
[CMFCTasksPaneTask Sınıfı](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)
