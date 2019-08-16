---
title: CAnimationController sınıfı
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
ms.openlocfilehash: 9039d44d9ef36a47c11b3ecaddf232ad427727c4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507646"
---
# <a name="canimationcontroller-class"></a>CAnimationController sınıfı

Animasyonların oluşturulması ve yönetilmesi için merkezi bir arabirim sağlayan animasyon denetleyicisini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationController : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationController:: CAnimationController](#canimationcontroller)|Bir animasyon denetleyicisi oluşturur.|
|[CAnimationController:: ~ CAnimationController](#_dtorcanimationcontroller)|Yok edicisi. Animasyon denetleyici nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationController:: AddAnimationObject](#addanimationobject)|Animasyon denetleyicisine ait olan bir gruba animasyon nesnesi ekler.|
|[CAnimationController:: AddKeyframeToGroup](#addkeyframetogroup)|Gruba bir ana kare ekler.|
|[CAnimationController:: AnimateGroup](#animategroup)|Animasyonu çalıştırmak için bir grup hazırlar ve isteğe bağlı olarak zamanlamayı zamanlar.|
|[CAnimationController:: CleanUpGroup](#cleanupgroup)|Fazla Yüklendi. Animasyon zamanlandığı sırada grubu temizlemek için Framework tarafından çağırılır.|
|[CAnimationController:: CreateKeyframe](#createkeyframe)|Fazla Yüklendi. Geçişe bağlı olan bir ana kare oluşturur ve belirtilen gruba ekler.|
|[CAnimationController:: EnableAnimationManagerEvent](#enableanimationmanagerevent)|Animasyon yöneticisinin durumu değiştiğinde çağırmak için bir işleyici ayarlar veya serbest bırakır.|
|[CAnimationController:: EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|Zamanlama güncelleştirmeleri için bir işleyici, zamanlama olayları ve işleyicisi için ayarlar veya yayınlar.|
|[CAnimationController:: EnablePriorityComparisonHandler](#enableprioritycomparisonhandler)|Zamanlanan bir görsel taslağın iptal edilip edilmeyeceğini, sonlandırılacağını, kırpıldığını veya sıkıştıramayacağını belirleme çağrısı yapmak için öncelik karşılaştırma işleyicisini ayarlar veya serbest bırakır.|
|[CAnimationController:: EnableStoryboardEventHandler](#enablestoryboardeventhandler)|Görsel taslak durumu ve güncelleştirme olayları için bir işleyici ayarlar veya yayınlar.|
|[CAnimationController:: Findanimasyongroup](#findanimationgroup)|Fazla Yüklendi. Görsel taslağa göre bir animasyon grubunu bulur.|
|[CAnimationController:: FindAnimationObject](#findanimationobject)|Belirtilen bir animasyon değişkenini içeren animasyon nesnesini bulur.|
|[CAnimationController:: GetKeyframeStoryboardStart](#getkeyframestoryboardstart)|Görsel taslak başlangıcını tanımlayan bir ana kare döndürür.|
|[CAnimationController:: GetUIAnimationManager](#getuianimationmanager)|Encapsulated IUIAnimationManager nesnesine erişim sağlar.|
|[CAnimationController:: Getuıanimationtimer](#getuianimationtimer)|Encapsulated IUIAnimationTimer nesnesine erişim sağlar.|
|[CAnimationController:: GetUITransitionFactory](#getuitransitionfactory)|Geçiş kitaplığı oluşturma işlemi başarısız olduysa, ıuıanimationgeçişli Tionfactory arabirimine veya NULL öğesine yönelik bir işaretçi.|
|[CAnimationController:: GetUITransitionLibrary](#getuitransitionlibrary)|Encapsulated ıuıanimationgeçiş Tionlibrary nesnesine erişim sağlar.|
|[CAnimationController:: ısanimationınprogress](#isanimationinprogress)|En az bir grubun animasyon çalıp oynamadığını söyler.|
|[CAnimationController:: IsValid](#isvalid)|Animasyon denetleyicisinin geçerli olup olmadığını söyler.|
|[CAnimationController:: OnAnimationIntegerValueChanged](#onanimationintegervaluechanged)|Animasyon değişkeninin tamsayı değeri değiştiğinde Framework tarafından çağırılır.|
|[CAnimationController:: OnAnimationManagerStatusChanged](#onanimationmanagerstatuschanged)|Animasyon yöneticisinden StatusChanged olayına yanıt olarak Framework tarafından çağırılır.|
|[CAnimationController:: OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|Bir animasyon güncelleştirmesi tamamlandıktan sonra Framework tarafından çağırılır.|
|[CAnimationController:: OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|Bir animasyon güncelleştirmesi başlamadan önce Framework tarafından çağırılır.|
|[CAnimationController:: Onanimationtimerrenderingtoolow](#onanimationtimerrenderingtooslow)|Bir animasyonun işleme çerçevesi oranı, istenen en düşük kare oranının altına düştüğünde Framework tarafından çağırılır.|
|[CAnimationController:: Onanimasyonvaluechanged](#onanimationvaluechanged)|Animasyon değişkeninin değeri değiştiğinde Framework tarafından çağırılır.|
|[CAnimationController:: OnBeforeAnimationStart](#onbeforeanimationstart)|Animasyon zamanlanmadan önce Framework tarafından çağırılır.|
|[CAnimationController:: OnHasPriorityCancel](#onhasprioritycancel)|Zamanlama çakışmalarını çözmek için Framework tarafından çağırılır.|
|[CAnimationController:: OnHasPriorityCompress](#onhasprioritycompress)|Zamanlama çakışmalarını çözmek için Framework tarafından çağırılır.|
|[CAnimationController:: Onhasprioritysonuçde](#onhaspriorityconclude)|Zamanlama çakışmalarını çözmek için Framework tarafından çağırılır.|
|[CAnimationController:: OnHasPriorityTrim](#onhasprioritytrim)|Zamanlama çakışmalarını çözmek için Framework tarafından çağırılır.|
|[CAnimationController:: OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Görsel taslak durumu değiştiğinde Framework tarafından çağırılır.|
|[CAnimationController:: OnStoryboardUpdated](#onstoryboardupdated)|Görsel taslak güncelleştirildiği zaman Framework tarafından çağırılır.|
|[CAnimationController:: RemoveAllAnimationGroups](#removeallanimationgroups)|Tüm animasyon gruplarını animasyon denetleyicisinden kaldırır.|
|[CAnimationController:: RemoveAnimationGroup](#removeanimationgroup)|Belirtilen KIMLIĞE sahip bir animasyon grubunu animasyon denetleyicisinden kaldırır.|
|[CAnimationController:: RemoveAnimationObject](#removeanimationobject)|Animasyon denetleyicisinden bir animasyon nesnesi kaldırın.|
|[CAnimationController:: Removetransıtions](#removetransitions)|Belirtilen gruba ait olan animasyon nesnelerinden geçişleri kaldırır.|
|[CAnimationController:: ScheduleGroup](#schedulegroup)|Bir animasyon zamanlar.|
|[CAnimationController:: SetRelatedWnd](#setrelatedwnd)|Animasyon denetleyicisi ve pencere arasında bir ilişki oluşturur.|
|[CAnimationController:: UpdateAnimationManager](#updateanimationmanager)|Animasyon yöneticisini tüm animasyon değişkenlerinin değerlerini güncelleştirecek şekilde yönlendirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationController:: CleanUpGroup](#cleanupgroup)|Fazla Yüklendi. Grubu Temizleme Yardımcısı.|
|[CAnimationController:: OnAfterSchedule](#onafterschedule)|Belirtilen gruba yönelik bir animasyon henüz zamanlandığında Framework tarafından çağırılır.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationController:: gkeyframeStoryboardStart](#g_keyframestoryboardstart)|Görsel taslak başlangıcını temsil eden bir ana kare.|
|[CAnimationController:: m_bIsValid](#m_bisvalid)|Bir animasyon denetleyicisinin geçerli olup olmadığını belirtir. Geçerli işletim sistemi Windows Animation API 'YI desteklemiyorsa bu üye FALSE olarak ayarlanır.|
|[CAnimationController:: m_lstAnimationGroups](#m_lstanimationgroups)|Bu animasyon denetleyicisine ait olan animasyon gruplarının listesi.|
|[CAnimationController:: m_pAnimationManager](#m_panimationmanager)|Animation Manager COM nesnesine bir işaretçi depolar.|
|[CAnimationController:: m_pAnimationTimer](#m_panimationtimer)|Animasyon Zamanlayıcı COM nesnesine bir işaretçi depolar.|
|[CAnimationController:: m_pRelatedWnd](#m_prelatedwnd)|Animasyon Yöneticisi 'nin durumu değiştiğinde otomatik olarak yeniden çizilebilir olabilecek ilgili bir CWnd nesnesine yönelik işaretçi veya güncelleştirme sonrası olay meydana geldi. NULL olabilir.|
|[CAnimationController:: m_pTransitionFactory](#m_ptransitionfactory)|Geçiş fabrikası COM nesnesine bir işaretçi depolar.|
|[CAnimationController:: m_pTransitionLibrary](#m_ptransitionlibrary)|Geçiş kitaplığı COM nesnesine bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

CAnimationController sınıfı, animasyonları yöneten temel sınıftır. Bir uygulamada bir veya daha fazla animasyon denetleyicisi örneği oluşturabilir ve isteğe bağlı olarak, CAnimationController:: SetRelatedWnd kullanarak bir animasyon denetleyicisi örneğini CWnd nesnesine bağlayabilirsiniz. Bu bağlantı, Animation Manager durumu değiştiğinde veya animasyon süreölçeri güncelleştirildiği zaman ilgili pencereye otomatik olarak WM_PAINT iletileri göndermek için gereklidir. Bu ilişkiyi etkinleştirmezseniz, el ile bir animasyon görüntüleyen pencereyi yeniden çizmelidir. Bu amaçla, CAnimationController ' dan bir sınıf türetebilir ve OnAnimationManagerStatusChanged ve/veya OnAnimationTimerPostUpdate ' i geçersiz kılabilir ve gerektiğinde bir veya daha fazla pencere geçersiz kılabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationController`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

##  <a name="_dtorcanimationcontroller"></a>CAnimationController:: ~ CAnimationController

Yok edicisi. Animasyon denetleyici nesnesi yok edildiğinde çağırılır.

```
virtual ~CAnimationController(void);
```

##  <a name="addanimationobject"></a>CAnimationController:: AddAnimationObject

Animasyon denetleyicisine ait olan bir gruba animasyon nesnesi ekler.

```
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```

### <a name="parameters"></a>Parametreler

*Nesnesini*<br/>
Animasyon nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa pObject 'in eklendiği mevcut veya yeni animasyon grubuna yönelik bir işaretçi; PObject zaten başka bir animasyon denetleyicisine ait olan bir gruba eklendiyse NULL.

### <a name="remarks"></a>Açıklamalar

Animasyon denetleyicisine bir animasyon nesnesi eklemek için bu yöntemi çağırın. Bir nesne, nesnenin GroupID öğesine göre gruba eklenir (bkz. CAnimationBaseObject:: SetID). Belirtilen GroupID ile ilk nesne ekleniyorsa animasyon denetleyicisi yeni bir grup oluşturur. Bir animasyon nesnesi yalnızca bir animasyon denetleyicisine eklenebilir. Başka bir denetleyiciye bir nesne eklemeniz gerekiyorsa, önce RemoveAnimationObject ' i çağırın. Bir gruba zaten eklenmiş olan bir nesne için SetID 'yi yeni GroupID ile çağırırsanız, nesne eski gruptan kaldırılır ve belirtilen KIMLIĞE sahip başka bir gruba eklenir.

##  <a name="addkeyframetogroup"></a>CAnimationController:: AddKeyframeToGroup

Gruba bir ana kare ekler.

```
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe);
```

### <a name="parameters"></a>Parametreler

*Ngroupıd*<br/>
Grup KIMLIĞINI belirtir.

*Pana kare*<br/>
Bir ana kare işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Genellikle bu yöntemi çağırmanız gerekmez; bunun yerine CAnimationController:: CreateKeyframe kullanın ve oluşturulan ana kareyi bir gruba otomatik olarak ekler.

##  <a name="animategroup"></a>CAnimationController:: AnimateGroup

Animasyonu çalıştırmak için bir grup hazırlar ve isteğe bağlı olarak zamanlamayı zamanlar.

```
BOOL AnimateGroup(
    UINT32 nGroupID,
    BOOL bScheduleNow = TRUE);
```

### <a name="parameters"></a>Parametreler

*Ngroupıd*<br/>
GroupID belirtir.

*Şimdi bschedule*<br/>
Animasyonun hemen çalıştırılıp çalıştırılmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Animasyon başarıyla zamanlanırsa ve çalıştırıldığında doğru.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gerçek işi film şeridi oluşturuyor, animasyon değişkenleri ekleme, geçişleri uygulama ve ana kareleri ayarlama. BScheduleNow değerini FALSE olarak ayarlarsanız zamanlamayı erteleyebilir. Bu durumda, belirtilen grup animasyon için ayarlanmış bir film şeridini tutacaktır. Bu noktada, film şeridi ve animasyon değişkenlerine yönelik olayları ayarlayabilirsiniz. Gerçekten bir animasyon çalıştırmak istediğinizde, CAnimationController:: ScheduleGroup öğesini çağırın.

##  <a name="canimationcontroller"></a>CAnimationController:: CAnimationController

Bir animasyon denetleyicisi oluşturur.

```
CAnimationController(void);
```

##  <a name="cleanupgroup"></a>CAnimationController:: CleanUpGroup

Animasyon zamanlandığı sırada grubu temizlemek için Framework tarafından çağırılır.

```
void CleanUpGroup(UINT32 nGroupID);
void CleanUpGroup(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parametreler

*Ngroupıd*<br/>
GroupID belirtir.

*pGroup*<br/>
Temizleme için animasyon grubuna yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir animasyon zamanlandıktan sonra ilgili olmadıklarından, belirtilen gruptaki tüm geçişleri ve ana kareleri kaldırır.

##  <a name="createkeyframe"></a>CAnimationController:: CreateKeyframe

Geçişe bağlı olan bir ana kare oluşturur ve belirtilen gruba ekler.

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

*Ngroupıd*<br/>
Ana karenin oluşturulduğu grup KIMLIĞINI belirtir.

*pTransition*<br/>
Geçiş işaretçisi. Ana kare, Bu geçişten sonra görsel taslağa eklenecektir.

*Pana kare*<br/>
Bu ana kare için ana anahtar karesine yönelik bir işaretçi.

*konumu*<br/>
PKeyframe tarafından belirtilen taban ana kareden saniye cinsinden konum.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa yeni oluşturulan ana kareye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Döndürülen işaretçiyi ve diğer ana kareleri yeni oluşturulan ana karede saklayabilir (ikinci aşırı yüklemeye bakın). Ana kareler üzerinde geçişler başlatmak mümkündür-bkz. CBaseTransition:: Setana kareleri. Bu şekilde oluşturulan ana kareleri, animasyon grupları tarafından otomatik olarak silindiği için silmeniz gerekmez. Diğer ana kareleri ve geçişleri temel alan ana kareler oluştururken dikkatli olun ve döngüsel başvurularınızı önleyin.

##  <a name="enableanimationmanagerevent"></a>CAnimationController:: EnableAnimationManagerEvent

Animasyon yöneticisinin durumu değiştiğinde çağırmak için bir işleyici ayarlar veya serbest bırakır.

```
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
Bir işleyicinin ayarlanacağını veya serbest bırakılıp başlatılmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşleyici başarıyla ayarlandıysa veya yayımlandıysa TRUE.

### <a name="remarks"></a>Açıklamalar

Bir işleyici ayarlandığında (etkin), animasyon yöneticisinin durumu değiştiğinde OnAnimationManagerStatusChanged Windows animasyonu çağırır.

##  <a name="enableanimationtimereventhandler"></a>CAnimationController:: EnableAnimationTimerEventHandler

Zamanlama güncelleştirmeleri için bir işleyici, zamanlama olayları ve işleyicisi için ayarlar veya yayınlar.

```
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
İşleyicilerin ayarlanacağını veya yayınlanıp yayınlanmayacağını belirtir.

*ıdde davranışı*<br/>
Zamanlayıcı güncelleştirme işleyicisi için boşta davranışını belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşleyiciler başarıyla ayarlandıysa veya yayımlanmışsa doğru; Bu yöntem, önce işleyicileri serbest bırakmadan ikinci bir kez çağrılırsa veya başka bir hata oluşursa FALSE.

### <a name="remarks"></a>Açıklamalar

İşleyiciler ayarlandığında (etkin) Windows animasyon API 'SI OnAnimationTimerPreUpdate, OnAnimationTimerPostUpdate, Onrenderingtoolow yöntemlerini çağırır. Windows animasyon API 'SI güncelleştirme görsel taslaklara izin vermek için animasyon zamanlayıcılarını etkinleştirmeniz gerekir. Aksi takdirde, tüm animasyon değişkenlerinin değerlerini güncelleştirmek üzere animasyon yöneticisini yönlendirmek için CAnimationController:: UpdateAnimationManager ' i çağırmanız gerekir.

##  <a name="enableprioritycomparisonhandler"></a>CAnimationController:: EnablePriorityComparisonHandler

Zamanlanan bir görsel taslağın iptal edilip edilmeyeceğini, sonlandırılacağını, kırpıldığını veya sıkıştıramayacağını belirleme çağrısı yapmak için öncelik karşılaştırma işleyicisini ayarlar veya serbest bırakır.

```
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```

### <a name="parameters"></a>Parametreler

*dwHandlerType*<br/>
Ayarlanacak veya yayınlanacak işleyicileri belirten UI_ANIMATION_PHT_ bayraklarının (bkz. notlar) birleşimi.

### <a name="return-value"></a>Dönüş Değeri

İşleyici başarıyla ayarlandıysa veya yayımlandıysa TRUE.

### <a name="remarks"></a>Açıklamalar

Bir işleyici ayarlandığında (etkin), Windows animasyonu dwHandlerType öğesine bağlı olarak aşağıdaki sanal yöntemleri çağırır: OnHasPriorityCancel, Onhasprioritysonuçde, OnHasPriorityTrim, OnHasPriorityCompress. dwHandler aşağıdaki bayrakların bir birleşimi olabilir: UI_ANIMATION_PHT_NONE-tüm işleyicileri serbest bırak UI_ANIMATION_PHT_CANCEL-set Cancel karşılaştırma işleyicisi UI_ANIMATION_PHT_CONCLUDE-sonuçlandırma karşılaştırma işleyicisini ayarla UI_ANIMATION_PHT_COMPRESS-bir sıkıştırma karşılaştırma işleyicisi UI_ANIMATION_PHT_TRIM-set Kırpma karşılaştırma işleyicisi UI_ANIMATION_PHT_CANCEL_REMOVE-kaldırma karşılaştırma işleyicisi UI_ANIMATION_PHT_CONCLUDE_REMOVE-kaldırma sonuçlandırma işleyicisi UI_ANIMATION_PHT_COMPRESS_REMOVE-kaldır karşılaştırma işleyicisi UI_ANIMATION_PHT _KıRıLAMıYOR _KALDıR-kırpma karşılaştırma işleyicisini kaldır

##  <a name="enablestoryboardeventhandler"></a>CAnimationController:: EnableStoryboardEventHandler

Görsel taslak durumu ve güncelleştirme olayları için bir işleyici ayarlar veya yayınlar.

```
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*Ngroupıd*<br/>
Grup KIMLIĞINI belirtir.

*bEnable*<br/>
Bir işleyicinin ayarlanacağını veya serbest bırakılıp başlatılmayacağını belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşleyici başarıyla ayarlandıysa veya yayımlandıysa doğru; Belirtilen animasyon grubu şimdi bulunursa veya belirtilen grup için animasyon başlatılmamışsa ve iç film şeridi NULL ise FALSE.

### <a name="remarks"></a>Açıklamalar

Bir işleyici ayarlandığında (etkin) Windows animasyon API 'SI OnStoryboardStatusChanges ve OnStoryboardUpdated sanal yöntemlerini çağırır. Bir işleyici, belirtilen animasyon grubu için CAnimationController:: Canıuıafter, kapsüllenmiş IUIAnimationStoryboard nesnesi oluşturduğundan ayarlanmalıdır.

##  <a name="findanimationgroup"></a>CAnimationController:: Findanimasyongroup

Grup KIMLIĞINE göre bir animasyon grubunu bulur.

```
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parametreler

*Ngroupıd*<br/>
GroupID belirtir.

*pStoryboard*<br/>
Görsel taslağa yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen KIMLIĞE sahip Grup bulunmazsa animasyon grubuna yönelik bir işaretçi veya NULL.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanında bir animasyon grubu bulmak için bu yöntemi kullanın. Belirli bir GroupID 'ye sahip ilk animasyon nesnesi animasyon denetleyiciye eklenirken bir grup oluşturulur ve animasyon gruplarının iç listesine eklenir.

##  <a name="findanimationobject"></a>CAnimationController:: FindAnimationObject

Belirtilen bir animasyon değişkenini içeren animasyon nesnesini bulur.

```
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,
    CAnimationBaseObject** ppObject,
    CAnimationGroup** ppGroup);
```

### <a name="parameters"></a>Parametreler

*pVariable*<br/>
Animasyon değişkenine yönelik bir işaretçi.

*ppObject*<br/>
Çıktıların. Animasyon nesnesine veya NULL işaretçisine sahip bir işaretçi içerir.

*ppGroup*<br/>
Çıktıların. Animasyon nesnesini veya NULL değerini tutan bir animasyon grubuna yönelik bir işaretçi içerir.

### <a name="return-value"></a>Dönüş Değeri

Nesne bulunursa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Gelen animasyon değişkeninden bir animasyon nesnesi bulması gerektiğinde olay işleyicilerinden çağırılır.

##  <a name="g_keyframestoryboardstart"></a>CAnimationController:: gkeyframeStoryboardStart

Görsel taslak başlangıcını temsil eden bir ana kare.

```
static CBaseKeyFrame gkeyframeStoryboardStart;
```

##  <a name="getkeyframestoryboardstart"></a>CAnimationController:: GetKeyframeStoryboardStart

Görsel taslak başlangıcını tanımlayan bir ana kare döndürür.

```
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```

### <a name="return-value"></a>Dönüş Değeri

Görsel taslak başlangıcını tanımlayan temel ana kare işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu ana kareyi, bir film şeridinin başladığı anda diğer tüm ana kareleri veya geçişleri temel alacak şekilde elde edin.

##  <a name="getuianimationmanager"></a>CAnimationController:: GetUIAnimationManager

Encapsulated IUIAnimationManager nesnesine erişim sağlar.

```
IUIAnimationManager* GetUIAnimationManager();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon Yöneticisi oluşturma başarısız olursa IUIAnimationManager arabirimine veya NULL 'a yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli işletim sistemi Windows Animation API 'yi desteklemiyorsa, bu yöntem NULL döndürür ve CAnimationController:: IsValid üzerinde yapılan tüm çağrılar FALSE döndürün. Bir animasyon denetleyicisi tarafından sarmalanmamış arabirim yöntemlerini çağırmak için IUIAnimationManager 'a erişmeniz gerekebilir.

##  <a name="getuianimationtimer"></a>CAnimationController:: Getuıanimationtimer

Encapsulated IUIAnimationTimer nesnesine erişim sağlar.

```
IUIAnimationTimer* GetUIAnimationTimer();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon Zamanlayıcı oluşturma başarısız olduysa, IUIAnimationTimer arabirimine veya NULL 'a yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli işletim sistemi Windows Animation API 'yi desteklemiyorsa, bu yöntem NULL döndürür ve CAnimationController:: IsValid üzerinde yapılan tüm çağrılar FALSE döndürün.

##  <a name="getuitransitionfactory"></a>CAnimationController:: GetUITransitionFactory

Geçiş kitaplığı oluşturma işlemi başarısız olduysa, ıuıanimationgeçişli Tionfactory arabirimine veya NULL öğesine yönelik bir işaretçi.

```
IUIAnimationTransitionFactory* GetUITransitionFactory();
```

### <a name="return-value"></a>Dönüş Değeri

Geçiş fabrikası oluşturma işlemi başarısız olursa ıuıanimationgeçişli Tionfactory veya NULL işaretçisi.

### <a name="remarks"></a>Açıklamalar

Geçerli işletim sistemi Windows Animation API 'yi desteklemiyorsa, bu yöntem NULL döndürür ve CAnimationController:: IsValid üzerinde yapılan tüm çağrılar FALSE döndürün.

##  <a name="getuitransitionlibrary"></a>CAnimationController:: GetUITransitionLibrary

Encapsulated ıuıanimationgeçiş Tionlibrary nesnesine erişim sağlar.

```
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```

### <a name="return-value"></a>Dönüş Değeri

Geçiş kitaplığı oluşturma işlemi başarısız olduysa, ıuıanimationgeçişli Tionlibrary arabirimine veya NULL öğesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli işletim sistemi Windows Animation API 'yi desteklemiyorsa, bu yöntem NULL döndürür ve CAnimationController:: IsValid üzerinde yapılan tüm çağrılar FALSE döndürün.

##  <a name="isanimationinprogress"></a>CAnimationController:: ısanimationınprogress

En az bir grubun animasyon çalıp oynamadığını söyler.

```
virtual BOOL IsAnimationInProgress();
```

### <a name="return-value"></a>Dönüş Değeri

Bu animasyon denetleyicisi için devam eden bir animasyon varsa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Animasyon yöneticisinin durumunu denetler ve durum UI_ANIMATION_MANAGER_BUSY ise doğru değerini döndürür.

##  <a name="isvalid"></a>CAnimationController:: IsValid

Animasyon denetleyicisinin geçerli olup olmadığını söyler.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon denetleyicisi geçerliyse doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yalnızca Windows animasyon API 'SI geçerli IŞLETIM sisteminde desteklenmiyorsa ve animasyon Yöneticisi kaydettirilmediği için başarısız olduysa FALSE döndürür. Bu bayrağın ayarlanmasına neden olması için COM kitaplıklarını başlattıktan sonra GetUIAnimationManager 'ı en az bir kez çağırmanız gerekir.

##  <a name="m_bisvalid"></a>CAnimationController:: m_bIsValid

Bir animasyon denetleyicisinin geçerli olup olmadığını belirtir. Geçerli işletim sistemi Windows Animation API 'YI desteklemiyorsa bu üye FALSE olarak ayarlanır.

```
BOOL m_bIsValid;
```

##  <a name="m_lstanimationgroups"></a>CAnimationController:: m_lstAnimationGroups

Bu animasyon denetleyicisine ait olan animasyon gruplarının listesi.

```
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;
```

##  <a name="m_panimationmanager"></a>CAnimationController:: m_pAnimationManager

Animation Manager COM nesnesine bir işaretçi depolar.

```
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;
```

##  <a name="m_panimationtimer"></a>CAnimationController:: m_pAnimationTimer

Animasyon Zamanlayıcı COM nesnesine bir işaretçi depolar.

```
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;
```

##  <a name="m_prelatedwnd"></a>CAnimationController:: m_pRelatedWnd

Animasyon Yöneticisi 'nin durumu değiştiğinde otomatik olarak yeniden çizilebilir olabilecek ilgili bir CWnd nesnesine yönelik işaretçi veya güncelleştirme sonrası olay meydana geldi. NULL olabilir.

```
CWnd* m_pRelatedWnd;
```

##  <a name="m_ptransitionfactory"></a>CAnimationController:: m_pTransitionFactory

Geçiş fabrikası COM nesnesine bir işaretçi depolar.

```
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;
```

##  <a name="m_ptransitionlibrary"></a>CAnimationController:: m_pTransitionLibrary

Geçiş kitaplığı COM nesnesine bir işaretçi depolar.

```
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;
```

##  <a name="onafterschedule"></a>CAnimationController:: OnAfterSchedule

Belirtilen gruba yönelik bir animasyon henüz zamanlandığında Framework tarafından çağırılır.

```
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parametreler

*pGroup*<br/>
Zamanlanan bir animasyon grubuna yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama belirtilen gruptaki ana kareleri kaldırır ve belirtilen gruba ait olan animasyon değişkenlerinden geçiş yapar. Animasyon zamanlamasında ek eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir.

##  <a name="onanimationintegervaluechanged"></a>CAnimationController:: OnAnimationIntegerValueChanged

Animasyon değişkeninin tamsayı değeri değiştiğinde Framework tarafından çağırılır.

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
Değeri değişmiş bir animasyon nesnesini tutan animasyon grubuna yönelik bir işaretçi.

*Nesnesini*<br/>
Değeri değişmiş bir animasyon değişkeni içeren animasyon nesnesine yönelik bir işaretçi.

*değişken*<br/>
Animasyon değişkenine yönelik bir işaretçi.

*Değer*<br/>
Yeni bir değer belirtir.

*prevValue*<br/>
Önceki değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirli bir animasyon değişkeni veya animasyon nesnesi için EnableIntegerValueChangedEvent çağrılan animasyon değişken olaylarını etkinleştirirseniz çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir.

##  <a name="onanimationmanagerstatuschanged"></a>CAnimationController:: OnAnimationManagerStatusChanged

Animasyon yöneticisinden StatusChanged olayına yanıt olarak Framework tarafından çağırılır.

```
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>Parametreler

*newStatus*<br/>
Yeni animasyon Yöneticisi durumu.

*previousStatus*<br/>
Önceki animasyon Yöneticisi durumu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, EnableAnimationManagerEvent ile Animation Manager olaylarını etkinleştirirseniz çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir. Varsayılan uygulama, SetRelatedWnd ile ayarlandıysa ilgili bir pencereyi günceller.

##  <a name="onanimationtimerpostupdate"></a>CAnimationController:: OnAnimationTimerPostUpdate

Bir animasyon güncelleştirmesi tamamlandıktan sonra Framework tarafından çağırılır.

```
virtual void OnAnimationTimerPostUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, EnableAnimationTimerEventHandler kullanarak Zamanlayıcı olay işleyicilerini etkinleştirirseniz çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir.

##  <a name="onanimationtimerpreupdate"></a>CAnimationController:: OnAnimationTimerPreUpdate

Bir animasyon güncelleştirmesi başlamadan önce Framework tarafından çağırılır.

```
virtual void OnAnimationTimerPreUpdate();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, EnableAnimationTimerEventHandler kullanarak Zamanlayıcı olay işleyicilerini etkinleştirirseniz çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir.

##  <a name="onanimationtimerrenderingtooslow"></a>CAnimationController:: Onanimationtimerrenderingtoolow

Bir animasyonun işleme çerçevesi oranı, istenen en düşük kare oranının altına düştüğünde Framework tarafından çağırılır.

```
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```

### <a name="parameters"></a>Parametreler

*fps*<br/>
Kare/saniye cinsinden geçerli kare hızı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, EnableAnimationTimerEventHandler kullanarak Zamanlayıcı olay işleyicilerini etkinleştirirseniz çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir. IUIAnimationTimer:: SetFrameRateThreshold çağırarak, istenen en düşük kare hızı belirtilir.

##  <a name="onanimationvaluechanged"></a>CAnimationController:: Onanimasyonvaluechanged

Animasyon değişkeninin değeri değiştiğinde Framework tarafından çağırılır.

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
Değeri değişmiş bir animasyon nesnesini tutan animasyon grubuna yönelik bir işaretçi.

*Nesnesini*<br/>
Değeri değişmiş bir animasyon değişkeni içeren animasyon nesnesine yönelik bir işaretçi.

*değişken*<br/>
Animasyon değişkenine yönelik bir işaretçi.

*Değer*<br/>
Yeni bir değer belirtir.

*prevValue*<br/>
Önceki değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirli bir animasyon değişkeni veya animasyon nesnesi için, EnableValueChangedEvent çağrılan animasyon değişken olaylarını etkinleştirirseniz çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir.

##  <a name="onbeforeanimationstart"></a>CAnimationController:: OnBeforeAnimationStart

Animasyon zamanlanmadan önce Framework tarafından çağırılır.

```
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parametreler

*pGroup*<br/>
Animasyonu başlamak üzere olan bir animasyon grubuna yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu çağrı ilgili CWnd 'e yönlendirilir ve belirtilen grup için animasyon başlamadan önce ek eylemler gerçekleştirmek üzere türetilmiş bir sınıfta geçersiz kılınabilir.

##  <a name="onhasprioritycancel"></a>CAnimationController:: OnHasPriorityCancel

Zamanlama çakışmalarını çözmek için Framework tarafından çağırılır.

```
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parametreler

*Pgroupzamanlandı*<br/>
Şu anda zamanlanmış görsel taslağa sahip olan grup.

*pGroupNew*<br/>
Zamanlama içinde olan yeni görsel taslağa sahip olan Grup, Pgroupzamanlandı tarafından sahip olunan zamanlanmış Görsel Taslakla çakışıyor.

*priorityEffect*<br/>
Pgroupzamanlanırsa daha yüksek önceliğe sahip olan pGroupNew üzerindeki olası etkisi.

### <a name="return-value"></a>Dönüş Değeri

PGroupNew 'un sahip olduğu film şeridi önceliğe sahipse TRUE döndürmelidir. Pgroupzamanlanan tarafından sahip olunan film şeridi önceliğe sahipse, FALSE döndürmelidir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, CAnimationController:: EnablePriorityComparisonHandler kullanarak Öncelik karşılaştırma olaylarını etkinleştirirseniz ve UI_ANIMATION_PHT_CANCEL belirtirseniz çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir. [Çakışma yönetimi](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)hakkında daha fazla bilgi Için WINDOWS Animation API belgelerini okuyun.

##  <a name="onhasprioritycompress"></a>CAnimationController:: OnHasPriorityCompress

Zamanlama çakışmalarını çözmek için Framework tarafından çağırılır.

```
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parametreler

*Pgroupzamanlandı*<br/>
Şu anda zamanlanmış görsel taslağa sahip olan grup.

*pGroupNew*<br/>
Zamanlama içinde olan yeni görsel taslağa sahip olan Grup, Pgroupzamanlandı tarafından sahip olunan zamanlanmış Görsel Taslakla çakışıyor.

*priorityEffect*<br/>
Pgroupzamanlanırsa daha yüksek önceliğe sahip olan pGroupNew üzerindeki olası etkisi.

### <a name="return-value"></a>Dönüş Değeri

PGroupNew 'un sahip olduğu film şeridi önceliğe sahipse TRUE döndürmelidir. Pgroupzamanlanan tarafından sahip olunan film şeridi önceliğe sahipse, FALSE döndürmelidir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, CAnimationController:: EnablePriorityComparisonHandler kullanarak Öncelik karşılaştırma olaylarını etkinleştirirseniz ve UI_ANIMATION_PHT_COMPRESS belirtirseniz çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir. [Çakışma yönetimi](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)hakkında daha fazla bilgi Için WINDOWS Animation API belgelerini okuyun.

##  <a name="onhaspriorityconclude"></a>CAnimationController:: Onhasprioritysonuçde

Zamanlama çakışmalarını çözmek için Framework tarafından çağırılır.

```
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parametreler

*Pgroupzamanlandı*<br/>
Şu anda zamanlanmış görsel taslağa sahip olan grup.

*pGroupNew*<br/>
Zamanlama içinde olan yeni görsel taslağa sahip olan Grup, Pgroupzamanlandı tarafından sahip olunan zamanlanmış Görsel Taslakla çakışıyor.

*priorityEffect*<br/>
Pgroupzamanlanırsa daha yüksek önceliğe sahip olan pGroupNew üzerindeki olası etkisi.

### <a name="return-value"></a>Dönüş Değeri

PGroupNew 'un sahip olduğu film şeridi önceliğe sahipse TRUE döndürmelidir. Pgroupzamanlanan tarafından sahip olunan film şeridi önceliğe sahipse, FALSE döndürmelidir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, CAnimationController:: EnablePriorityComparisonHandler kullanarak Öncelik karşılaştırma olaylarını etkinleştirirseniz ve UI_ANIMATION_PHT_CONCLUDE belirtirseniz çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir. [Çakışma yönetimi](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)hakkında daha fazla bilgi Için WINDOWS Animation API belgelerini okuyun.

##  <a name="onhasprioritytrim"></a>CAnimationController:: OnHasPriorityTrim

Zamanlama çakışmalarını çözmek için Framework tarafından çağırılır.

```
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>Parametreler

*Pgroupzamanlandı*<br/>
Şu anda zamanlanmış görsel taslağa sahip olan grup.

*pGroupNew*<br/>
Zamanlama içinde olan yeni görsel taslağa sahip olan Grup, Pgroupzamanlandı tarafından sahip olunan zamanlanmış Görsel Taslakla çakışıyor.

*priorityEffect*<br/>
Pgroupzamanlanırsa daha yüksek önceliğe sahip olan pGroupNew üzerindeki olası etkisi.

### <a name="return-value"></a>Dönüş Değeri

PGroupNew 'un sahip olduğu film şeridi önceliğe sahipse TRUE döndürmelidir. Pgroupzamanlanan tarafından sahip olunan film şeridi önceliğe sahipse, FALSE döndürmelidir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, CAnimationController:: EnablePriorityComparisonHandler kullanarak Öncelik karşılaştırma olaylarını etkinleştirirseniz ve UI_ANIMATION_PHT_TRIM belirtirseniz çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir. [Çakışma yönetimi](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)hakkında daha fazla bilgi Için WINDOWS Animation API belgelerini okuyun.

##  <a name="onstoryboardstatuschanged"></a>CAnimationController:: OnStoryboardStatusChanged

Görsel taslak durumu değiştiğinde Framework tarafından çağırılır.

```
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,
    UI_ANIMATION_STORYBOARD_STATUS newStatus,
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>Parametreler

*pGroup*<br/>
Durumu değişmiş olan görsel taslağa sahip bir animasyon grubuna yönelik bir işaretçi.

*newStatus*<br/>
Yeni durumu belirtir.

*previousStatus*<br/>
Önceki durumu belirtir.

### <a name="remarks"></a>Açıklamalar

CAnimationController:: EnableStoryboardEventHandler kullanarak görsel taslak olaylarını etkinleştirirseniz bu yöntem çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir.

##  <a name="onstoryboardupdated"></a>CAnimationController:: OnStoryboardUpdated

Görsel taslak güncelleştirildiği zaman Framework tarafından çağırılır.

```
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>Parametreler

*pGroup*<br/>
Görsel taslağa sahip bir grubun işaretçisi.

### <a name="remarks"></a>Açıklamalar

CAnimationController:: EnableStoryboardEventHandler kullanarak görsel taslak olaylarını etkinleştirirseniz bu yöntem çağrılır. Uygulamaya özel eylemler gerçekleştirmek için türetilmiş bir sınıfta geçersiz kılınabilir.

##  <a name="removeallanimationgroups"></a>CAnimationController:: RemoveAllAnimationGroups

Tüm animasyon gruplarını animasyon denetleyicisinden kaldırır.

```
void RemoveAllAnimationGroups();
```

### <a name="remarks"></a>Açıklamalar

Tüm gruplar silinecek, bu, uygulama düzeyinde depolanıyorsa işaretçisi geçersiz kılınmalıdır. Silinmekte olan bir grup için CAnimationGroup:: m_bAutodestroyAnimationObjects TRUE ise, o gruba ait olan tüm animasyon nesneleri silinir; Aksi takdirde, üst animasyon denetleyicisine yapılan başvurular NULL olarak ayarlanır ve bu, başka bir denetleyiciye eklenebilir.

##  <a name="removeanimationgroup"></a>CAnimationController:: RemoveAnimationGroup

Belirtilen KIMLIĞE sahip bir animasyon grubunu animasyon denetleyicisinden kaldırır.

```
void RemoveAnimationGroup(UINT32 nGroupID);
```

### <a name="parameters"></a>Parametreler

*Ngroupıd*<br/>
Animasyon grubu KIMLIĞINI belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir animasyon grubunu iç Grup listesinden kaldırır ve siler, bu nedenle bu animasyon grubuna bir işaretçi depoladıysanız geçersiz kılınmalıdır. CAnimationGroup:: m_bAutodestroyAnimationObjects TRUE ise, o gruba ait olan tüm animasyon nesneleri silinir; Aksi takdirde, üst animasyon denetleyicisine yapılan başvurular NULL olarak ayarlanır ve bu, başka bir denetleyiciye eklenebilir.

##  <a name="removeanimationobject"></a>CAnimationController:: RemoveAnimationObject

Animasyon denetleyicisinden bir animasyon nesnesi kaldırın.

```
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,
    BOOL bNoDelete = FALSE);
```

### <a name="parameters"></a>Parametreler

*Nesnesini*<br/>
Animasyon nesnesine yönelik bir işaretçi.

*bNoDelete*<br/>
Bu parametre TRUE ise, kaldırma işlemi sırasında nesne silinmez.

### <a name="remarks"></a>Açıklamalar

Animasyon denetleyicisi ve animasyon grubundan bir animasyon nesnesini kaldırır. Belirli bir nesnenin artık animasyon uygulanmamalıdır veya nesneyi başka bir animasyon denetleyicisine taşımanız gerekiyorsa bu işlevi çağırın. Son durumda bNoDelete doğru olmalıdır.

##  <a name="removetransitions"></a>CAnimationController:: Removetransıtions

Belirtilen gruba ait olan animasyon nesnelerinden geçişleri kaldırır.

```
void RemoveTransitions(UINT32 nGroupID);
```

### <a name="parameters"></a>Parametreler

*Ngroupıd*<br/>
Grup KIMLIĞINI belirtir.

### <a name="remarks"></a>Açıklamalar

Grup, animasyon nesneleri üzerinde döngü yapar ve her bir animasyon nesnesi için Cleargeçişler (FALSE) çağırır. Bu yöntem, animasyon zamanlandıktan sonra Framework tarafından çağırılır.

##  <a name="schedulegroup"></a>CAnimationController:: ScheduleGroup

Bir animasyon zamanlar.

```
BOOL ScheduleGroup(
    UINT32 nGroupID,
    UI_ANIMATION_SECONDS time = 0.0);
```

### <a name="parameters"></a>Parametreler

*Ngroupıd*<br/>
Zamanlanacak animasyon grubu KIMLIĞINI belirtir.

*saat*<br/>
Zamanlama süresini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Animasyon başarıyla zamanlanırsa TRUE. Film şeridi oluşturulmadıysa veya başka bir hata oluşursa FALSE.

### <a name="remarks"></a>Açıklamalar

BScheduleNow parametresi ile AnimateGroup ' u çağırmanız gerekir. IUIAnimationTimer:: GetTime öğesinden elde edilen istenen animasyon süresini belirtebilirsiniz. Zaman parametresi 0,0 ise, Animasyon geçerli saat için zamanlanır.

##  <a name="setrelatedwnd"></a>CAnimationController:: SetRelatedWnd

Animasyon denetleyicisi ve pencere arasında bir ilişki oluşturur.

```
void SetRelatedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Ayarlanacak pencere nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İlgili bir CWnd nesnesi ayarlandıysa, animasyon yöneticisinin durumu değiştiğinde veya zamanlayıcı güncelleştirme sonrası olay oluştuğunda animasyon denetleyicisi onu otomatik olarak güncelleştirebilir (WM_PAINT iletisi gönderebilir).

##  <a name="updateanimationmanager"></a>CAnimationController:: UpdateAnimationManager

Animasyon yöneticisini tüm animasyon değişkenlerinin değerlerini güncelleştirecek şekilde yönlendirir.

```
virtual void UpdateAnimationManager();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırmak, animasyon yöneticisini geçerli zamana ilerletir, film şeridi durumlarını gerektiği şekilde değiştirir ve herhangi bir animasyon değişkenini uygun bir enterpolasyonlu değere göre güncelleştiriyor. Dahili olarak bu yöntem IUIAnimationTimer:: GetTime (Tımenow) ve IUIAnimationManager:: Update (timeNow) öğesini çağırır. Bu davranışı özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
