---
title: CAnimationGroup Sınıfı
ms.date: 03/27/2019
f1_keywords:
- CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::Animate
- AFXANIMATIONCONTROLLER/CAnimationGroup::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationGroup::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::Schedule
- AFXANIMATIONCONTROLLER/CAnimationGroup::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutoclearTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstKeyFrames
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pStoryboard
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pParentController
helpviewer_keywords:
- CAnimationGroup [MFC], CAnimationGroup
- CAnimationGroup [MFC], Animate
- CAnimationGroup [MFC], ApplyTransitions
- CAnimationGroup [MFC], FindAnimationObject
- CAnimationGroup [MFC], GetGroupID
- CAnimationGroup [MFC], RemoveKeyframes
- CAnimationGroup [MFC], RemoveTransitions
- CAnimationGroup [MFC], Schedule
- CAnimationGroup [MFC], SetAutodestroyTransitions
- CAnimationGroup [MFC], AddKeyframes
- CAnimationGroup [MFC], AddTransitions
- CAnimationGroup [MFC], CreateTransitions
- CAnimationGroup [MFC], m_bAutoclearTransitions
- CAnimationGroup [MFC], m_bAutodestroyAnimationObjects
- CAnimationGroup [MFC], m_bAutodestroyKeyframes
- CAnimationGroup [MFC], m_lstAnimationObjects
- CAnimationGroup [MFC], m_lstKeyFrames
- CAnimationGroup [MFC], m_pStoryboard
- CAnimationGroup [MFC], m_nGroupID
- CAnimationGroup [MFC], m_pParentController
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
ms.openlocfilehash: 28d305e2107f7b9a8fd2164eb0ec9678d62ef8fa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369741"
---
# <a name="canimationgroup-class"></a>CAnimationGroup Sınıfı

Animasyon film şeridini, animasyon nesnelerini ve animasyonu tanımlamak için geçişleri birleştiren bir animasyon grubu uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationGroup;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationGroup::CAnimationGroup](#canimationgroup)|Bir animasyon grubu kurar.|
|[CAnimationGroup::~CAnimationGroup](#_dtorcanimationgroup)|Yıkıcı. Animasyon grubu yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationGroup::Animasyon](#animate)|Bir grubu canlandırır.|
|[CAnimationGroup::GeçişUygula](#applytransitions)|Animasyon nesnelerine geçişler uygular.|
|[CAnimationGroup::FindAnimationObject](#findanimationobject)|Belirtilen animasyon değişkenini içeren bir animasyon nesnesi bulur.|
|[CAnimationGroup::GetGroupID](#getgroupid)|GroupID'yi döndürür.|
|[CAnimationGroup::Anahtar Kareleri Kaldırma](#removekeyframes)|Animasyon grubuna ait tüm anahtar kareleri kaldırır ve isteğe bağlı olarak yok eder.|
|[CAnimationGroup::Geçişleri Kaldırma](#removetransitions)|Animasyon grubuna ait animasyon nesnelerinden geçişleri kaldırır.|
|[CAnimationGroup::Zamanlama](#schedule)|Animasyonu belirtilen zamanda planlar.|
|[CAnimationGroup::SetAutodestroyGeçişler](#setautodestroytransitions)|Gruba ait tüm animasyon nesnelerini otomatik olarak geçişleri yok eder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationGroup::AddKeyframes](#addkeyframes)|Film şeridine anahtar kareler ekleyen bir yardımcı.|
|[CAnimationGroup::Geçiş Ekleme](#addtransitions)|Film şeridine geçişler ekleyen bir yardımcı.|
|[CAnimationGroup::Geçiş Oluşturma](#createtransitions)|COM geçiş nesneleri oluşturan bir yardımcı.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationGroup::m_bAutoclearTransitions](#m_bautocleartransitions)|Gruba ait animasyon nesnelerinden geçişlerin nasıl temizlenecek olduğunu belirtir. Bu üye TRUE ise, animasyon zamanlandığında geçişler otomatik olarak kaldırılır. Aksi takdirde geçişleri el ile kaldırmanız gerekir.|
|[CAnimationGroup::m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|Animasyon nesnelerinin nasıl yok edilecek olduğunu belirtir. Bu parametre TRUE ise, grup yok edildiğinde animasyon nesneleri otomatik olarak yok edilir. Aksi takdirde animasyon nesneleri el ile yok edilmelidir. Varsayılan değer FALSE'dur. Bu değeri yalnızca gruba ait tüm animasyon nesneleri işleç yeni ile dinamik olarak ayrılırsa TRUE olarak ayarlayın.|
|[CAnimationGroup::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|Anahtar karelerin nasıl yok edilebildiğini belirtir. Bu değer TRUE ise, tüm anahtar kareler kaldırılır ve yok edilir; aksi takdirde yalnızca listeden kaldırılır. Varsayılan değer TRUE'dur.|
|[CAnimationGroup::m_lstAnimationObjects](#m_lstanimationobjects)|Animasyon nesnelerinin listesini içerir.|
|[CAnimationGroup::m_lstKeyFrames](#m_lstkeyframes)|Anahtar karelerin listesini içerir.|
|[CAnimationGroup::m_pStoryboard](#m_pstoryboard)|Animasyon film şeridine işaret. Bu işaretçi yalnızca Animate'i aradıktan sonra geçerlidir.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationGroup::m_nGroupID](#m_ngroupid)|Animasyon grubunun benzersiz bir tanımlayıcısı.|
|[CAnimationGroup:m_pParentController](#m_pparentcontroller)|Bu grubun ait olduğu animasyon denetleyicisine işaretçi.|

## <a name="remarks"></a>Açıklamalar

Animasyon grupları, CAnimationController:AddAnimationObject kullanarak animasyon nesneleri eklediğinizde animasyon denetleyicisi (CAnimationController) tarafından otomatik olarak oluşturulur. Bir animasyon grubu GroupID tarafından tanımlanır ve bu grup genellikle animasyon gruplarını işlemek için bir parametre olarak alınır. GroupID, yeni bir animasyon grubuna eklenen ilk animasyon nesnesinden alınır. CAnimationController::AnimateGroup'u aradıktan sonra kapsüllenmiş bir animasyon film şeridi oluşturulur ve herkese açık üye m_pStoryboard aracılığıyla erişilebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAnimationGroup`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationgroupcanimationgroup"></a><a name="_dtorcanimationgroup"></a>CAnimationGroup::~CAnimationGroup

Yıkıcı. Animasyon grubu yok edilirken çağrılır.

```
~CAnimationGroup();
```

## <a name="canimationgroupaddkeyframes"></a><a name="addkeyframes"></a>CAnimationGroup::AddKeyframes

Film şeridine anahtar kareler ekleyen bir yardımcı.

```
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Bir film şeridi COM nesnesine işaretçi.

*bAddDeep*<br/>
Bu yöntemin diğer anahtar karelere bağlı olan film şeridi anahtar karelerine ekleyip eklememesi gerektiğini belirtir.

## <a name="canimationgroupaddtransitions"></a><a name="addtransitions"></a>CAnimationGroup::Geçiş Ekleme

Film şeridine geçişler ekleyen bir yardımcı.

```
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Bir film şeridi COM nesnesine işaretçi.

*bDependOnKeyframes*

## <a name="canimationgroupanimate"></a><a name="animate"></a>CAnimationGroup::Animasyon

Bir grubu canlandırır.

```
BOOL Animate(
    IUIAnimationManager* pManager,
    IUIAnimationTimer* pTimer,
    BOOL bScheduleNow);
```

### <a name="parameters"></a>Parametreler

*pManager*<br/>
*pTimer*
*bScheduleNow*

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir iç film şeridi oluşturur, geçişler oluşturur ve uygular ve bScheduleNow TRUE ise bir animasyon zamanlar. bScheduleNow FALSE ise, animasyonu belirtilen zamanda başlatmak için Zamanlama'yı aramanız gerekir.

## <a name="canimationgroupapplytransitions"></a><a name="applytransitions"></a>CAnimationGroup::GeçişUygula

Animasyon nesnelerine geçişler uygular.

```
void ApplyTransitions();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, film şeridi oluşturulmamadıysa hata ayıklama modunda ileri salar. Önce tüm geçişleri oluşturur, sonra "statik" anahtar kareler (uzaklıklara bağlı anahtar kareler), anahtar karelere bağlı olmayan geçişler ekler, geçişlere ve diğer anahtar karelere bağlı olarak anahtar kareler ekler ve en sonunda anahtar karelere bağlı geçişler ekler.

## <a name="canimationgroupcanimationgroup"></a><a name="canimationgroup"></a>CAnimationGroup::CAnimationGroup

Bir animasyon grubu kurar.

```
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```

### <a name="parameters"></a>Parametreler

*pParentController*<br/>
Grup oluşturan animasyon denetleyicisine işaretçi.

*nGroupID*<br/>
GroupID'yi belirtir.

## <a name="canimationgroupcreatetransitions"></a><a name="createtransitions"></a>CAnimationGroup::Geçiş Oluşturma

COM geçiş nesneleri oluşturan bir yardımcı.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Dönüş Değeri

TRUE yöntem, aksi takdirde FALSE başarılı olmasıdır.

## <a name="canimationgroupfindanimationobject"></a><a name="findanimationobject"></a>CAnimationGroup::FindAnimationObject

Belirtilen animasyon değişkenini içeren bir animasyon nesnesi bulur.

```
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametreler

*pDeğişken*<br/>
Animasyon değişkenine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Animasyon nesnesi için bir işaretçi veya animasyon nesnesi bulunamazsa NULL.

## <a name="canimationgroupgetgroupid"></a><a name="getgroupid"></a>CAnimationGroup::GetGroupID

GroupID'yi döndürür.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir grup tanımlayıcısı.

## <a name="canimationgroupm_bautocleartransitions"></a><a name="m_bautocleartransitions"></a>CAnimationGroup::m_bAutoclearTransitions

Gruba ait animasyon nesnelerinden geçişlerin nasıl temizlenecek olduğunu belirtir. Bu üye TRUE ise, animasyon zamanlandığında geçişler otomatik olarak kaldırılır. Aksi takdirde geçişleri el ile kaldırmanız gerekir.

```
BOOL m_bAutoclearTransitions;
```

## <a name="canimationgroupm_bautodestroyanimationobjects"></a><a name="m_bautodestroyanimationobjects"></a>CAnimationGroup::m_bAutodestroyAnimationObjects

Animasyon nesnelerinin nasıl yok edilecek olduğunu belirtir. Bu parametre TRUE ise, grup yok edildiğinde animasyon nesneleri otomatik olarak yok edilir. Aksi takdirde animasyon nesneleri el ile yok edilmelidir. Varsayılan değer FALSE'dur. Bu değeri yalnızca gruba ait tüm animasyon nesneleri işleç yeni ile dinamik olarak ayrılırsa TRUE olarak ayarlayın.

```
BOOL m_bAutodestroyAnimationObjects;
```

## <a name="canimationgroupm_bautodestroykeyframes"></a><a name="m_bautodestroykeyframes"></a>CAnimationGroup::m_bAutodestroyKeyframes

Anahtar karelerin nasıl yok edilebildiğini belirtir. Bu değer TRUE ise, tüm anahtar kareler kaldırılır ve yok edilir; aksi takdirde yalnızca listeden kaldırılır. Varsayılan değer TRUE'dur.

```
BOOL m_bAutodestroyKeyframes;
```

## <a name="canimationgroupm_lstanimationobjects"></a><a name="m_lstanimationobjects"></a>CAnimationGroup::m_lstAnimationObjects

Animasyon nesnelerinin listesini içerir.

```
CObList m_lstAnimationObjects;
```

## <a name="canimationgroupm_lstkeyframes"></a><a name="m_lstkeyframes"></a>CAnimationGroup::m_lstKeyFrames

Anahtar karelerin listesini içerir.

```
CObList m_lstKeyFrames;
```

## <a name="canimationgroupm_ngroupid"></a><a name="m_ngroupid"></a>CAnimationGroup::m_nGroupID

Animasyon grubunun benzersiz bir tanımlayıcısı.

```
UINT32 m_nGroupID;
```

## <a name="canimationgroupm_pparentcontroller"></a><a name="m_pparentcontroller"></a>CAnimationGroup:m_pParentController

Bu grubun ait olduğu animasyon denetleyicisine işaretçi.

```
CAnimationController* m_pParentController;
```

## <a name="canimationgroupm_pstoryboard"></a><a name="m_pstoryboard"></a>CAnimationGroup::m_pStoryboard

Animasyon film şeridine işaret. Bu işaretçi yalnızca Animate'i aradıktan sonra geçerlidir.

```
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;
```

## <a name="canimationgroupremovekeyframes"></a><a name="removekeyframes"></a>CAnimationGroup::Anahtar Kareleri Kaldırma

Animasyon grubuna ait tüm anahtar kareleri kaldırır ve isteğe bağlı olarak yok eder.

```
void RemoveKeyframes();
```

### <a name="remarks"></a>Açıklamalar

m_bAutodestroyKeyframes üye DOĞRUYSA, anahtar kareler kaldırılır ve yok edilir, aksi takdirde anahtar kareler iç anahtar kareler listesinden kaldırılır.

## <a name="canimationgroupremovetransitions"></a><a name="removetransitions"></a>CAnimationGroup::Geçişleri Kaldırma

Animasyon grubuna ait animasyon nesnelerinden geçişleri kaldırır.

```
void RemoveTransitions();
```

### <a name="remarks"></a>Açıklamalar

m_bAutoclearTransitions bayrağı TRUE olarak ayarlanmışsa, bu yöntem gruba ait tüm animasyon nesnelerinin üzerine döngüler ve CAnimationObject::ClearTransitions(FALSE) çağırır.

## <a name="canimationgroupschedule"></a><a name="schedule"></a>CAnimationGroup::Zamanlama

Animasyonu belirtilen zamanda planlar.

```
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```

### <a name="parameters"></a>Parametreler

*pTimer*<br/>
Animasyon zamanlayıcısı için bir işaretçi.

*time*<br/>
Animasyonu zamanlamak için zaman belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa DOĞRU; Yöntem başarısız olursa veya Animate bScheduleNow false olarak ayarlanmış olarak çağrılmazsa YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Belirtilen zamanda bir animasyon zamanlamak için bu işlevi çağırın. Önce FALSE olarak ayarlanmış bScheduleNow ile Animate'i aramalısınız.

## <a name="canimationgroupsetautodestroytransitions"></a><a name="setautodestroytransitions"></a>CAnimationGroup::SetAutodestroyGeçişler

Gruba ait tüm animasyon nesnelerini otomatik olarak geçişleri yok eder.

```
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*bAutoDestroy*<br/>
Geçişleri nasıl yok edineni belirtir.

### <a name="remarks"></a>Açıklamalar

Bu değeri yalnızca yığına geçişler ayırırsanız FALSE olarak ayarlayın. Varsayılan değer TRUE olduğundan, geçiş nesnelerinin operatör yeni kullanılarak ayrılması önerilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
