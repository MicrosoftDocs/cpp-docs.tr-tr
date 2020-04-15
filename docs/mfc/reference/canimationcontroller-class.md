---
title: CAnimationController Sınıfı
ms.date: 03/27/2019
f1_keywords:
- CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::AddAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::AddKeyframeToGroup
- AFXANIMATIONCONTROLLER/CAnimationController::AnimateGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CleanUpGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CreateKeyframe
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationManagerEvent
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnablePriorityComparisonHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnableStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::GetKeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionLibrary
- AFXANIMATIONCONTROLLER/CAnimationController::IsAnimationInProgress
- AFXANIMATIONCONTROLLER/CAnimationController::IsValid
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnBeforeAnimationStart
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCancel
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCompress
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityConclude
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityTrim
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAllAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationController::ScheduleGroup
- AFXANIMATIONCONTROLLER/CAnimationController::SetRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::UpdateAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::OnAfterSchedule
- AFXANIMATIONCONTROLLER/CAnimationController::gkeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::m_bIsValid
- AFXANIMATIONCONTROLLER/CAnimationController::m_lstAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::m_pRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionLibrary
helpviewer_keywords:
- CAnimationController [MFC], CAnimationController
- CAnimationController [MFC], AddAnimationObject
- CAnimationController [MFC], AddKeyframeToGroup
- CAnimationController [MFC], AnimateGroup
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], CreateKeyframe
- CAnimationController [MFC], EnableAnimationManagerEvent
- CAnimationController [MFC], EnableAnimationTimerEventHandler
- CAnimationController [MFC], EnablePriorityComparisonHandler
- CAnimationController [MFC], EnableStoryboardEventHandler
- CAnimationController [MFC], FindAnimationGroup
- CAnimationController [MFC], FindAnimationObject
- CAnimationController [MFC], GetKeyframeStoryboardStart
- CAnimationController [MFC], GetUIAnimationManager
- CAnimationController [MFC], GetUIAnimationTimer
- CAnimationController [MFC], GetUITransitionFactory
- CAnimationController [MFC], GetUITransitionLibrary
- CAnimationController [MFC], IsAnimationInProgress
- CAnimationController [MFC], IsValid
- CAnimationController [MFC], OnAnimationIntegerValueChanged
- CAnimationController [MFC], OnAnimationManagerStatusChanged
- CAnimationController [MFC], OnAnimationTimerPostUpdate
- CAnimationController [MFC], OnAnimationTimerPreUpdate
- CAnimationController [MFC], OnAnimationTimerRenderingTooSlow
- CAnimationController [MFC], OnAnimationValueChanged
- CAnimationController [MFC], OnBeforeAnimationStart
- CAnimationController [MFC], OnHasPriorityCancel
- CAnimationController [MFC], OnHasPriorityCompress
- CAnimationController [MFC], OnHasPriorityConclude
- CAnimationController [MFC], OnHasPriorityTrim
- CAnimationController [MFC], OnStoryboardStatusChanged
- CAnimationController [MFC], OnStoryboardUpdated
- CAnimationController [MFC], RemoveAllAnimationGroups
- CAnimationController [MFC], RemoveAnimationGroup
- CAnimationController [MFC], RemoveAnimationObject
- CAnimationController [MFC], RemoveTransitions
- CAnimationController [MFC], ScheduleGroup
- CAnimationController [MFC], SetRelatedWnd
- CAnimationController [MFC], UpdateAnimationManager
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], OnAfterSchedule
- CAnimationController [MFC], gkeyframeStoryboardStart
- CAnimationController [MFC], m_bIsValid
- CAnimationController [MFC], m_lstAnimationGroups
- CAnimationController [MFC], m_pAnimationManager
- CAnimationController [MFC], m_pAnimationTimer
- CAnimationController [MFC], m_pRelatedWnd
- CAnimationController [MFC], m_pTransitionFactory
- CAnimationController [MFC], m_pTransitionLibrary
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
ms.openlocfilehash: 34a02567bfeb76666cc38ccf05dcc285a1f658f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369763"
---
# <a name="canimationcontroller-class"></a>CAnimationController Sınıfı

Animasyonoluşturmak ve yönetmek için merkezi bir arabirim sağlayan animasyon denetleyicisini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationController : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationController::CAnimationController](#canimationcontroller)|Animasyon denetleyicisi oluşturuyor.|
|[CAnimationController::~CAnimationController](#_dtorcanimationcontroller)|Yıkıcı. Animasyon denetleyici nesnesi yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationController::AddAnimationObject](#addanimationobject)|Animasyon denetleyicisine ait bir gruba animasyon nesnesi ekler.|
|[CAnimationController::AddKeyframeToGroup](#addkeyframetogroup)|Gruba bir anahtar kare ekler.|
|[CAnimationController::AnimateGroup](#animategroup)|Animasyonu çalıştırmak için bir grup hazırlar ve isteğe bağlı olarak zamanlar.|
|[CAnimationController::Temizleme Grubu](#cleanupgroup)|Fazla Yüklendi. Animasyon zamanlandığında grubu temizlemek için çerçeve tarafından çağrılır.|
|[CAnimationController::Anahtar Çerçevesi Oluşturma](#createkeyframe)|Fazla Yüklendi. Geçişe bağlı bir anahtar çerçevesi oluşturur ve belirtilen gruba ekler.|
|[CAnimationController::EnableAnimationManagerOlay](#enableanimationmanagerevent)|Animasyon yöneticisinin durumu değiştiğinde aramak için bir işleyici ayarlar veya yayımlar.|
|[CAnimationController::EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|Zamanlama olayları için bir işleyici ve zamanlama güncelleştirmeleri için işleyicisi ayarlar veya yayımlar.|
|[CAnimationController::EnablePriorityComparisonHandler](#enableprioritycomparisonhandler)|Zamanlanmış bir film şeridinin iptal edilip edilmeyeceğini, sonuçlandırılıp kesilemeyeceğini veya sıkıştırılıp sıkıştırılamayacağını belirlemek için çağırmak üzere öncelikli karşılaştırma işleyicisini ayarlar veya yayımlar.|
|[CAnimationController::EnableStoryboardEventHandler](#enablestoryboardeventhandler)|Film şeridi durumu ve güncelleştirme olayları için bir işleyici ayarlar veya yayımlar.|
|[CAnimationController::FindAnimationGroup](#findanimationgroup)|Fazla Yüklendi. Film şeridine göre bir animasyon grubu bulur.|
|[CAnimationController::FindAnimationObject](#findanimationobject)|Belirli bir animasyon değişkenini içeren animasyon nesnesi bulur.|
|[CAnimationController::GetKeyframeStoryboardBaşlat](#getkeyframestoryboardstart)|Film şeridinin başlangıcını tanımlayan bir anahtar çerçevesi döndürür.|
|[CAnimationController::GetuiAnimationManager](#getuianimationmanager)|Kapsüllenmiş IUIAnimationManager nesnesine erişim sağlar.|
|[CAnimationController::GetUIAnimationTimer](#getuianimationtimer)|Kapsüllenmiş IUIAnimationTimer nesnesine erişim sağlar.|
|[CanimationController::GetuitransitionFactory](#getuitransitionfactory)|Geçiş kitaplığı oluşturulduysa, IUIAnimationTransitionFactory arabirimi veya NULL için bir işaretçi.|
|[CanimationController::GetuiTransitionLibrary](#getuitransitionlibrary)|Kapsüllü IUIAnimationTransitionLibrary nesnesine erişim sağlar.|
|[CAnimationController::IsAnimationInProgress](#isanimationinprogress)|En az bir grubun animasyon oynatılıp oynatmadığını söyler.|
|[CAnimationController::Geçersiz](#isvalid)|Animasyon denetleyicisi geçerli olup olmadığını söyler.|
|[CAnimationController::OnAnimationIntegerValueChanged](#onanimationintegervaluechanged)|Animasyon değişkeninin insa değeri değiştiğinde çerçeve tarafından çağrılır.|
|[CAnimationController::OnAnimationManagerStatus Değiştirildi](#onanimationmanagerstatuschanged)|Animasyon yöneticisinden DurumDeğiştirildi olayına yanıt olarak çerçeve tarafından çağrıldı.|
|[CAnimationController::OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|Animasyon güncelleştirmesi tamamlandıktan sonra çerçeve tarafından çağrılır.|
|[CAnimationController::OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|Animasyon güncelleştirmesi başlamadan önce çerçeve tarafından çağrılır.|
|[CAnimationController::OnAnimationTimerRenderingTooSlow](#onanimationtimerrenderingtooslow)|Animasyoniçin görüntüleme kare hızı minimum arzu edilen kare hızının altına düştüğünde çerçeve tarafından çağrılır.|
|[CAnimationController::OnAnimationValue Changed](#onanimationvaluechanged)|Animasyon değişkeninin değeri değiştiğinde çerçeve tarafından çağrılır.|
|[CAnimationController::OnbeforeAnimationStart](#onbeforeanimationstart)|Animasyon zamanlanmadan hemen önce çerçeve tarafından çağrılır.|
|[CanimationController::OnhasPriorityCancel](#onhasprioritycancel)|Zamanlama çakışmalarını gidermek için çerçeve tarafından çağrıldı.|
|[CanimationController::OnHasPriorityCompress](#onhasprioritycompress)|Zamanlama çakışmalarını gidermek için çerçeve tarafından çağrıldı.|
|[CanimationController::OnHasPriorityconclude](#onhaspriorityconclude)|Zamanlama çakışmalarını gidermek için çerçeve tarafından çağrıldı.|
|[CanimationController::OnhasPrioritytrim](#onhasprioritytrim)|Zamanlama çakışmalarını gidermek için çerçeve tarafından çağrıldı.|
|[CAnimationController::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Film şeridi durumu değiştiğinde çerçeve tarafından çağrılır.|
|[CAnimationController::OnStoryboardGüncel](#onstoryboardupdated)|Film şeridi güncelleştirildiğinde çerçeve tarafından çağrılır.|
|[CAnimationController::RemoveAllAnimationGroups](#removeallanimationgroups)|Tüm animasyon gruplarını animasyon denetleyicisinden kaldırır.|
|[CAnimationController::RemoveAnimationGroup](#removeanimationgroup)|Animasyon denetleyicisinden belirtilen kimliği olan bir animasyon grubunu kaldırır.|
|[CAnimationController::RemoveAnimationObject](#removeanimationobject)|Animasyon nesnesi animasyon denetleyicisinden kaldırın.|
|[CAnimationController::Geçişleri Kaldırma](#removetransitions)|Belirtilen gruba ait animasyon nesnelerinden geçişleri kaldırır.|
|[CAnimationController::Program Grubu](#schedulegroup)|Animasyon planlar.|
|[CAnimationController::SetRelatedWnd](#setrelatedwnd)|Animasyon denetleyicisi ve bir pencere arasında bir ilişki kurar.|
|[CAnimationController::UpdateAnimationManager](#updateanimationmanager)|Animasyon yöneticisini tüm animasyon değişkenlerinin değerlerini güncelleştirmeye yönlendirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationController::Temizleme Grubu](#cleanupgroup)|Fazla Yüklendi. Grubu temizleyen bir yardımcı.|
|[CAnimationController::OnafterSchedule](#onafterschedule)|Belirtilen grup için bir animasyon zamanlandığında çerçeve tarafından çağrılır.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationController::gkeyframeStoryboardBaşlat](#g_keyframestoryboardstart)|Film şeridinin başlangıcını temsil eden bir anahtar kare.|
|[CAnimationController::m_bIsValid](#m_bisvalid)|Animasyon denetleyicinin geçerli olup olmadığını belirtir. Geçerli işletim sistemi Windows Animasyon API'sını desteklemiyorsa, bu üye FALSE olarak ayarlanır.|
|[CAnimationController::m_lstAnimationGroups](#m_lstanimationgroups)|Bu animasyon denetleyicisine ait animasyon gruplarının listesi.|
|[CAnimationController::m_pAnimationManager](#m_panimationmanager)|Animasyon Yöneticisi COM nesnesine bir işaretçi depolar.|
|[CAnimationController::m_pAnimationTimer](#m_panimationtimer)|Animasyon Zamanlayıcı COM nesnesine bir işaretçi depolar.|
|[CAnimationController::m_pRelatedWnd](#m_prelatedwnd)|Animasyon yöneticisinin durumu değiştiğinde veya güncelleştirme sonrası olay oluştuğunda otomatik olarak yeniden çizilebilen ilgili bir CWnd nesnesine işaretçi. NULL olabilir.|
|[CAnimationController::m_pTransitionFactory](#m_ptransitionfactory)|Geçiş Fabrikası COM nesnesine işaretçi depolar.|
|[CAnimationController::m_pTransitionLibrary](#m_ptransitionlibrary)|Geçiş Kitaplığı COM nesnesine işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

CAnimationController sınıfı animasyonları yöneten anahtar sınıftır. Bir uygulamada bir veya daha fazla animasyon denetleyicisi örneği oluşturabilir ve isteğe bağlı olarak, cAnimationController::SetRelatedWnd kullanarak animasyon denetleyicisi örneğini CWnd nesnesine bağlayabilirsiniz. Animasyon yöneticisi durumu değiştiğinde veya animasyon zamanlayıcısı güncelleştirildiğinde, bu bağlantının ilgili pencereye otomatik olarak WM_PAINT ileti göndermesi gerekir. Bu ilişkiyi etkinleştirmezseniz, animasyonu el ile görüntüleyen bir pencereyi yeniden çizmeniz gerekir. Bu amaçla CAnimationController bir sınıf türetmek ve OnAnimationManagerStatusChanged ve / veya OnAnimationTimerPostUpdate geçersiz ve gerektiğinde bir veya daha fazla pencere geçersiz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CAnimationController`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationcontrollercanimationcontroller"></a><a name="_dtorcanimationcontroller"></a>CAnimationController::~CAnimationController

Yıkıcı. Animasyon denetleyici nesnesi yok edilirken çağrılır.

```
virtual ~CAnimationController(void);
```

## <a name="canimationcontrolleraddanimationobject"></a><a name="addanimationobject"></a>CAnimationController::AddAnimationObject

Animasyon denetleyicisine ait bir gruba animasyon nesnesi ekler.

```
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```

### <a name="parameters"></a>Parametreler

*Pobject*<br/>
Animasyon nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Işlev başarılı olursa pObject eklendiği varolan veya yeni animasyon grubuna işaretçi; NULL eğer pObject zaten başka bir animasyon denetleyicisine ait bir gruba eklenmiştir.

### <a name="remarks"></a>Açıklamalar

Animasyon denetleyicisine animasyon nesnesi eklemek için bu yöntemi arayın. Nesnenin GroupID'sine göre bir gruba bir nesne eklenir (bkz. CAnimationBaseObject::SetID). Animasyon denetleyicisi, belirtilen GroupID ile eklenen ilk nesneyse yeni bir grup oluşturur. Animasyon nesnesi yalnızca bir animasyon denetleyicisine eklenebilir. Başka bir denetleyiciye nesne eklemeniz gerekiyorsa, önce RemoveAnimationObject'i arayın. Bir gruba zaten ekilmiş bir nesne için yeni GroupID ile SetID'yi çağırırsanız, nesne eski gruptan kaldırılır ve belirtilen kimliği olan başka bir gruba eklenir.

## <a name="canimationcontrolleraddkeyframetogroup"></a><a name="addkeyframetogroup"></a>CAnimationController::AddKeyframeToGroup

Gruba bir anahtar kare ekler.

```
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe);
```

### <a name="parameters"></a>Parametreler

*nGroupID*<br/>
Grup Kimliğini belirtir.

*pKeyframe*<br/>
Anahtar kare için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Genellikle bu yöntemi aramanız gerekmez, CAnimationController kullanın::CreateKeyframe yerine, oluşturulan anahtar çerçeveyi otomatik olarak oluşturur ve gruba ekler.

## <a name="canimationcontrolleranimategroup"></a><a name="animategroup"></a>CAnimationController::AnimateGroup

Animasyonu çalıştırmak için bir grup hazırlar ve isteğe bağlı olarak zamanlar.

```
BOOL AnimateGroup(
    UINT32 nGroupID,
    BOOL bScheduleNow = TRUE);
```

### <a name="parameters"></a>Parametreler

*nGroupID*<br/>
GroupID'yi belirtir.

*bScheduleNow*<br/>
Animasyonun hemen çalıştırılıp çalıştırılmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Animasyon başarıyla zamanlandı ve çalıştırıldıysa TRUE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, gerçek iş storyboard oluşturma, animasyon değişkenleri ekleme, geçişleri uygulama ve anahtar kareler ayar yapar. bScheduleNow'u FALSE olarak ayarlarsanız zamanlamayı geciktirmek mümkündür. Bu durumda, belirtilen grup animasyon için ayarlanmış bir film şeridi tutar. Bu noktada, film şeridi ve animasyon değişkenleri için olayları ayarlayabilirsiniz. Animasyonu gerçekten çalıştırmanız gerektiğinde CAnimationController::ScheduleGroup'u arayın.

## <a name="canimationcontrollercanimationcontroller"></a><a name="canimationcontroller"></a>CAnimationController::CAnimationController

Animasyon denetleyicisi oluşturuyor.

```
CAnimationController(void);
```

## <a name="canimationcontrollercleanupgroup"></a><a name="cleanupgroup"></a>CAnimationController::Temizleme Grubu

Animasyon zamanlandığında grubu temizlemek için çerçeve tarafından çağrılır.

```
void CleanUpGroup(UINT32 nGroupID);
void CleanUpGroup(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parametreler

*nGroupID*<br/>
GroupID'yi belirtir.

*pGroup*<br/>
Temizlemek için animasyon grubu için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir animasyon zamanlandıktan sonra alakalı olmadıklarından, belirtilen gruptan tüm geçişleri ve anahtar kareleri kaldırır.

## <a name="canimationcontrollercreatekeyframe"></a><a name="createkeyframe"></a>CAnimationController::Anahtar Çerçevesi Oluşturma

Geçişe bağlı bir anahtar çerçevesi oluşturur ve belirtilen gruba ekler.

```
CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,
    CBaseTransition* pTransition);

CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>Parametreler

*nGroupID*<br/>
Anahtar çerçevesinin oluşturulduğu Grup Kimliğini belirtir.

*pGeçiş*<br/>
Geçiş için bir işaretçi. Bu geçişten sonra anahtar çerçeve film şeridine eklenir.

*pKeyframe*<br/>
Bu anahtar çerçevesi için anahtar çerçevesi temel almak için bir işaretçi.

*Uzaklık*<br/>
pKeyframe tarafından belirtilen temel anahtar çerçevesinden saniyeler içinde mahsup edin.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa yeni oluşturulan anahtar çerçevesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Döndürülen işaretçiyi depolayabilir ve diğer anahtar kareleri yeni oluşturulan anahtar çerçevesine dayandırabilirsiniz (ikinci aşırı yüklemeye bakın). Anahtar karelerde geçişlere başlamak mümkündür - Bkz. CBaseTransition::SetKeyframes. Animasyon grupları tarafından otomatik olarak silindiğinden, bu şekilde oluşturulan anahtar kareleri silmeniz gerekmez. Diğer anahtar karelere ve geçişlere dayalı anahtar kareler oluştururken dikkatli olun ve dairesel başvurulardan kaçının.

## <a name="canimationcontrollerenableanimationmanagerevent"></a><a name="enableanimationmanagerevent"></a>CAnimationController::EnableAnimationManagerOlay

Animasyon yöneticisinin durumu değiştiğinde aramak için bir işleyici ayarlar veya yayımlar.

```
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
Bir işleyiciayarlanıp ayarlamayacağını veya serbest bırakılamayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Işleyici başarıyla ayarlanmış veya serbest bırakılmışsa DOĞRU.

### <a name="remarks"></a>Açıklamalar

Bir işleyici ayarlandığında (etkinleştirilmiş) Windows Animasyon, animasyon yöneticisinin durumu değiştiğinde OnAnimationManagerStatusChanged'i çağırır.

## <a name="canimationcontrollerenableanimationtimereventhandler"></a><a name="enableanimationtimereventhandler"></a>CAnimationController::EnableAnimationTimerEventHandler

Zamanlama olayları için bir işleyici ve zamanlama güncelleştirmeleri için işleyicisi ayarlar veya yayımlar.

```
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
Işleyicileri ayarlayıp ayarlamayacağını veya serbest bırakmayacağını belirtir.

*idleBehavior*<br/>
Zamanlayıcı güncelleştirme işleyicisi için boşta davranışı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Işleyiciler başarıyla ayarlanmış veya serbest bırakılmışsa DOĞRU; Bu yöntem işleyicileri önce bırakmadan ikinci kez çağrılırsa veya başka bir hata oluşursa YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Işleyiciler ayarlandığında (etkin) Windows Animasyon API onAnimationTimerPreUpdate, OnAnimationTimerPostUpdate, OnRenderingTooSlow yöntemleri çağırır. Windows Animasyon API güncelleştirme film şeridine izin vermek için animasyon zamanlayıcılarını etkinleştirmeniz gerekir. Aksi takdirde, animasyon yöneticisini tüm animasyon değişkenlerinin değerlerini güncelleştirmeye yönlendirmek için CAnimationController::UpdateAnimationManager'ı aramanız gerekir.

## <a name="canimationcontrollerenableprioritycomparisonhandler"></a><a name="enableprioritycomparisonhandler"></a>CAnimationController::EnablePriorityComparisonHandler

Zamanlanmış bir film şeridinin iptal edilip edilmeyeceğini, sonuçlandırılıp kesilemeyeceğini veya sıkıştırılıp sıkıştırılamayacağını belirlemek için çağırmak üzere öncelikli karşılaştırma işleyicisini ayarlar veya yayımlar.

```
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```

### <a name="parameters"></a>Parametreler

*dwHandlerType*<br/>
UI_ANIMATION_PHT_ bayraklarının (bkz. açıklamalar) birleşimi, hangi işleyicilerin ayarlayacağını veya serbest bırakılacaklarını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Işleyici başarıyla ayarlanmış veya serbest bırakılmışsa DOĞRU.

### <a name="remarks"></a>Açıklamalar

Bir işleyici ayarlandığında (etkinleştirilmiş) Windows Animasyon dwHandlerType bağlı olarak aşağıdaki sanal yöntemleri çağırır: OnHasPriorityCancel, OnHasPriorityConclude, OnHasPriorityTrim, OnHasPriorityCompress. dwHandler aşağıdaki bayrakların bir birleşimi olabilir: UI_ANIMATION_PHT_NONE - tüm işleyicileri UI_ANIMATION_PHT_CANCEL serbest bırak - karşılaştırma işleyicisini UI_ANIMATION_PHT_CONCLUDE ayarla - Karşılaştırma işleyicisini UI_ANIMATION_PHT_COMPRESS ayarla - Karşılaştırma işleyicisini UI_ANIMATION_PHT_TRIM ayarla - Trim karşılaştırma işleyicisini UI_ANIMATION_PHT_CANCEL_REMOVE ayarla - Karşılaştırma işleyicisini UI_ANIMATION_PHT_CONCLUDE_REMOVE kaldır - Karşılaştırma işleyicisini UI_ANIMATION_PHT_COMPRESS_REMOVE kaldır - Karşılaştırma iş UI_ANIMATION_PHT_TRIM_REMOVEleyicisini sıkıştırı kaldır - Kırpma karşılaştırma işleyicisi kaldırmak

## <a name="canimationcontrollerenablestoryboardeventhandler"></a><a name="enablestoryboardeventhandler"></a>CAnimationController::EnableStoryboardEventHandler

Film şeridi durumu ve güncelleştirme olayları için bir işleyici ayarlar veya yayımlar.

```
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*nGroupID*<br/>
Grup Kimliğini belirtir.

*bEtkinleştir*<br/>
Bir işleyiciayarlanıp ayarlamayacağını veya serbest bırakılamayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Işleyici başarıyla ayarlanmış veya serbest bırakılmışsa DOĞRU; Belirtilen animasyon grubu şimdi bulunursa veya belirtilen grup için animasyon başlatılmamışsa ve dahili film şeridi NULL ise FALSE.

### <a name="remarks"></a>Açıklamalar

Bir işleyici ayarlandığında (etkinleştirilmiş) Windows Animasyon API'si OnStoryboardStatusChanges ve OnStoryboardUpdated sanal yöntemleri çağırır. Bir işleyici CAnimationController sonra ayarlanmalıdır::Animasyon belirtilen animasyon grubu için çağrıldı, çünkü kapsüllü IUIAnimationStoryboard nesnesi oluşturur.

## <a name="canimationcontrollerfindanimationgroup"></a><a name="findanimationgroup"></a>CAnimationController::FindAnimationGroup

Grup kimliğine göre bir animasyon grubu bulur.

```
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parametreler

*nGroupID*<br/>
Bir GroupID belirtir.

*pStoryboard*<br/>
Bir film şeridi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen kimliği olan grup bulunamazsa animasyon grubu veya NULL için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanında bir animasyon grubu bulmak için bu yöntemi kullanın. Belirli GroupID'li ilk animasyon nesnesi animasyon denetleyicisine eklendiğinde bir grup oluşturulur ve animasyon gruplarıiç listesine eklenir.

## <a name="canimationcontrollerfindanimationobject"></a><a name="findanimationobject"></a>CAnimationController::FindAnimationObject

Belirli bir animasyon değişkenini içeren animasyon nesnesi bulur.

```
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,
    CAnimationBaseObject** ppObject,
    CAnimationGroup** ppGroup);
```

### <a name="parameters"></a>Parametreler

*pDeğişken*<br/>
Animasyon değişkenine işaretçi.

*ppNesne*<br/>
Çıkış. Animasyon nesnesi veya NULL için bir işaretçi içerir.

*ppGroup*<br/>
Çıkış. Animasyon nesnesini tutan animasyon grubuna işaretçi veya NULL içerir.

### <a name="return-value"></a>Dönüş Değeri

Nesne bulunursa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Gelen animasyon değişkeninden bir animasyon nesnesi bulmak gerektiğinde olay işleyicilerinden çağrılır.

## <a name="canimationcontrollergkeyframestoryboardstart"></a><a name="g_keyframestoryboardstart"></a>CAnimationController::gkeyframeStoryboardBaşlat

Film şeridinin başlangıcını temsil eden bir anahtar kare.

```
static CBaseKeyFrame gkeyframeStoryboardStart;
```

## <a name="canimationcontrollergetkeyframestoryboardstart"></a><a name="getkeyframestoryboardstart"></a>CAnimationController::GetKeyframeStoryboardBaşlat

Film şeridinin başlangıcını tanımlayan bir anahtar çerçevesi döndürür.

```
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```

### <a name="return-value"></a>Dönüş Değeri

Film şeridinin başlangıcını tanımlayan anahtar çerçevesine temel alan bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu anahtar çerçeveyi, bir hikaye şeridinin başladığı zamana göre diğer anahtar kareleri veya geçişleri temel almak için edinin.

## <a name="canimationcontrollergetuianimationmanager"></a><a name="getuianimationmanager"></a>CAnimationController::GetuiAnimationManager

Kapsüllenmiş IUIAnimationManager nesnesine erişim sağlar.

```
IUIAnimationManager* GetUIAnimationManager();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon yöneticisi oluşturma başarısız olursa, IUIAnimationManager arabirimi veya NULL için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli işletim sistemi Windows Animasyon API'yı desteklemiyorsa, bu yöntem NULL'u döndürür ve bundan sonra CAnimationController'daki sonraki tüm çağrılar::Geçerli return FALSE' da. Animasyon denetleyicisi tarafından sarılmayan arabirim yöntemlerini aramak için IUIAnimationManager'a erişmeniz gerekebilir.

## <a name="canimationcontrollergetuianimationtimer"></a><a name="getuianimationtimer"></a>CAnimationController::GetUIAnimationTimer

Kapsüllenmiş IUIAnimationTimer nesnesine erişim sağlar.

```
IUIAnimationTimer* GetUIAnimationTimer();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon zamanlayıcısı oluşturma başarısız olduysa, IUIAnimationTimer arabirimi veya NULL için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli işletim sistemi Windows Animasyon API'yı desteklemiyorsa, bu yöntem NULL'u döndürür ve bundan sonra CAnimationController'daki sonraki tüm çağrılar::Geçerli return FALSE' da.

## <a name="canimationcontrollergetuitransitionfactory"></a><a name="getuitransitionfactory"></a>CanimationController::GetuitransitionFactory

Geçiş kitaplığı oluşturulduysa, IUIAnimationTransitionFactory arabirimi veya NULL için bir işaretçi.

```
IUIAnimationTransitionFactory* GetUITransitionFactory();
```

### <a name="return-value"></a>Dönüş Değeri

Geçiş fabrikası oluşturma başarısız olduysa, IUIAnimationTransitionFactory veya NULL için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli işletim sistemi Windows Animasyon API'yı desteklemiyorsa, bu yöntem NULL'u döndürür ve bundan sonra CAnimationController'daki sonraki tüm çağrılar::Geçerli return FALSE' da.

## <a name="canimationcontrollergetuitransitionlibrary"></a><a name="getuitransitionlibrary"></a>CanimationController::GetuiTransitionLibrary

Kapsüllü IUIAnimationTransitionLibrary nesnesine erişim sağlar.

```
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```

### <a name="return-value"></a>Dönüş Değeri

Geçiş kitaplığı oluşturulduysa, IUIAnimationTransitionLibrary arabirimi veya NULL için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli işletim sistemi Windows Animasyon API'yı desteklemiyorsa, bu yöntem NULL'u döndürür ve bundan sonra CAnimationController'daki sonraki tüm çağrılar::Geçerli return FALSE' da.

## <a name="canimationcontrollerisanimationinprogress"></a><a name="isanimationinprogress"></a>CAnimationController::IsAnimationInProgress

En az bir grubun animasyon oynatılıp oynatmadığını söyler.

```
virtual BOOL IsAnimationInProgress();
```

### <a name="return-value"></a>Dönüş Değeri

Bu animasyon denetleyicisi için devam etmekte olan bir animasyon varsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Animasyon yöneticisinin durumunu denetler ve durum UI_ANIMATION_MANAGER_BUSY ysa TRUE döndürür.

## <a name="canimationcontrollerisvalid"></a><a name="isvalid"></a>CAnimationController::Geçersiz

Animasyon denetleyicisi geçerli olup olmadığını söyler.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon denetleyicisi geçerliyse TRUE; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yalnızca Geçerli işletim sistemi üzerinde Windows Animasyon API'sı desteklenmiyorsa ve kayıtlı olmadığı için animasyon yöneticisi nin oluşturulması başarısız olursa FALSE döndürür. Bu bayrağın ayarlanmasına neden olmak için COM kitaplıklarının başlatılmasından sonra en az bir kez GetUIAnimationManager'ı aramanız gerekir.

## <a name="canimationcontrollerm_bisvalid"></a><a name="m_bisvalid"></a>CAnimationController::m_bIsValid

Animasyon denetleyicinin geçerli olup olmadığını belirtir. Geçerli işletim sistemi Windows Animasyon API'sını desteklemiyorsa, bu üye FALSE olarak ayarlanır.

```
BOOL m_bIsValid;
```

## <a name="canimationcontrollerm_lstanimationgroups"></a><a name="m_lstanimationgroups"></a>CAnimationController::m_lstAnimationGroups

Bu animasyon denetleyicisine ait animasyon gruplarının listesi.

```
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;
```

## <a name="canimationcontrollerm_panimationmanager"></a><a name="m_panimationmanager"></a>CAnimationController::m_pAnimationManager

Animasyon Yöneticisi COM nesnesine bir işaretçi depolar.

```
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;
```

## <a name="canimationcontrollerm_panimationtimer"></a><a name="m_panimationtimer"></a>CAnimationController::m_pAnimationTimer

Animasyon Zamanlayıcı COM nesnesine bir işaretçi depolar.

```
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;
```

## <a name="canimationcontrollerm_prelatedwnd"></a><a name="m_prelatedwnd"></a>CAnimationController::m_pRelatedWnd

Animasyon yöneticisinin durumu değiştiğinde veya güncelleştirme sonrası olay oluştuğunda otomatik olarak yeniden çizilebilen ilgili bir CWnd nesnesine işaretçi. NULL olabilir.

```
CWnd* m_pRelatedWnd;
```

## <a name="canimationcontrollerm_ptransitionfactory"></a><a name="m_ptransitionfactory"></a>CAnimationController::m_pTransitionFactory

Geçiş Fabrikası COM nesnesine işaretçi depolar.

```
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;
```

## <a name="canimationcontrollerm_ptransitionlibrary"></a><a name="m_ptransitionlibrary"></a>CAnimationController::m_pTransitionLibrary

Geçiş Kitaplığı COM nesnesine işaretçi depolar.

```
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;
```

## <a name="canimationcontrolleronafterschedule"></a><a name="onafterschedule"></a>CAnimationController::OnafterSchedule

Belirtilen grup için bir animasyon zamanlandığında çerçeve tarafından çağrılır.

```
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parametreler

*pGroup*<br/>
Zamanlanan animasyon grubuna işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, anahtar kareleri belirtilen gruptan kaldırır ve belirtilen gruba ait animasyon değişkenlerinden geçişler. Animasyon zamanlaması üzerinde herhangi bir ek eylem almak için türetilmiş bir sınıfta geçersiz kılınabilir.

## <a name="canimationcontrolleronanimationintegervaluechanged"></a><a name="onanimationintegervaluechanged"></a>CAnimationController::OnAnimationIntegerValueChanged

Animasyon değişkeninin insa değeri değiştiğinde çerçeve tarafından çağrılır.

```
virtual void OnAnimationIntegerValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    INT32 newValue,
    INT32 prevValue);
```

### <a name="parameters"></a>Parametreler

*pGroup*<br/>
Değeri değişen bir animasyon nesnesini tutan bir animasyon grubuna işaretçi.

*Pobject*<br/>
Değeri değişen bir animasyon değişkeni içeren bir animasyon nesnesi için işaretçi.

*Değişken*<br/>
Animasyon değişkenine işaretçi.

*Newvalue*<br/>
Yeni değer belirtir.

*prevValue*<br/>
Önceki değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Belirli bir animasyon değişkeni veya animasyon nesnesi için çağrılan EnableIntegerValueChangedEvent ile animasyon değişken olayları etkinleştirmek bu yöntem denir. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir.

## <a name="canimationcontrolleronanimationmanagerstatuschanged"></a><a name="onanimationmanagerstatuschanged"></a>CAnimationController::OnAnimationManagerStatus Değiştirildi

Animasyon yöneticisinden DurumDeğiştirildi olayına yanıt olarak çerçeve tarafından çağrıldı.

```
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>Parametreler

*newDurum*<br/>
Yeni animasyon yöneticisi durumu.

*öncekiDurum*<br/>
Önceki animasyon yöneticisi durumu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, EnableAnimationManagerEvent ile animasyon yöneticisi olaylarını etkinleştiriyorsanız çağrılır. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir. Varsayılan uygulama, SetRelatedWnd ile ayarlanmışsa ilgili pencereyi güncelleştirir.

## <a name="canimationcontrolleronanimationtimerpostupdate"></a><a name="onanimationtimerpostupdate"></a>CAnimationController::OnAnimationTimerPostUpdate

Animasyon güncelleştirmesi tamamlandıktan sonra çerçeve tarafından çağrılır.

```
virtual void OnAnimationTimerPostUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, EnableAnimationTimerEventHandler kullanarak zamanlayıcı olay işleyicileri etkinleştirmek bu yöntem denir. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir.

## <a name="canimationcontrolleronanimationtimerpreupdate"></a><a name="onanimationtimerpreupdate"></a>CAnimationController::OnAnimationTimerPreUpdate

Animasyon güncelleştirmesi başlamadan önce çerçeve tarafından çağrılır.

```
virtual void OnAnimationTimerPreUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, EnableAnimationTimerEventHandler kullanarak zamanlayıcı olay işleyicileri etkinleştirmek bu yöntem denir. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir.

## <a name="canimationcontrolleronanimationtimerrenderingtooslow"></a><a name="onanimationtimerrenderingtooslow"></a>CAnimationController::OnAnimationTimerRenderingTooSlow

Animasyoniçin görüntüleme kare hızı minimum arzu edilen kare hızının altına düştüğünde çerçeve tarafından çağrılır.

```
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```

### <a name="parameters"></a>Parametreler

*Fps*<br/>
Saniyedeki karelerde geçerli kare hızı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, EnableAnimationTimerEventHandler kullanarak zamanlayıcı olay işleyicileri etkinleştirmek bu yöntem denir. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir. İstenilen minimum kare hızı IUIAnimationTimer::SetFrameRateThreshold numaralı çağrılarak belirtilir.

## <a name="canimationcontrolleronanimationvaluechanged"></a><a name="onanimationvaluechanged"></a>CAnimationController::OnAnimationValue Changed

Animasyon değişkeninin değeri değiştiğinde çerçeve tarafından çağrılır.

```
virtual void OnAnimationValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    DOUBLE newValue,
    DOUBLE prevValue);
```

### <a name="parameters"></a>Parametreler

*pGroup*<br/>
Değeri değişen bir animasyon nesnesini tutan bir animasyon grubuna işaretçi.

*Pobject*<br/>
Değeri değişen bir animasyon değişkeni içeren bir animasyon nesnesi için işaretçi.

*Değişken*<br/>
Animasyon değişkenine işaretçi.

*Newvalue*<br/>
Yeni değer belirtir.

*prevValue*<br/>
Önceki değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Belirli bir animasyon değişkeni veya animasyon nesnesi için çağrılan EnableValueChangedEvent ile animasyon değişken olayları etkinleştirmek bu yöntem denir. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir.

## <a name="canimationcontrolleronbeforeanimationstart"></a><a name="onbeforeanimationstart"></a>CAnimationController::OnbeforeAnimationStart

Animasyon zamanlanmadan hemen önce çerçeve tarafından çağrılır.

```
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parametreler

*pGroup*<br/>
Animasyonu başlamak üzere olan bir animasyon grubuna işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu çağrı ilgili CWnd'ye yönlendirilir ve animasyon belirtilen grup için animasyon başlamadan önce ek eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir.

## <a name="canimationcontrolleronhasprioritycancel"></a><a name="onhasprioritycancel"></a>CanimationController::OnhasPriorityCancel

Zamanlama çakışmalarını gidermek için çerçeve tarafından çağrıldı.

```
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parametreler

*pGroupScheduled*<br/>
Şu anda zamanlanmış film şeridinin sahibi olan grup.

*pGroupYeni*<br/>
pGroupScheduled'ın sahip olduğu zamanlanmış film şeridiyle çakışma zamanlama da bulunan yeni hikaye şeridinin sahibi olan grup.

*öncelikEtkisi*<br/>
pGroupScheduled'ın daha yüksek bir önceliği varsa pGroupNew üzerindeki olası etkisi.

### <a name="return-value"></a>Dönüş Değeri

pGroupNew'a ait storyboard'un önceliği varsa TRUE döndürmelidir. pGroupScheduled'a ait hikaye şeridinin önceliği varsa FALSE döndürmelidir.

### <a name="remarks"></a>Açıklamalar

CAnimationController::EnablePriorityComparisonHandler kullanarak öncelik karşılaştırma olaylarını etkinleştiriniz ve UI_ANIMATION_PHT_CANCEL belirtin bu yöntem edenir. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir. [Çakışma Yönetimi](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)hakkında daha fazla bilgi için Windows Animasyon API belgelerini okuyun.

## <a name="canimationcontrolleronhasprioritycompress"></a><a name="onhasprioritycompress"></a>CanimationController::OnHasPriorityCompress

Zamanlama çakışmalarını gidermek için çerçeve tarafından çağrıldı.

```
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parametreler

*pGroupScheduled*<br/>
Şu anda zamanlanmış film şeridinin sahibi olan grup.

*pGroupYeni*<br/>
pGroupScheduled'ın sahip olduğu zamanlanmış film şeridiyle çakışma zamanlama da bulunan yeni hikaye şeridinin sahibi olan grup.

*öncelikEtkisi*<br/>
pGroupScheduled'ın daha yüksek bir önceliği varsa pGroupNew üzerindeki olası etkisi.

### <a name="return-value"></a>Dönüş Değeri

pGroupNew'a ait storyboard'un önceliği varsa TRUE döndürmelidir. pGroupScheduled'a ait hikaye şeridinin önceliği varsa FALSE döndürmelidir.

### <a name="remarks"></a>Açıklamalar

CAnimationController::EnablePriorityComparisonHandler kullanarak öncelik karşılaştırma olaylarını etkinleştiriniz ve UI_ANIMATION_PHT_COMPRESS belirtin bu yöntem ekidir. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir. [Çakışma Yönetimi](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)hakkında daha fazla bilgi için Windows Animasyon API belgelerini okuyun.

## <a name="canimationcontrolleronhaspriorityconclude"></a><a name="onhaspriorityconclude"></a>CanimationController::OnHasPriorityconclude

Zamanlama çakışmalarını gidermek için çerçeve tarafından çağrıldı.

```
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parametreler

*pGroupScheduled*<br/>
Şu anda zamanlanmış film şeridinin sahibi olan grup.

*pGroupYeni*<br/>
pGroupScheduled'ın sahip olduğu zamanlanmış film şeridiyle çakışma zamanlama da bulunan yeni hikaye şeridinin sahibi olan grup.

*öncelikEtkisi*<br/>
pGroupScheduled'ın daha yüksek bir önceliği varsa pGroupNew üzerindeki olası etkisi.

### <a name="return-value"></a>Dönüş Değeri

pGroupNew'a ait storyboard'un önceliği varsa TRUE döndürmelidir. pGroupScheduled'a ait hikaye şeridinin önceliği varsa FALSE döndürmelidir.

### <a name="remarks"></a>Açıklamalar

CAnimationController::EnablePriorityComparisonHandler kullanarak öncelik karşılaştırma olaylarını etkinleştiriniz ve UI_ANIMATION_PHT_CONCLUDE belirtin bu yöntem edenir. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir. [Çakışma Yönetimi](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)hakkında daha fazla bilgi için Windows Animasyon API belgelerini okuyun.

## <a name="canimationcontrolleronhasprioritytrim"></a><a name="onhasprioritytrim"></a>CanimationController::OnhasPrioritytrim

Zamanlama çakışmalarını gidermek için çerçeve tarafından çağrıldı.

```
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parametreler

*pGroupScheduled*<br/>
Şu anda zamanlanmış film şeridinin sahibi olan grup.

*pGroupYeni*<br/>
pGroupScheduled'ın sahip olduğu zamanlanmış film şeridiyle çakışma zamanlama da bulunan yeni hikaye şeridinin sahibi olan grup.

*öncelikEtkisi*<br/>
pGroupScheduled'ın daha yüksek bir önceliği varsa pGroupNew üzerindeki olası etkisi.

### <a name="return-value"></a>Dönüş Değeri

pGroupNew'a ait storyboard'un önceliği varsa TRUE döndürmelidir. pGroupScheduled'a ait hikaye şeridinin önceliği varsa FALSE döndürmelidir.

### <a name="remarks"></a>Açıklamalar

CAnimationController::EnablePriorityComparisonHandler kullanarak öncelik karşılaştırma olaylarını etkinleştiriniz ve UI_ANIMATION_PHT_TRIM belirtin bu yöntem edenir. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir. [Çakışma Yönetimi](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)hakkında daha fazla bilgi için Windows Animasyon API belgelerini okuyun.

## <a name="canimationcontrolleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a>CAnimationController::OnStoryboardStatusChanged

Film şeridi durumu değiştiğinde çerçeve tarafından çağrılır.

```
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,
    UI_ANIMATION_STORYBOARD_STATUS newStatus,
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>Parametreler

*pGroup*<br/>
Durumu değişen film şeridinin sahibi olan animasyon grubuna işaretçi.

*newDurum*<br/>
Yeni durumu belirtir.

*öncekiDurum*<br/>
Önceki durumu belirtir.

### <a name="remarks"></a>Açıklamalar

CAnimationController::EnableStoryboardEventHandler kullanarak film şeridi olaylarını etkinleştiriyorsanız bu yöntem edenir. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir.

## <a name="canimationcontrolleronstoryboardupdated"></a><a name="onstoryboardupdated"></a>CAnimationController::OnStoryboardGüncel

Film şeridi güncelleştirildiğinde çerçeve tarafından çağrılır.

```
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parametreler

*pGroup*<br/>
Film şeridinin sahibi olan bir gruba işaretçi.

### <a name="remarks"></a>Açıklamalar

CAnimationController::EnableStoryboardEventHandler kullanarak film şeridi olaylarını etkinleştiriyorsanız bu yöntem edenir. Uygulamaya özgü eylemler icra etmek için türetilmiş bir sınıfta geçersiz kılınabilir.

## <a name="canimationcontrollerremoveallanimationgroups"></a><a name="removeallanimationgroups"></a>CAnimationController::RemoveAllAnimationGroups

Tüm animasyon gruplarını animasyon denetleyicisinden kaldırır.

```
void RemoveAllAnimationGroups();
```

### <a name="remarks"></a>Açıklamalar

Tüm gruplar silinir, işaretçileri, uygulama düzeyinde depolanırsa geçersiz kılınmalıdır. CAnimationGroup::m_bAutodestroyAnimationObjects bir grubun silinmesi için DOĞRU ise, o gruba ait tüm animasyon nesneleri silinir; aksi takdirde ana animasyon denetleyicisine yapılan atıflar NULL olarak ayarlanır ve başka bir denetleyiciye eklenebilir.

## <a name="canimationcontrollerremoveanimationgroup"></a><a name="removeanimationgroup"></a>CAnimationController::RemoveAnimationGroup

Animasyon denetleyicisinden belirtilen kimliği olan bir animasyon grubunu kaldırır.

```
void RemoveAnimationGroup(UINT32 nGroupID);
```

### <a name="parameters"></a>Parametreler

*nGroupID*<br/>
Animasyon grubu kimliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir animasyon grubunu iç gruplar listesinden kaldırır ve siler, bu nedenle bu animasyon grubuna bir işaretçi depolarsanız geçersiz kılınması gerekir. CAnimationGroup::m_bAutodestroyAnimationObjects DOĞRUise, bu gruba ait tüm animasyon nesneleri silinir; aksi takdirde ana animasyon denetleyicisine yapılan atıflar NULL olarak ayarlanır ve başka bir denetleyiciye eklenebilir.

## <a name="canimationcontrollerremoveanimationobject"></a><a name="removeanimationobject"></a>CAnimationController::RemoveAnimationObject

Animasyon nesnesi animasyon denetleyicisinden kaldırın.

```
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,
    BOOL bNoDelete = FALSE);
```

### <a name="parameters"></a>Parametreler

*Pobject*<br/>
Animasyon nesnesine işaretçi.

*bNoDelete*<br/>
Bu parametre TRUE ise nesne kaldırıldıktan sonra silinmez.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesi animasyon denetleyicisi ve animasyon grubundan bir animasyon nesnesi kaldırır. Belirli bir nesne artık animasyonlu değilse veya nesneyi başka bir animasyon denetleyicisine taşımanız gerekiyorsa bu işlevi arayın. Son durumda bNoDelete DOĞRU olmalıdır.

## <a name="canimationcontrollerremovetransitions"></a><a name="removetransitions"></a>CAnimationController::Geçişleri Kaldırma

Belirtilen gruba ait animasyon nesnelerinden geçişleri kaldırır.

```
void RemoveTransitions(UINT32 nGroupID);
```

### <a name="parameters"></a>Parametreler

*nGroupID*<br/>
Grup Kimliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Grup, animasyon nesnelerinin üzerine döngüler ve her animasyon nesnesi için ClearTransitions(FALSE) çağırır. Bu yöntem, animasyon zamanlandıktan sonra çerçeve tarafından çağrılır.

## <a name="canimationcontrollerschedulegroup"></a><a name="schedulegroup"></a>CAnimationController::Program Grubu

Animasyon planlar.

```
BOOL ScheduleGroup(
    UINT32 nGroupID,
    UI_ANIMATION_SECONDS time = 0.0);
```

### <a name="parameters"></a>Parametreler

*nGroupID*<br/>
Zamanlamaiçin animasyon Grup Kimliğini belirtir.

*time*<br/>
Zamançizelgesi için zaman belirtir.

### <a name="return-value"></a>Dönüş Değeri

Animasyon başarıyla zamanlanmışsa TRUE. Storyboard oluşturulmamadıysa veya başka bir hata oluşuyorsa FALSE.

### <a name="remarks"></a>Açıklamalar

BScheduleNow parametresi false prior ScheduleGroup olarak ayarlanmış Olan AnimateGroup'u aramanız gerekir. IUIAnimationTimer'dan elde edilen istenilen animasyon süresini belirtebilirsiniz::GetTime. Zaman parametresi 0,0 ise, animasyon geçerli saat için zamanlanır.

## <a name="canimationcontrollersetrelatedwnd"></a><a name="setrelatedwnd"></a>CAnimationController::SetRelatedWnd

Animasyon denetleyicisi ve bir pencere arasında bir ilişki kurar.

```
void SetRelatedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Ayarlamak için pencere nesnesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İlgili bir CWnd nesnesi ayarlanırsa, animasyon yöneticisinin durumu değiştiğinde veya zamanlayıcı sonrası güncelleştirme olayı oluştuğunda animasyon denetleyicisi otomatik olarak güncelleyebilir (WM_PAINT ileti gönder).

## <a name="canimationcontrollerupdateanimationmanager"></a><a name="updateanimationmanager"></a>CAnimationController::UpdateAnimationManager

Animasyon yöneticisini tüm animasyon değişkenlerinin değerlerini güncelleştirmeye yönlendirir.

```
virtual void UpdateAnimationManager();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağrılması animasyon yöneticisini geçerli saate doğru ilerler, gerektiğinde film panolarının durumlarını değiştirir ve animasyon değişkenlerini uygun enterpolasyonlu değerlere günceller. Dahili olarak bu yöntem iUIAnimationTimer çağırır::GetTime(timeNow) ve IUIAnimationManager::Update(timeNow). Bu davranışı özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
