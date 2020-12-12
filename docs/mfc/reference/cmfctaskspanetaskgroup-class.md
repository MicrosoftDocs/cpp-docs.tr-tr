---
description: 'Daha fazla bilgi edinin: CMFCTasksPaneTaskGroup sınıfı'
title: CMFCTasksPaneTaskGroup sınıfı
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
ms.openlocfilehash: 6b09923c70ad6208b1b029e6ad555c22cd4c771f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254709"
---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup sınıfı

`CMFCTasksPaneTaskGroup`Sınıfı, [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) denetimi tarafından kullanılan bir yardımcı sınıftır. Türündeki nesneler `CMFCTasksPaneTaskGroup` bir *görev grubunu* temsil eder. Görev grubu, Framework 'ün daraltma düğmesi olan ayrı bir kutu içinde görüntülediği öğelerin listesidir. Kutu, isteğe bağlı bir açıklamalı alt yazı (grup adı) olabilir. Bir grup daraltılmışsa, görev listesi görünür değildir.

## <a name="syntax"></a>Syntax

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup:: CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Bir `CMFCTasksPaneTaskGroup` nesnesi oluşturur.|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup:: SetACCData](#setaccdata)|Geçerli görev grubu için erişilebilirlik verilerini belirler.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup:: m_bIsBottom](#m_bisbottom)|Görev grubunun, görev bölmesi denetiminin alt kısmına hizalanıp hizalanmayacağını belirler.|
|[CMFCTasksPaneTaskGroup:: m_bIsCollapsed](#m_biscollapsed)|Görev grubunun daraltılıp daraltılmadığını belirler.|
|[CMFCTasksPaneTaskGroup:: m_bIsSpecial](#m_bisspecial)|Görev grubunun özel olup olmadığını belirler *.* Çerçeve, özel açıklamalı alt yazıları farklı bir renkte görüntüler.|
|[CMFCTasksPaneTaskGroup:: m_lstTasks](#m_lsttasks)|Görevlerin iç listesini içerir.|
|[CMFCTasksPaneTaskGroup:: m_rect](#m_rect)|Grup başlığının sınırlayıcı dikdörtgenini belirtir.|
|[CMFCTasksPaneTaskGroup:: m_rectGroup](#m_rectgroup)|Grubun sınırlayıcı dikdörtgenini belirtir.|
|[CMFCTasksPaneTaskGroup:: m_strName](#m_strname)|Grubun adını belirtir.|

## <a name="remarks"></a>Açıklamalar

Aşağıdaki çizimde, genişletilmiş bir görev grubu gösterilmektedir:

![Görev grubu, genişletilmiş](../../mfc/reference/media/nexttaskgrpexpand.png "Görev grubu, genişletilmiş")

Aşağıdaki çizimde daraltılmış bir görev grubu gösterilmektedir:

![Daraltılmış görev grubu](../../mfc/reference/media/nexttaskgrpcollapse.png "Daraltılmış görev grubu")

Aşağıdaki çizimde, bir resim yazısı olmadan bir görev grubu gösterilmektedir:

![Açıklamalı alt yazı olmadan görev grubu](../../mfc/reference/media/nexttaskgrpnocapt.png "Açıklamalı alt yazı olmadan görev grubu")

Aşağıdaki çizimde iki görev grubu gösterilmektedir. İlk görev grubu, `m_bIsSpecial` bayrak true olarak ayarlanarak, ikinci görev grubu özel olmadığı sürece özel olarak işaretlenir. İlk görev grubunun başlığının ikinci görev grubundan daha koyu olduğunu aklınızda edin:

![Özel görev grubu](../../mfc/reference/media/nexttaskgrpspecial.png "Özel görev grubu")

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxTasksPane. h

## <a name="cmfctaskspanetaskgroupcmfctaskspanetaskgroup"></a><a name="cmfctaskspanetaskgroup"></a> CMFCTasksPaneTaskGroup:: CMFCTasksPaneTaskGroup

Bir `CMFCTasksPaneTaskGroup` nesnesi oluşturur.

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
Grup başlık kutusunda grubun adını belirtir.

*bIsBottom*<br/>
Grubun, görev bölmesi denetiminin alt kısmına hizalanıp Hizalanmadığını belirtir.

*bIsSpecial*<br/>
Grubun *özel* olarak yapılıp yapılmayacağını ve bu nedenle Grup başlığının farklı bir renkle doldurulup doldurulmadığını belirtir.

*Bisdaraltılmış*<br/>
Grubun daraltılıp daraltılmadığını belirtir.

*pPage*<br/>
Bu görev grubunun ait olduğu özellik sayfasını belirtir.

*HICON*<br/>
Grup başlığında görüntülenen simgeyi belirtir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctaskspanetaskgroupm_bisbottom"></a><a name="m_bisbottom"></a> CMFCTasksPaneTaskGroup:: m_bIsBottom

Görev grubunun, görev bölmesi denetiminin alt kısmına hizalanıp hizalanmayacağını belirler.

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>Açıklamalar

Görev bölmesi denetiminin alt kısmına yalnızca bir grup hizalanabilir. Bu görev grubunun son eklenmesi gerekiyor. Daha fazla bilgi için bkz. [CMFCTasksPane:: AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).

## <a name="cmfctaskspanetaskgroupm_biscollapsed"></a><a name="m_biscollapsed"></a> CMFCTasksPaneTaskGroup:: m_bIsCollapsed

Görev grubunun daraltılıp daraltılmadığını belirler.

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>Açıklamalar

[CMFCTasksPane:: EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse)' i çağırarak görev bölmesindeki grupları daraltma özelliğini etkinleştirebilir veya devre dışı bırakabilirsiniz.

## <a name="cmfctaskspanetaskgroupm_bisspecial"></a><a name="m_bisspecial"></a> CMFCTasksPaneTaskGroup:: m_bIsSpecial

Görev grubunun *özel* olup olmadığını ve özel bir görev grubunun açıklamalı alt yazısının farklı bir renkle tanımlanması gerekip gerekmediğini belirler.

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>Açıklamalar

Uygulamanız Windows XP görsel temasını kullanıyorsa ve `m_bIsSpecial` yanlış ise, çerçeve `DrawThemeBackground` EBP_NORMALGROUPBACKGROUND bayrağıyla çağırır. `m_bIsSpecial`True ise framework `DrawThemeBackground` EBP_SPECIALGROUPBACKGROUND bayrağıyla çağırır.

## <a name="cmfctaskspanetaskgroupm_lsttasks"></a><a name="m_lsttasks"></a> CMFCTasksPaneTaskGroup:: m_lstTasks

Görevlerin iç listesini içerir.

```
CObList m_lstTasks;
```

### <a name="remarks"></a>Açıklamalar

Bu listeyi doldurmanız için [CMFCTasksPane:: AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask)komutunu çağırın.

## <a name="cmfctaskspanetaskgroupm_rect"></a><a name="m_rect"></a> CMFCTasksPaneTaskGroup:: m_rect

Grup başlığının sınırlayıcı dikdörtgenini belirtir.

```
CRect m_rect;
```

### <a name="remarks"></a>Açıklamalar

Bu değer, Framework tarafından otomatik olarak hesaplanır.

## <a name="cmfctaskspanetaskgroupm_rectgroup"></a><a name="m_rectgroup"></a> CMFCTasksPaneTaskGroup:: m_rectGroup

Grubun sınırlayıcı dikdörtgenini belirtir.

```
CRect m_rectGroup;
```

### <a name="remarks"></a>Açıklamalar

Bu değer, Framework tarafından otomatik olarak hesaplanır.

## <a name="cmfctaskspanetaskgroupm_strname"></a><a name="m_strname"></a> CMFCTasksPaneTaskGroup:: m_strName

Grubun adını belirtir.

```
CString m_strName;
```

### <a name="remarks"></a>Açıklamalar

Bu değer boşsa, grup başlığı görüntülenmez ve grup daraltılamaz.

## <a name="cmfctaskspanetaskgroupsetaccdata"></a><a name="setaccdata"></a> CMFCTasksPaneTaskGroup:: SetACCData

Geçerli görev grubu için erişilebilirlik verilerini belirler.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
'ndaki Geçerli görev grubunun üst penceresini temsil eder.

*data*<br/>
dışı `CAccessibilityData` Geçerli görev grubunun erişilebilirlik verileriyle doldurulan türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

*Veri* parametresi geçerli görev grubunun erişilebilirlik verileriyle başarıyla DOLDURULDıYSA true. Aksi takdirde, FALSE.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTasksPane sınıfı](../../mfc/reference/cmfctaskspane-class.md)<br/>
[CMFCTasksPaneTask sınıfı](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)
