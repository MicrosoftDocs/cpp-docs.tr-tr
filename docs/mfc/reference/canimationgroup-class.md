---
description: 'Daha fazla bilgi edinin: CAnimationGroup sınıfı'
title: CAnimationGroup sınıfı
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
ms.openlocfilehash: 45fd49b95f73811f52795b87bf3de2dd004fa5ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336795"
---
# <a name="canimationgroup-class"></a>CAnimationGroup sınıfı

Bir animasyon görsel taslağı, animasyon nesneleri ve bir animasyon tanımlamak için geçişleri birleştiren bir animasyon grubu uygular.

## <a name="syntax"></a>Syntax

```
class CAnimationGroup;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationGroup:: CAnimationGroup](#canimationgroup)|Bir animasyon grubu oluşturur.|
|[CAnimationGroup:: ~ CAnimationGroup](#_dtorcanimationgroup)|Yok edicisi. Bir animasyon grubu yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationGroup:: canlandır](#animate)|Bir grubun animasyonunu yapar.|
|[CAnimationGroup:: Applygeçişleri](#applytransitions)|Animasyon nesnelerine geçişleri uygular.|
|[CAnimationGroup:: Findanimasyonobject](#findanimationobject)|Belirtilen animasyon değişkenini içeren bir animasyon nesnesi bulur.|
|[CAnimationGroup:: Getgroupıd](#getgroupid)|GroupID döndürür.|
|[CAnimationGroup:: RemoveKeyframes](#removekeyframes)|Bir animasyon grubuna ait olan tüm ana kareleri kaldırır ve isteğe bağlı olarak yok eder.|
|[CAnimationGroup:: Removetransıtions](#removetransitions)|Animasyon grubuna ait olan animasyon nesnelerinden geçişleri kaldırır.|
|[CAnimationGroup:: Schedule](#schedule)|Belirtilen zamanda bir animasyon zamanlar.|
|[CAnimationGroup:: Setautodestroygeçişler](#setautodestroytransitions)|Gruba ait olan tüm animasyon nesnelerinin geçişleri otomatik olarak yok eder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationGroup:: Addana kareler](#addkeyframes)|Görsel taslağa ana kare ekleyen bir yardımcı.|
|[CAnimationGroup:: Addgeçişleri](#addtransitions)|Görsel taslağa geçiş ekleyen bir yardımcı.|
|[CAnimationGroup:: Creategeçişler](#createtransitions)|COM geçiş nesneleri oluşturan bir yardımcı.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationGroup:: m_bAutoclearTransitions](#m_bautocleartransitions)|Gruba ait olan animasyon nesnelerinden geçişlerin nasıl temizleceğini belirtir. Bu üye TRUE ise, bir animasyon zamanlandığı sırada geçişler otomatik olarak kaldırılır. Aksi takdirde, geçişleri el ile kaldırmanız gerekir.|
|[CAnimationGroup:: m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|Animasyon nesnelerinin nasıl yok ettiğini belirtir. Bu parametre TRUE ise, grup yok edildiğinde animasyon nesneleri otomatik olarak yok edilir. Aksi takdirde animasyon nesnelerinin elle yok edilmesi gerekir. Varsayılan değer FALSE 'dur. Bu değeri yalnızca, gruba ait tüm animasyon nesneleri yeni işleçle dinamik olarak ayrılmışsa TRUE olarak ayarlayın.|
|[CAnimationGroup:: m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|Ana karelerin nasıl yok ettiğini belirtir. Bu değer TRUE ise, tüm ana kareler kaldırılır ve yok edilir; Aksi takdirde, bunlar yalnızca listeden kaldırılır. Varsayılan değer TRUE 'dur.|
|[CAnimationGroup:: m_lstAnimationObjects](#m_lstanimationobjects)|Animasyon nesnelerinin bir listesini içerir.|
|[CAnimationGroup:: m_lstKeyFrames](#m_lstkeyframes)|Ana karelerin bir listesini içerir.|
|[CAnimationGroup:: m_pStoryboard](#m_pstoryboard)|Animasyon görsel taslağa işaret eder. Bu işaretçi yalnızca hareketlendirme üzerinde yapılan çağrıdan sonra geçerlidir.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationGroup:: m_nGroupID](#m_ngroupid)|Animasyon grubunun benzersiz tanıtıcısı.|
|[CAnimationGroup:: m_pParentController](#m_pparentcontroller)|Bu grubun ait olduğu animasyon denetleyicisine yönelik bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

CAnimationController:: AddAnimationObject kullanarak animasyon nesneleri eklediğinizde animasyon grupları animasyon denetleyicisi (CAnimationController) tarafından otomatik olarak oluşturulur. Animasyon grubu, genellikle animasyon gruplarını işlemek için bir parametre olarak alınan GroupID tarafından tanımlanır. GroupID, yeni bir animasyon grubuna eklenmekte olan ilk animasyon nesnesinden alınır. CAnimationController:: AnimateGroup öğesini çağırdıktan sonra kapsüllenmiş bir animasyon şeridi oluşturulur ve ortak üye m_pStoryboard aracılığıyla erişilebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAnimationGroup`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationgroupcanimationgroup"></a><a name="_dtorcanimationgroup"></a> CAnimationGroup:: ~ CAnimationGroup

Yok edicisi. Bir animasyon grubu yok edildiğinde çağırılır.

```
~CAnimationGroup();
```

## <a name="canimationgroupaddkeyframes"></a><a name="addkeyframes"></a> CAnimationGroup:: Addana kareler

Görsel taslağa ana kare ekleyen bir yardımcı.

```cpp
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslak COM nesnesi işaretçisi.

*Baddderin*<br/>
Bu yöntemin diğer ana karelere bağlı olan film şeridi ana kareleri 'ne eklenip eklenmeyeceğini belirtir.

## <a name="canimationgroupaddtransitions"></a><a name="addtransitions"></a> CAnimationGroup:: Addgeçişleri

Görsel taslağa geçiş ekleyen bir yardımcı.

```cpp
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslak COM nesnesi işaretçisi.

*bDependOnKeyframes*

## <a name="canimationgroupanimate"></a><a name="animate"></a> CAnimationGroup:: canlandır

Bir grubun animasyonunu yapar.

```
BOOL Animate(
    IUIAnimationManager* pManager,
    IUIAnimationTimer* pTimer,
    BOOL bScheduleNow);
```

### <a name="parameters"></a>Parametreler

*pManager*<br/>
*Ptimer* 
 *Şimdi Bschedule*

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir iç film şeridi oluşturur, geçişleri oluşturur ve uygular ve bScheduleNow TRUE ise bir animasyon zamanlar. BScheduleNow yanlış ise, animasyonu belirtilen zamanda başlatmak için zamanlamayı çağırmanız gerekir.

## <a name="canimationgroupapplytransitions"></a><a name="applytransitions"></a> CAnimationGroup:: Applygeçişleri

Animasyon nesnelerine geçişleri uygular.

```cpp
void ApplyTransitions();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, film şeridi oluşturulmadıysa hata ayıklama modunda onay vermez. Önce tüm geçişleri oluşturur, ardından "static" ana kareleri ekler (uzaklıklara bağlı olan ana kareler), ana karelere bağlı olmayan geçişleri ekler, geçişleri ve diğer ana karelere bağlı olarak ana kareler ekler ve en son, ana karelere bağlı olan geçişleri ekler.

## <a name="canimationgroupcanimationgroup"></a><a name="canimationgroup"></a> CAnimationGroup:: CAnimationGroup

Bir animasyon grubu oluşturur.

```
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```

### <a name="parameters"></a>Parametreler

*pParentController*<br/>
Bir grup oluşturan animasyon denetleyicisi işaretçisi.

*Ngroupıd*<br/>
GroupID belirtir.

## <a name="canimationgroupcreatetransitions"></a><a name="createtransitions"></a> CAnimationGroup:: Creategeçişler

COM geçiş nesneleri oluşturan bir yardımcı.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olur, aksi takdirde FALSE.

## <a name="canimationgroupfindanimationobject"></a><a name="findanimationobject"></a> CAnimationGroup:: Findanimasyonobject

Belirtilen animasyon değişkenini içeren bir animasyon nesnesi bulur.

```
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametreler

*pVariable*<br/>
Animasyon değişkenine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Animasyon nesnesi işaretçisi veya animasyon nesnesi bulunamazsa NULL.

## <a name="canimationgroupgetgroupid"></a><a name="getgroupid"></a> CAnimationGroup:: Getgroupıd

GroupID döndürür.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir grup tanımlayıcısı.

## <a name="canimationgroupm_bautocleartransitions"></a><a name="m_bautocleartransitions"></a> CAnimationGroup:: m_bAutoclearTransitions

Gruba ait olan animasyon nesnelerinden geçişlerin nasıl temizleceğini belirtir. Bu üye TRUE ise, bir animasyon zamanlandığı sırada geçişler otomatik olarak kaldırılır. Aksi takdirde, geçişleri el ile kaldırmanız gerekir.

```
BOOL m_bAutoclearTransitions;
```

## <a name="canimationgroupm_bautodestroyanimationobjects"></a><a name="m_bautodestroyanimationobjects"></a> CAnimationGroup:: m_bAutodestroyAnimationObjects

Animasyon nesnelerinin nasıl yok ettiğini belirtir. Bu parametre TRUE ise, grup yok edildiğinde animasyon nesneleri otomatik olarak yok edilir. Aksi takdirde animasyon nesnelerinin elle yok edilmesi gerekir. Varsayılan değer FALSE 'dur. Bu değeri yalnızca, gruba ait tüm animasyon nesneleri yeni işleçle dinamik olarak ayrılmışsa TRUE olarak ayarlayın.

```
BOOL m_bAutodestroyAnimationObjects;
```

## <a name="canimationgroupm_bautodestroykeyframes"></a><a name="m_bautodestroykeyframes"></a> CAnimationGroup:: m_bAutodestroyKeyframes

Ana karelerin nasıl yok ettiğini belirtir. Bu değer TRUE ise, tüm ana kareler kaldırılır ve yok edilir; Aksi takdirde, bunlar yalnızca listeden kaldırılır. Varsayılan değer TRUE 'dur.

```
BOOL m_bAutodestroyKeyframes;
```

## <a name="canimationgroupm_lstanimationobjects"></a><a name="m_lstanimationobjects"></a> CAnimationGroup:: m_lstAnimationObjects

Animasyon nesnelerinin bir listesini içerir.

```
CObList m_lstAnimationObjects;
```

## <a name="canimationgroupm_lstkeyframes"></a><a name="m_lstkeyframes"></a> CAnimationGroup:: m_lstKeyFrames

Ana karelerin bir listesini içerir.

```
CObList m_lstKeyFrames;
```

## <a name="canimationgroupm_ngroupid"></a><a name="m_ngroupid"></a> CAnimationGroup:: m_nGroupID

Animasyon grubunun benzersiz tanıtıcısı.

```
UINT32 m_nGroupID;
```

## <a name="canimationgroupm_pparentcontroller"></a><a name="m_pparentcontroller"></a> CAnimationGroup:: m_pParentController

Bu grubun ait olduğu animasyon denetleyicisine yönelik bir işaretçi.

```
CAnimationController* m_pParentController;
```

## <a name="canimationgroupm_pstoryboard"></a><a name="m_pstoryboard"></a> CAnimationGroup:: m_pStoryboard

Animasyon görsel taslağa işaret eder. Bu işaretçi yalnızca hareketlendirme üzerinde yapılan çağrıdan sonra geçerlidir.

```
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;
```

## <a name="canimationgroupremovekeyframes"></a><a name="removekeyframes"></a> CAnimationGroup:: RemoveKeyframes

Bir animasyon grubuna ait olan tüm ana kareleri kaldırır ve isteğe bağlı olarak yok eder.

```cpp
void RemoveKeyframes();
```

### <a name="remarks"></a>Açıklamalar

M_bAutodestroyKeyframes üyesi TRUE ise, ana kareler kaldırılır ve yok edilir; Aksi takdirde, ana kareler iç listesinden kaldırılır.

## <a name="canimationgroupremovetransitions"></a><a name="removetransitions"></a> CAnimationGroup:: Removetransıtions

Animasyon grubuna ait olan animasyon nesnelerinden geçişleri kaldırır.

```cpp
void RemoveTransitions();
```

### <a name="remarks"></a>Açıklamalar

M_bAutoclearTransitions bayrağı TRUE olarak ayarlanırsa, bu yöntem gruba ait olan tüm animasyon nesnelerinin üzerinde döngü yapar ve CAnimationObject:: Cleargeçişler (FALSE) öğesini çağırır.

## <a name="canimationgroupschedule"></a><a name="schedule"></a> CAnimationGroup:: Schedule

Belirtilen zamanda bir animasyon zamanlar.

```
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```

### <a name="parameters"></a>Parametreler

*pTimer*<br/>
Animasyon süreölçeri işaretçisi.

*ışınızda*<br/>
Animasyonun zaman çizelgesine yönelik süreyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa doğru; Yöntem başarısız olursa ya da Bscheduleile kscheduleçağrılmamışsa yanlış olarak ayarlanır.

### <a name="remarks"></a>Açıklamalar

Belirtilen zamanda bir animasyon zamanlamak için bu işlevi çağırın. Şimdi Bscheduleile canlandır ' i çağırmanız gerekir.

## <a name="canimationgroupsetautodestroytransitions"></a><a name="setautodestroytransitions"></a> CAnimationGroup:: Setautodestroygeçişler

Gruba ait olan tüm animasyon nesnelerinin geçişleri otomatik olarak yok eder.

```cpp
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*bAutoDestroy*<br/>
Geçişlerin nasıl yok yapılacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu değeri yalnızca yığında geçişler ayırdıysanız FALSE olarak ayarlayın. Varsayılan değer TRUE 'dur, bu nedenle geçiş nesnelerinin Yeni işleç kullanılarak ayrılması kesinlikle önerilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
