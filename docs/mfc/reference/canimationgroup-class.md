---
title: CAnimationGroup sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: b05de00697aa019382014402f7701a8341da5198
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512924"
---
# <a name="canimationgroup-class"></a>CAnimationGroup sınıfı

Animasyon film şeridi, animasyon nesneleri ve geçişleri animasyon tanımlamak için bir araya getiren bir animasyon grubu uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationGroup;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationGroup::CAnimationGroup](#canimationgroup)|Bir animasyon grubu oluşturur.|
|[CAnimationGroup:: ~ CAnimationGroup](#canimationgroup__~canimationgroup)|Yıkıcı. Bir animasyon grubu yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationGroup::Animate](#animate)|Bir grubu canlandırır.|
|[CAnimationGroup::ApplyTransitions](#applytransitions)|Geçişleri animasyon nesneler için geçerlidir.|
|[CAnimationGroup::FindAnimationObject](#findanimationobject)|Belirtilen bir animasyon değişkenini içeren bir animasyon nesne bulur.|
|[CAnimationGroup::GetGroupID](#getgroupid)|GroupID döndürür.|
|[CAnimationGroup::RemoveKeyframes](#removekeyframes)|Kaldırır ve isteğe bağlı olarak bir animasyon gruba ait tüm ana kareleri yok eder.|
|[CAnimationGroup::RemoveTransitions](#removetransitions)|Bir animasyon grubuna ait animasyon nesneleri geçişleri kaldırır.|
|[CAnimationGroup::Schedule](#schedule)|Belirtilen zamanda bir animasyon zamanlar.|
|[CAnimationGroup::SetAutodestroyTransitions](#setautodestroytransitions)|Geçişleri otomatik olarak gruba ait tüm animasyon nesneleri yok yönlendirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationGroup::AddKeyframes](#addkeyframes)|Ana kareleri bir film şeridini ekler Yardımcısı.|
|[CAnimationGroup::AddTransitions](#addtransitions)|Geçiş için görsel taslak ekler Yardımcısı.|
|[CAnimationGroup::CreateTransitions](#createtransitions)|COM geçiş nesneleri oluşturur Yardımcısı.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationGroup::m_bAutoclearTransitions](#m_bautocleartransitions)|Gruba ait animasyon nesneleri geçişler temizleme belirtir. Bu üye TRUE ise, bir animasyon zamanlandıysa geçişleri otomatik olarak kaldırılır. Aksi takdirde, geçişleri el ile kaldırmanız gerekir.|
|[CAnimationGroup::m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|Animasyon nesnelerini yok etme belirtir. Bu parametre TRUE ise Grup kaldırıldığında animasyon nesneleri otomatik olarak edileceği. Aksi takdirde animasyon nesneleri elle yok edilmelidir. Varsayılan değer FALSE olur. Yalnızca gruba ait tüm animasyon nesneleri işleci ile yeni dinamik olarak ayrılır, bu değeri TRUE olarak ayarlayın.|
|[CAnimationGroup::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|Ana kareleri yok etmek nasıl belirtir. Bu değer TRUE ise, tüm ana kareleri kaldırıldı ve yok; Aksi takdirde bunlar yalnızca listeden kaldırılır. Varsayılan değer True'dur.|
|[CAnimationGroup::m_lstAnimationObjects](#m_lstanimationobjects)|Animasyon nesnelerin bir listesini içerir.|
|[CAnimationGroup::m_lstKeyFrames](#m_lstkeyframes)|Ana kareleri listesini içerir.|
|[CAnimationGroup::m_pStoryboard](#m_pstoryboard)|Animasyon film şeridi işaret eder. Bu işaretçinin animasyon ekle çağrıda sonra yalnızca geçerli değil.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationGroup::m_nGroupID](#m_ngroupid)|Animasyon grubun benzersiz bir tanımlayıcı.|
|[CAnimationGroup::m_pParentController](#m_pparentcontroller)|Bu grubun ait olduğu animasyon denetleyicisini bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

Animasyon nesneleri CAnimationController::AddAnimationObject kullanarak eklediğinizde, animasyon grupları animasyon denetleyicisini (CAnimationController) tarafından otomatik olarak oluşturulur. Bir animasyon Grup genellikle animasyon grupları denetlemek için bir parametre olarak geçen GroupID tarafından tanımlanır. Komutun grup kimliği, yeni bir animasyon grubuna eklenen ilk animasyon nesnesinden alınır. Kapsüllenmiş animasyon film şeridi CAnimationController::AnimateGroup çağırın ve ortak üye m_pStoryboard erişilebilen sonra oluşturulur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAnimationGroup`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="_dtorcanimationgroup"></a>  CAnimationGroup:: ~ CAnimationGroup

Yıkıcı. Bir animasyon grubu yok ediliyorken çağırılır.

```
~CAnimationGroup();
```

##  <a name="addkeyframes"></a>  CAnimationGroup::AddKeyframes

Ana kareleri bir film şeridini ekler Yardımcısı.

```
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Bir görsel taslak COM nesnesi için bir işaretçi.

*bAddDeep*<br/>
Bu yöntem üzerinde başka ana karelerde bağımlı film şeridi ana kareleri eklemeniz gerekip gerekmediğini belirtir.

##  <a name="addtransitions"></a>  CAnimationGroup::AddTransitions

Geçiş için görsel taslak ekler Yardımcısı.

```
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Bir görsel taslak COM nesnesi için bir işaretçi.

*bDependOnKeyframes*

##  <a name="animate"></a>  CAnimationGroup::Animate

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

Yöntem başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem iç bir görsel taslağı oluşturur, oluşturur ve geçişler için geçerlidir ve bScheduleNow TRUE ise bir animasyon zamanlar. BScheduleNow FALSE ise, belirtilen zamanda animasyonu başlatmak için zamanlama çağrı gerekir.

##  <a name="applytransitions"></a>  CAnimationGroup::ApplyTransitions

Geçişleri animasyon nesneler için geçerlidir.

```
void ApplyTransitions();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, hata ayıklama modunda görsel taslak olmayan oluşturulduğunu ONAYLAR. İlk olarak, tüm geçişler oluşturur sonra "statik" ana kareler (üzerinde uzaklıkları bağımlı ana kareleri) ekler, üzerinde ana kareleri bağlı olmayan geçişler ekler, ana kareleri geçişleri bağlı olarak ve diğer ana kareleri ekler ve en son ana kareleri üzerinde bağımlı geçişleri ekler .

##  <a name="canimationgroup"></a>  CAnimationGroup::CAnimationGroup

Bir animasyon grubu oluşturur.

```
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```

### <a name="parameters"></a>Parametreler

*pParentController*<br/>
Bir grup oluşturur animasyon denetleyicisini bir işaretçi.

*nGroupID*<br/>
GroupID belirtir.

##  <a name="createtransitions"></a>  CAnimationGroup::CreateTransitions

COM geçiş nesneleri oluşturur Yardımcısı.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, aksi takdirde FALSE true'dur.

##  <a name="findanimationobject"></a>  CAnimationGroup::FindAnimationObject

Belirtilen bir animasyon değişkenini içeren bir animasyon nesne bulur.

```
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametreler

*pVariable*<br/>
Animasyon değişkeninin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Animasyon nesne veya animasyon nesne bulunamazsa NULL bir işaretçi.

##  <a name="getgroupid"></a>  CAnimationGroup::GetGroupID

GroupID döndürür.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir grup tanımlayıcısı.

##  <a name="m_bautocleartransitions"></a>  CAnimationGroup::m_bAutoclearTransitions

Gruba ait animasyon nesneleri geçişler temizleme belirtir. Bu üye TRUE ise, bir animasyon zamanlandıysa geçişleri otomatik olarak kaldırılır. Aksi takdirde, geçişleri el ile kaldırmanız gerekir.

```
BOOL m_bAutoclearTransitions;
```

##  <a name="m_bautodestroyanimationobjects"></a>  CAnimationGroup::m_bAutodestroyAnimationObjects

Animasyon nesnelerini yok etme belirtir. Bu parametre TRUE ise Grup kaldırıldığında animasyon nesneleri otomatik olarak edileceği. Aksi takdirde animasyon nesneleri elle yok edilmelidir. Varsayılan değer FALSE olur. Yalnızca gruba ait tüm animasyon nesneleri işleci ile yeni dinamik olarak ayrılır, bu değeri TRUE olarak ayarlayın.

```
BOOL m_bAutodestroyAnimationObjects;
```

##  <a name="m_bautodestroykeyframes"></a>  CAnimationGroup::m_bAutodestroyKeyframes

Ana kareleri yok etmek nasıl belirtir. Bu değer TRUE ise, tüm ana kareleri kaldırıldı ve yok; Aksi takdirde bunlar yalnızca listeden kaldırılır. Varsayılan değer True'dur.

```
BOOL m_bAutodestroyKeyframes;
```

##  <a name="m_lstanimationobjects"></a>  CAnimationGroup::m_lstAnimationObjects

Animasyon nesnelerin bir listesini içerir.

```
CObList m_lstAnimationObjects;
```

##  <a name="m_lstkeyframes"></a>  CAnimationGroup::m_lstKeyFrames

Ana kareleri listesini içerir.

```
CObList m_lstKeyFrames;
```

##  <a name="m_ngroupid"></a>  CAnimationGroup::m_nGroupID

Animasyon grubun benzersiz bir tanımlayıcı.

```
UINT32 m_nGroupID;
```

##  <a name="m_pparentcontroller"></a>  CAnimationGroup::m_pParentController

Bu grubun ait olduğu animasyon denetleyicisini bir işaretçi.

```
CAnimationController* m_pParentController;
```

##  <a name="m_pstoryboard"></a>  CAnimationGroup::m_pStoryboard

Animasyon film şeridi işaret eder. Bu işaretçinin animasyon ekle çağrıda sonra yalnızca geçerli değil.

```
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;
```

##  <a name="removekeyframes"></a>  CAnimationGroup::RemoveKeyframes

Kaldırır ve isteğe bağlı olarak bir animasyon gruba ait tüm ana kareleri yok eder.

```
void RemoveKeyframes();
```

### <a name="remarks"></a>Açıklamalar

Ana kareleri kaldırılır ve yok, TRUE m_bAutodestroyKeyframes üyesi, aksi takdirde ana kareleri ana kareleri iç listesinden yalnızca kaldırılır.

##  <a name="removetransitions"></a>  CAnimationGroup::RemoveTransitions

Bir animasyon grubuna ait animasyon nesneleri geçişleri kaldırır.

```
void RemoveTransitions();
```

### <a name="remarks"></a>Açıklamalar

M_bAutoclearTransitions bayrağı TRUE olarak ayarlandıysa, bu yöntem gruba ait tüm animasyon nesneleri üzerinden döngüye girer ve CAnimationObject::ClearTransitions(FALSE) çağırır.

##  <a name="schedule"></a>  CAnimationGroup::Schedule

Belirtilen zamanda bir animasyon zamanlar.

```
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```

### <a name="parameters"></a>Parametreler

*pTimer*<br/>
Animasyon Zamanlayıcı işaretçisi.

*saat*<br/>
Animasyon zamanlamak için süreyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; FALSE yöntem başarısız olursa veya animasyon olarak oluşturmak, FALSE olarak ayarlanmış bScheduleNow ile çağrılmadı.

### <a name="remarks"></a>Açıklamalar

Belirtilen zamanda bir animasyon zamanlamak için bu işlevi çağırın. FALSE olarak ayarlamanız bScheduleNow ile animasyon ekle çağırmanız gerekir.

##  <a name="setautodestroytransitions"></a>  CAnimationGroup::SetAutodestroyTransitions

Geçişleri otomatik olarak gruba ait tüm animasyon nesneleri yok yönlendirir.

```
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametreler

*bAutoDestroy*<br/>
Geçişleri yok etmek nasıl belirtir.

### <a name="remarks"></a>Açıklamalar

Bu değer yalnızca yığında geçişleri ayırdığınızda FALSE ayarlayın. Varsayılan değer doğru ise, bu nedenle, yüksek oranda işleci kullanarak yeni geçiş nesneleri ayırmak için önerilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
