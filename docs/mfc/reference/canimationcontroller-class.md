---
title: CAnimationController sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ab340cb897d2e97f6d2a1ce0518077cfff2563b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222186"
---
# <a name="canimationcontroller-class"></a>CAnimationController sınıfı
Oluşturmak ve animasyonları yönetmek için merkezi bir arabirim sağlayan animasyon denetleyicisini uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimationController : public CObject;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationController::CAnimationController](#canimationcontroller)|Bir animasyon denetleyicisi oluşturur.|  
|[CAnimationController:: ~ CAnimationController](#canimationcontroller__~canimationcontroller)|Yıkıcı. Animasyon denetleyicisini nesne yok ediliyorken çağırılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationController::AddAnimationObject](#addanimationobject)|Bir animasyon nesne animasyon denetleyiciye ait bir gruba ekler.|  
|[CAnimationController::AddKeyframeToGroup](#addkeyframetogroup)|Bir anahtar kare grubuna ekler.|  
|[CAnimationController::AnimateGroup](#animategroup)|Bir grubu animasyonu çalıştıracak şekilde hazırlar ve isteğe bağlı olarak zamanlar.|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Fazla Yüklendi. Animasyon zamanlandıysa grubu temizlemek için framework tarafından çağırılır.|  
|[CAnimationController::CreateKeyframe](#createkeyframe)|Fazla Yüklendi. Geçişi bağlıdır ve belirtilen gruba ekleyen bir anahtar kare oluşturur.|  
|[CAnimationController::EnableAnimationManagerEvent](#enableanimationmanagerevent)|Ayarlar veya animasyon yöneticisinin durumu değiştiğinde çağrılacak işleyici serbest bırakır.|  
|[CAnimationController::EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|Zamanlama olayları için bir işleyici ve güncelleştirmeleri zamanlama için işleyici sürümleri veya ayarlar.|  
|[CAnimationController::EnablePriorityComparisonHandler](#enableprioritycomparisonhandler)|Ayarlar veya zamanlanmış bir görsel taslak iptal edildi, tamamlanmış, kırpılmış sıkıştırılmış veya olup olmadığını belirlemek için çağrılacak olan öncelik karşılaştırma işleyici serbest bırakır.|  
|[CAnimationController::EnableStoryboardEventHandler](#enablestoryboardeventhandler)|Ayarlar veya görsel taslak durumu ve güncelleştirme olaylarını için bir işleyici serbest bırakır.|  
|[CAnimationController::FindAnimationGroup](#findanimationgroup)|Fazla Yüklendi. Bir animasyon grubu tarafından şeridini bulur.|  
|[CAnimationController::FindAnimationObject](#findanimationobject)|Belirtilen bir animasyon değişkenini içeren animasyon nesnesi bulur.|  
|[CAnimationController::GetKeyframeStoryboardStart](#getkeyframestoryboardstart)|Görsel taslak başlangıcını tanımlayan bir anahtar kare döndürür.|  
|[CAnimationController::GetUIAnimationManager](#getuianimationmanager)|Kapsüllenmiş IUIAnimationManager nesneye erişim sağlar.|  
|[CAnimationController::GetUIAnimationTimer](#getuianimationtimer)|Kapsüllenmiş IUIAnimationTimer nesneye erişim sağlar.|  
|[CAnimationController::GetUITransitionFactory](#getuitransitionfactory)|IUIAnimationTransitionFactory arabirimi ya da geçiş kitaplığı oluşturulması başarısız olursa NULL bir işaretçi.|  
|[CAnimationController::GetUITransitionLibrary](#getuitransitionlibrary)|Kapsüllenmiş IUIAnimationTransitionLibrary nesneye erişim sağlar.|  
|[CAnimationController::IsAnimationInProgress](#isanimationinprogress)|En az bir grup animasyon yürütmeyi olup olmadığını söyler.|  
|[CAnimationController::IsValid](#isvalid)|Animasyon denetleyicisini geçerli olup olmadığını söyler.|  
|[CAnimationController::OnAnimationIntegerValueChanged](#onanimationintegervaluechanged)|Animasyon değişkeninin tamsayı değeri değiştiğinde framework tarafından çağırılır.|  
|[CAnimationController::OnAnimationManagerStatusChanged](#onanimationmanagerstatuschanged)|Animasyon Yöneticisi'nden StatusChanged olaya yanıt framework tarafından çağırılır.|  
|[CAnimationController::OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|Bir animasyon Güncelleştirme tamamlandıktan sonra framework tarafından çağırılır.|  
|[CAnimationController::OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|Bir animasyon güncelleştirme başlamadan önce framework tarafından çağırılır.|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](#onanimationtimerrenderingtooslow)|Bir animasyon işleme kare hızını en az tercih kare hızı düştüğünde framework tarafından çağırılır.|  
|[CAnimationController::OnAnimationValueChanged](#onanimationvaluechanged)|Animasyon değişkeninin değeri değiştiğinde framework tarafından çağırılır.|  
|[CAnimationController::OnBeforeAnimationStart](#onbeforeanimationstart)|Animasyon zamanlanmadan önce framework tarafından doğru çağrılır.|  
|[CAnimationController::OnHasPriorityCancel](#onhasprioritycancel)|Zamanlama çakışmaları çözümlemek için framework tarafından çağırılır.|  
|[CAnimationController::OnHasPriorityCompress](#onhasprioritycompress)|Zamanlama çakışmaları çözümlemek için framework tarafından çağırılır.|  
|[CAnimationController::OnHasPriorityConclude](#onhaspriorityconclude)|Zamanlama çakışmaları çözümlemek için framework tarafından çağırılır.|  
|[CAnimationController::OnHasPriorityTrim](#onhasprioritytrim)|Zamanlama çakışmaları çözümlemek için framework tarafından çağırılır.|  
|[CAnimationController::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Görsel taslak durumu değiştiğinde framework tarafından çağırılır.|  
|[CAnimationController::OnStoryboardUpdated](#onstoryboardupdated)|Görsel taslak güncellendiğinde framework tarafından çağırılır.|  
|[CAnimationController::RemoveAllAnimationGroups](#removeallanimationgroups)|Tüm animasyon grupları animasyon denetleyicisinden kaldırır.|  
|[CAnimationController::RemoveAnimationGroup](#removeanimationgroup)|Belirtilen Kimliğe sahip bir animasyon grubu animasyon denetleyicisinden kaldırır.|  
|[CAnimationController::RemoveAnimationObject](#removeanimationobject)|Bir animasyon nesne animasyon denetleyicisinden kaldırın.|  
|[CAnimationController::RemoveTransitions](#removetransitions)|Belirtilen gruba ait animasyon nesneleri geçişleri kaldırır.|  
|[CAnimationController::ScheduleGroup](#schedulegroup)|Bir animasyon zamanlar.|  
|[CAnimationController::SetRelatedWnd](#setrelatedwnd)|Animasyon denetleyicisini ve bir pencere arasında bir ilişki kurar.|  
|[CAnimationController::UpdateAnimationManager](#updateanimationmanager)|Tüm animasyon değişkenlerin değerleri güncelleştirmek için animasyon Yöneticisi yönlendirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Fazla Yüklendi. Grubu temizler Yardımcısı.|  
|[CAnimationController::OnAfterSchedule](#onafterschedule)|Belirtilen grup için bir animasyon yalnızca zamanlandı framework tarafından çağırılır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationController::gkeyframeStoryboardStart](#g_keyframestoryboardstart)|Görsel taslak başlangıcını temsil eden bir anahtar kare.|  
|[CAnimationController::m_bIsValid](#m_bisvalid)|Bir animasyon denetleyicisini geçerli olup olmadığını belirtir. Geçerli işletim sistemi Windows animasyon API'sı desteklemiyorsa bu üye FALSE olarak ayarlanır.|  
|[CAnimationController::m_lstAnimationGroups](#m_lstanimationgroups)|Bu animasyonu denetleyiciye ait animasyon gruplarının listesi.|  
|[CAnimationController::m_pAnimationManager](#m_panimationmanager)|Animasyon Yöneticisi COM nesnesine bir işaretçi depolar.|  
|[CAnimationController::m_pAnimationTimer](#m_panimationtimer)|Animasyon Zamanlayıcı COM nesnesine bir işaretçi depolar.|  
|[CAnimationController::m_pRelatedWnd](#m_prelatedwnd)|Animasyon yöneticisinin durumu değiştirildi veya sonrası güncelleştirme olayının meydana geldiğini, otomatik olarak çizilebilir ilgili bir CWnd nesnesine bir işaretçi. NULL olabilir.|  
|[CAnimationController::m_pTransitionFactory](#m_ptransitionfactory)|Geçiş Fabrika COM nesnesine bir işaretçi depolar.|  
|[CAnimationController::m_pTransitionLibrary](#m_ptransitionlibrary)|Geçiş kitaplığı COM nesnesine bir işaretçi depolar.|  
  
## <a name="remarks"></a>Açıklamalar  
 CAnimationController sınıfı animasyonları yöneten temel sınıftır. Animasyon denetleyicisini bir veya daha fazla örneğini bir uygulamada oluşturabilir ve, isteğe bağlı olarak, animasyon denetleyicisini örneğini CAnimationController::SetRelatedWnd kullanarak CWnd nesnesine bağlanmak. Bu bağlantı, WM_PAINT ilgili pencereyi otomatik olarak animasyon Yöneticisi durum değiştirildi veya animasyon Zamanlayıcı güncelleştirildi göndermek için gereklidir. Bu ilişki etkinleştirmezseniz, el ile animasyon görüntüleyen bir pencere yeniden çizmeniz gerekir. Bu amaçla CAnimationController bir sınıf türetin ve OnAnimationManagerStatusChanged ve/veya OnAnimationTimerPostUpdate geçersiz kılın ve bir veya daha fazla windows gerekli olduğunda geçersiz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationController`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationcontroller"></a>  CAnimationController:: ~ CAnimationController  
 Yıkıcı. Animasyon denetleyicisini nesne yok ediliyorken çağırılır.  
  
```  
virtual ~CAnimationController(void);
```   
  
##  <a name="addanimationobject"></a>  CAnimationController::AddAnimationObject  
 Bir animasyon nesne animasyon denetleyiciye ait bir gruba ekler.  
  
```  
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```  
  
### <a name="parameters"></a>Parametreler  
 *pObject*  
 Bir animasyon nesnesine bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa burada pObject eklenmiş olan mevcut veya yeni animasyon grubu için bir işaretçi; PObject zaten başka bir animasyon denetleyiciye ait bir gruba eklenmiş yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon denetleyicisini animasyon nesne eklemek için bu yöntemi çağırın. Bir nesne, nesnenin GroupID göre bir gruba eklenir (CAnimationBaseObject::SetID bakın). Belirtilen grup kimliği ile eklenen ilk nesnenin ise animasyon denetleyicisini yeni bir grup oluşturacaksınız. Bir animasyon nesne yalnızca bir animasyon denetleyicisini eklenebilir. Bir nesne başka bir denetleyiciye eklemeniz gerekiyorsa, RemoveAnimationObject çağırın. Bir gruba zaten eklenmiş olan bir nesne için yeni bir grup kimliği ile SetID çağırırsanız, nesne eski grubundan kaldırıldı ve belirtilen kimliğe sahip başka bir gruba eklendi  
  
##  <a name="addkeyframetogroup"></a>  CAnimationController::AddKeyframeToGroup  
 Bir anahtar kare grubuna ekler.  
  
```  
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,  
    CBaseKeyFrame* pKeyframe);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Grup kimliğini belirtir.  
  
 *pKeyframe*  
 Bir anahtar kare işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, bu yöntemi çağıran, bunun yerine, CAnimationController::CreateKeyframe kullanın oluşturur ve oluşturulan ana kare bir gruba otomatik olarak ekler gerek yoktur.  
  
##  <a name="animategroup"></a>  CAnimationController::AnimateGroup  
 Bir grubu animasyonu çalıştıracak şekilde hazırlar ve isteğe bağlı olarak zamanlar.  
  
```  
BOOL AnimateGroup(
    UINT32 nGroupID,  
    BOOL bScheduleNow = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 GroupID belirtir.  
  
 *bScheduleNow*  
 Animasyon hemen çalıştırılıp çalıştırılmayacağını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE animasyon başarıyla zamanlandı ve çalıştırın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, görsel taslak oluşturma, animasyon değişkenleri ekleniyor, geçişleri uygulama ve ana kareleri ayarı asıl işi yapar. BScheduleNow FALSE olarak ayarlarsanız zamanlama gecikme mümkündür. Bu durumda belirtilen grup animasyon için ayarlanmış olan bir görsel taslak tutar. Bu noktada film şeridini ve animasyon değişkenlerinin olayları ayarlayabilirsiniz. Olduğunda, gerçekten animasyon çağrı CAnimationController::ScheduleGroup çalıştırmanız gerekir.  
  
##  <a name="canimationcontroller"></a>  CAnimationController::CAnimationController  
 Bir animasyon denetleyicisi oluşturur.  
  
```  
CAnimationController(void);
```   
  
##  <a name="cleanupgroup"></a>  CAnimationController::CleanUpGroup  
 Animasyon zamanlandıysa grubu temizlemek için framework tarafından çağırılır.  
  
```  
void CleanUpGroup(UINT32 nGroupID);  
void CleanUpGroup(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 GroupID belirtir.  
  
 *pGroup*  
 Animasyon grubu temizlemek için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir animasyon zamanlandıktan sonra uygun olmadığı için bu yöntem tüm geçişler ve ana kareleri belirtilen grubundan kaldırır.  
  
##  <a name="createkeyframe"></a>  CAnimationController::CreateKeyframe  
 Geçişi bağlıdır ve belirtilen gruba ekleyen bir anahtar kare oluşturur.  
  
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
 *nGroupID*  
 Ana kare oluşturulduğu Grup Kimliğini belirtir.  
  
 *pTransition*  
 Geçiş için bir işaretçi. Ana kare, bu geçişten sonra görsel taslağa dönüştürme eklenir.  
  
 *pKeyframe*  
 Bu ana kare için temel bir anahtar kare işaretçi.  
  
 *uzaklık*  
 PKeyframe tarafından belirtilen temel kareden saniye cinsinden uzaklığı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa yeni oluşturulan bir ana kare işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen işaretçi depolamak ve yeni oluşturulan ana kare üzerinde diğer ana kareleri temel (ikinci aşırı yükleme bakın). Geçişleri durdurursunuz başlayın - CBaseTransition::SetKeyframes görmek mümkündür. Bu şekilde, oluşturulan ana kare animasyon grupları tarafından otomatik olarak silindiği için silmeniz gerekmez. Diğer ana kareleri ve geçişleri göre ana kareleri oluştururken dikkatli olun ve döngüsel başvurulardan kaçının.  
  
##  <a name="enableanimationmanagerevent"></a>  CAnimationController::EnableAnimationManagerEvent  
 Ayarlar veya animasyon yöneticisinin durumu değiştiğinde çağrılacak işleyici serbest bırakır.  
  
```  
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bSistemlerde*  
 Ayarlayın veya bir işleyici yayın belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleyici başarılı bir şekilde ayarlayın veya serbest gerekiyorsa TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işleyici (etkin) olarak ayarlandığında animasyon yöneticisinin durumu değiştiğinde Windows animasyon OnAnimationManagerStatusChanged çağırır.  
  
##  <a name="enableanimationtimereventhandler"></a>  CAnimationController::EnableAnimationTimerEventHandler  
 Zamanlama olayları için bir işleyici ve güncelleştirmeleri zamanlama için işleyici sürümleri veya ayarlar.  
  
```  
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,  
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bSistemlerde*  
 Ayarlayın ya da işleyicilerini serbest belirtir.  
  
 *idleBehavior*  
 Zamanlayıcı güncelleştirme işleyicisi için boşta davranışı belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleyicileri başarılı bir şekilde ayarlayın veya serbest TRUE; Bu yanlış yöntemi bırakmadan önce işleyicileri için ikinci bir kez çağrılır ve diğer, hata meydana gelir.  
  
### <a name="remarks"></a>Açıklamalar  
 Ne zaman işleyicileri (etkin) Windows animasyon API çağrıları, OnAnimationTimerPreUpdate OnAnimationTimerPostUpdate, OnRenderingTooSlow yöntemleri ayarlanır. Animasyon zamanlayıcılar Windows animasyon API'sı güncelleştirme film şeritleri izin vermek etkinleştirmeniz gerekir. Aksi takdirde, animasyon yönlendirmek için tüm animasyon değişkenlerin değerleri güncelleştirmek üzere manager CAnimationController::UpdateAnimationManager çağırmak gerekir.  
  
##  <a name="enableprioritycomparisonhandler"></a>  CAnimationController::EnablePriorityComparisonHandler  
 Ayarlar veya zamanlanmış bir görsel taslak iptal edildi, tamamlanmış, kırpılmış sıkıştırılmış veya olup olmadığını belirlemek için çağrılacak olan öncelik karşılaştırma işleyici serbest bırakır.  
  
```  
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwHandlerType*  
 UI_ANIMATION_PHT_ birleşimi (bkz. Notlar), ayarlamak veya yayın için hangi işleyiciler belirten bayraklar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleyici başarılı bir şekilde ayarlayın veya serbest gerekiyorsa TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işleyici (etkin) olarak ayarlandığında, Windows animasyon dwHandlerType bağlı olarak aşağıdaki sanal yöntemleri çağırır: OnHasPriorityCancel, OnHasPriorityConclude, OnHasPriorityTrim, OnHasPriorityCompress. dwHandler aşağıdaki bayrakların birleşimi olabilir: UI_ANIMATION_PHT_NONE - sürüm tüm işleyiciler UI_ANIMATION_PHT_CANCEL - Ayarla iptal karşılaştırma işleyici UI_ANIMATION_PHT_CONCLUDE - Conclude karşılaştırma işleyici UI_ANIMATION_PHT_COMPRESS ayarlama - ayarlayın Sıkıştırma karşılaştırma işleyici - kırpma karşılaştırma işleyicisini UI_ANIMATION_PHT_CANCEL_REMOVE - iptal karşılaştırma işleyici UI_ANIMATION_PHT_CONCLUDE_REMOVE Kaldır - UI_ANIMATION_PHT_TRIM Conclude karşılaştırma işleyici UI_ANIMATION_PHT_COMPRESS_ Kaldır REMOVE - sıkıştırma karşılaştırma işleyici UI_ANIMATION_PHT_TRIM_REMOVE - remove kırpma karşılaştırma işleyici Kaldır  
  
##  <a name="enablestoryboardeventhandler"></a>  CAnimationController::EnableStoryboardEventHandler  
 Ayarlar veya görsel taslak durumu ve güncelleştirme olaylarını için bir işleyici serbest bırakır.  
  
```  
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Grup kimliğini belirtir.  
  
 *bSistemlerde*  
 Ayarlayın veya bir işleyici yayın belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleyici başarılı bir şekilde ayarlayın veya serbest gerekiyorsa TRUE; Belirtilen animasyon grubun artık bulunamadı veya belirtilen grup için animasyon başlatılamadı ve iç şeridini NULL ise yanlış.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işleyici olarak ayarlandığında (etkin) Windows animasyon API'sı OnStoryboardStatusChanges ve OnStoryboardUpdated sanal yöntemleri çağırır. Belirtilen animasyon grubu için CAnimationController::Animate çağrıldıktan sonra kapsüllenmiş IUIAnimationStoryboard nesnesi oluşturur çünkü bir işleyici ayarlamanız gerekir.  
  
##  <a name="findanimationgroup"></a>  CAnimationController::FindAnimationGroup  
 Grup Kimliği bir animasyon group bulur  
  
```  
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);  
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Bir GroupID belirtir.  
  
 *pStoryboard*  
 Görsel taslak için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon grubu ya da grubun belirtilen Kimliğe sahip bulunamazsa NULL bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanında animasyon grup bulmak için bu yöntemi kullanın. Bir grup oluşturulur ve belirli GroupID ilk animasyon nesnesiyle animasyon denetleyicisini eklendiğinde iç animasyon grupları listesine eklenir.  
  
##  <a name="findanimationobject"></a>  CAnimationController::FindAnimationObject  
 Belirtilen bir animasyon değişkenini içeren animasyon nesnesi bulur.  
  
```  
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,  
    CAnimationBaseObject** ppObject,  
    CAnimationGroup** ppGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 *pVariable*  
 Animasyon değişkeninin bir işaretçi.  
  
 *ppObject*  
 Çıktı. Animasyon nesne veya NULL bir işaretçi içerir.  
  
 *ppGroup*  
 Çıktı. Animasyon grubuna animasyon nesne ya da NULL bir işaretçi içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne bulunduysa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Olay işleyicilerindeki gelen animasyon değişkenin bir animasyon nesneyi bulmak için gerekli olan çağrılır.  
  
##  <a name="g_keyframestoryboardstart"></a>  CAnimationController::gkeyframeStoryboardStart  
 Görsel taslak başlangıcını temsil eden bir anahtar kare.  
  
```  
static CBaseKeyFrame gkeyframeStoryboardStart;  
```  
  
##  <a name="getkeyframestoryboardstart"></a>  CAnimationController::GetKeyframeStoryboardStart  
 Görsel taslak başlangıcını tanımlayan bir anahtar kare döndürür.  
  
```  
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görsel taslak başlangıcını tanımlayan temel ana kare işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ana kare şu film şeridi başladığında zamanlı herhangi bir ana kareleri veya geçişleri temel almasını edinin.  
  
##  <a name="getuianimationmanager"></a>  CAnimationController::GetUIAnimationManager  
 Kapsüllenmiş IUIAnimationManager nesneye erişim sağlar.  
  
```  
IUIAnimationManager* GetUIAnimationManager();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 IUIAnimationManager arabirimi veya animasyon Yöneticisi oluşturulamadı yoksa NULL bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli işletim sistemi Windows animasyon API'sı desteklemiyorsa, bu yöntem NULL döndürür ve bundan sonra tüm sonraki çağrılarda CAnimationController::IsValid false değerini döndürür. IUIAnimationManager animasyon denetleyicisi tarafından Sarmalanan değil, arabirim yöntemleri çağırmak için erişim gerekebilir.  
  
##  <a name="getuianimationtimer"></a>  CAnimationController::GetUIAnimationTimer  
 Kapsüllenmiş IUIAnimationTimer nesneye erişim sağlar.  
  
```  
IUIAnimationTimer* GetUIAnimationTimer();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 IUIAnimationTimer arabirimi veya animasyon Zamanlayıcı oluşturulması başarısız olursa NULL bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli işletim sistemi Windows animasyon API'sı desteklemiyorsa, bu yöntem NULL döndürür ve bundan sonra tüm sonraki çağrılarda CAnimationController::IsValid false değerini döndürür.  
  
##  <a name="getuitransitionfactory"></a>  CAnimationController::GetUITransitionFactory  
 IUIAnimationTransitionFactory arabirimi ya da geçiş kitaplığı oluşturulması başarısız olursa NULL bir işaretçi.  
  
```  
IUIAnimationTransitionFactory* GetUITransitionFactory();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 IUIAnimationTransitionFactory ya da geçiş factory oluşturulması başarısız olursa NULL bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli işletim sistemi Windows animasyon API'sı desteklemiyorsa, bu yöntem NULL döndürür ve bundan sonra tüm sonraki çağrılarda CAnimationController::IsValid false değerini döndürür.  
  
##  <a name="getuitransitionlibrary"></a>  CAnimationController::GetUITransitionLibrary  
 Kapsüllenmiş IUIAnimationTransitionLibrary nesneye erişim sağlar.  
  
```  
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 IUIAnimationTransitionLibrary arabirimi ya da geçiş kitaplığı oluşturulması başarısız olursa NULL bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli işletim sistemi Windows animasyon API'sı desteklemiyorsa, bu yöntem NULL döndürür ve bundan sonra tüm sonraki çağrılarda CAnimationController::IsValid false değerini döndürür.  
  
##  <a name="isanimationinprogress"></a>  CAnimationController::IsAnimationInProgress  
 En az bir grup animasyon yürütmeyi olup olmadığını söyler.  
  
```  
virtual BOOL IsAnimationInProgress();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu animasyon denetleyicisini için devam eden bir animasyonu ise TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon Yöneticisi durumunu denetler ve durum UI_ANIMATION_MANAGER_BUSY ise true değeri döndürür.  
  
##  <a name="isvalid"></a>  CAnimationController::IsValid  
 Animasyon denetleyicisini geçerli olup olmadığını söyler.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon denetleyicisini geçerli ise TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi döndürür yalnızca Windows animasyon API'sı geçerli işletim sistemi ve animasyon Yöneticisi oluşturulmasını desteklenmiyorsa FALSE başarısız oldu, çünkü kayıtlı değil. En az bir kez bu bayrağının ayarını neden COM kitaplıklarının başlatmadan sonra GetUIAnimationManager çağırmanız gerekir.  
  
##  <a name="m_bisvalid"></a>  CAnimationController::m_bIsValid  
 Bir animasyon denetleyicisini geçerli olup olmadığını belirtir. Geçerli işletim sistemi Windows animasyon API'sı desteklemiyorsa bu üye FALSE olarak ayarlanır.  
  
```  
BOOL m_bIsValid;  
```  
  
##  <a name="m_lstanimationgroups"></a>  CAnimationController::m_lstAnimationGroups  
 Bu animasyonu denetleyiciye ait animasyon gruplarının listesi.  
  
```  
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;  
```  
  
##  <a name="m_panimationmanager"></a>  CAnimationController::m_pAnimationManager  
 Animasyon Yöneticisi COM nesnesine bir işaretçi depolar.  
  
```  
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;  
```  
  
##  <a name="m_panimationtimer"></a>  CAnimationController::m_pAnimationTimer  
 Animasyon Zamanlayıcı COM nesnesine bir işaretçi depolar.  
  
```  
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;  
```  
  
##  <a name="m_prelatedwnd"></a>  CAnimationController::m_pRelatedWnd  
 Animasyon yöneticisinin durumu değiştirildi veya sonrası güncelleştirme olayının meydana geldiğini, otomatik olarak çizilebilir ilgili bir CWnd nesnesine bir işaretçi. NULL olabilir.  
  
```  
CWnd* m_pRelatedWnd;  
```  
  
##  <a name="m_ptransitionfactory"></a>  CAnimationController::m_pTransitionFactory  
 Geçiş Fabrika COM nesnesine bir işaretçi depolar.  
  
```  
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;  
```  
  
##  <a name="m_ptransitionlibrary"></a>  CAnimationController::m_pTransitionLibrary  
 Geçiş kitaplığı COM nesnesine bir işaretçi depolar.  
  
```  
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;  
```  
  
##  <a name="onafterschedule"></a>  CAnimationController::OnAfterSchedule  
 Belirtilen grup için bir animasyon yalnızca zamanlandı framework tarafından çağırılır.  
  
```  
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroup*  
 Zamanlandı bir animasyon grubu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama ana kareleri belirtilen gruptan kaldırır ve belirtilen gruba ait olan bir animasyon değişkenini geçer. Herhangi bir ek eylem animasyon zamanlama sırasında gerçekleştirilecek türetilen bir sınıfta geçersiz kılınabilir.  
  
##  <a name="onanimationintegervaluechanged"></a>  CAnimationController::OnAnimationIntegerValueChanged  
 Animasyon değişkeninin tamsayı değeri değiştiğinde framework tarafından çağırılır.  
  
```  
virtual void OnAnimationIntegerValueChanged(
    CAnimationGroup* pGroup,  
    CAnimationBaseObject* pObject,  
    IUIAnimationVariable* variable,  
    INT32 newValue,  
    INT32 prevValue);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroup*  
 Bir animasyon nesne değeri tutan bir animasyon grubu için bir işaretçi değişti.  
  
 *pObject*  
 Animasyon değişkenin değeri değişti içeren bir animasyon nesne işaretçisi.  
  
 *Değişkeni*  
 Animasyon değişkenin bir işaretçi.  
  
 *newValue*  
 Yeni bir değer belirtir.  
  
 *prevValue*  
 Önceki değeri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli bir animasyon değişkenini veya animasyon nesne için adlı EnableIntegerValueChangedEvent ile animasyon değişken olayları etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir.  
  
##  <a name="onanimationmanagerstatuschanged"></a>  CAnimationController::OnAnimationManagerStatusChanged  
 Animasyon Yöneticisi'nden StatusChanged olaya yanıt framework tarafından çağırılır.  
  
```  
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,  
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Parametreler  
 *newStatus*  
 Yeni animasyon Yöneticisi durumu.  
  
 *previousStatus*  
 Önceki animasyon Yöneticisi durumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon Yöneticisi olaylarını EnableAnimationManagerEvent ile etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir. Varsayılan uygulama, SetRelatedWnd ile ayarlarsanız ilgili pencere güncelleştirir.  
  
##  <a name="onanimationtimerpostupdate"></a>  CAnimationController::OnAnimationTimerPostUpdate  
 Bir animasyon Güncelleştirme tamamlandıktan sonra framework tarafından çağırılır.  
  
```  
virtual void OnAnimationTimerPostUpdate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Zamanlayıcı olay işleyicileri EnableAnimationTimerEventHandler kullanarak etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir.  
  
##  <a name="onanimationtimerpreupdate"></a>  CAnimationController::OnAnimationTimerPreUpdate  
 Bir animasyon güncelleştirme başlamadan önce framework tarafından çağırılır.  
  
```  
virtual void OnAnimationTimerPreUpdate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Zamanlayıcı olay işleyicileri EnableAnimationTimerEventHandler kullanarak etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir.  
  
##  <a name="onanimationtimerrenderingtooslow"></a>  CAnimationController::OnAnimationTimerRenderingTooSlow  
 Bir animasyon işleme kare hızını en az tercih kare hızı düştüğünde framework tarafından çağırılır.  
  
```  
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```  
  
### <a name="parameters"></a>Parametreler  
 *fps*  
 Geçerli kare hızını kare / saniye.  
  
### <a name="remarks"></a>Açıklamalar  
 Zamanlayıcı olay işleyicileri EnableAnimationTimerEventHandler kullanarak etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir. En az tercih kare hızı IUIAnimationTimer::SetFrameRateThreshold çağırarak belirtilir.  
  
##  <a name="onanimationvaluechanged"></a>  CAnimationController::OnAnimationValueChanged  
 Animasyon değişkeninin değeri değiştiğinde framework tarafından çağırılır.  
  
```  
virtual void OnAnimationValueChanged(
    CAnimationGroup* pGroup,  
    CAnimationBaseObject* pObject,  
    IUIAnimationVariable* variable,  
    DOUBLE newValue,  
    DOUBLE prevValue);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroup*  
 Bir animasyon nesne değeri tutan bir animasyon grubu için bir işaretçi değişti.  
  
 *pObject*  
 Animasyon değişkenin değeri değişti içeren bir animasyon nesne işaretçisi.  
  
 *Değişkeni*  
 Animasyon değişkenin bir işaretçi.  
  
 *newValue*  
 Yeni bir değer belirtir.  
  
 *prevValue*  
 Önceki değeri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirli bir animasyon değişkenini veya animasyon nesne için adlı EnableValueChangedEvent ile animasyon değişken olayları etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir.  
  
##  <a name="onbeforeanimationstart"></a>  CAnimationController::OnBeforeAnimationStart  
 Animasyon zamanlanmadan önce framework tarafından doğru çağrılır.  
  
```  
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroup*  
 Animasyonunu başlamak için bir animasyon grubu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu çağrı için ilgili CWnd yönlendirilir ve belirtilen grup için animasyon başlatılmadan önce ek eylemleri gerçekleştirmek için türetilen bir sınıfta geçersiz kılınabilir.  
  
##  <a name="onhasprioritycancel"></a>  CAnimationController::OnHasPriorityCancel  
 Zamanlama çakışmaları çözümlemek için framework tarafından çağırılır.  
  
```  
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroupScheduled*  
 Şu anda zamanlanmış film şeridi sahibi olan grup.  
  
 *pGroupNew*  
 Sahip olan yeni bir film şeridi pGroupScheduled tarafından sahip olunan zamanlanmış görsel taslak çakışma planlamada gruptur.  
  
 *priorityEffect*  
 PGroupScheduled daha yüksek bir önceliğe sahipse pGroupNew potansiyel etkisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görsel taslak pGroupNew tarafından sahip olunan önceliği ise TRUE döndürmelidir. Görsel taslak pGroupScheduled tarafından sahip olunan önceliğine sahip değilse FALSE döndürmelidir.  
  
### <a name="remarks"></a>Açıklamalar  
 CAnimationController::EnablePriorityComparisonHandler kullanarak öncelik karşılaştırma olayları etkinleştirmektedir ve UI_ANIMATION_PHT_CANCEL'ı belirtirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir. Çakışma yönetimi hakkında daha fazla bilgi için Windows animasyon API'sı okuma belgeleri (https://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhasprioritycompress"></a>  CAnimationController::OnHasPriorityCompress  
 Zamanlama çakışmaları çözümlemek için framework tarafından çağırılır.  
  
```  
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroupScheduled*  
 Şu anda zamanlanmış film şeridi sahibi olan grup.  
  
 *pGroupNew*  
 Sahip olan yeni bir film şeridi pGroupScheduled tarafından sahip olunan zamanlanmış görsel taslak çakışma planlamada gruptur.  
  
 *priorityEffect*  
 PGroupScheduled daha yüksek bir önceliğe sahipse pGroupNew potansiyel etkisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görsel taslak pGroupNew tarafından sahip olunan önceliği ise TRUE döndürmelidir. Görsel taslak pGroupScheduled tarafından sahip olunan önceliğine sahip değilse FALSE döndürmelidir.  
  
### <a name="remarks"></a>Açıklamalar  
 CAnimationController::EnablePriorityComparisonHandler kullanarak öncelik karşılaştırma olayları etkinleştirmektedir ve UI_ANIMATION_PHT_COMPRESS'ı belirtirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir. Çakışma yönetimi hakkında daha fazla bilgi için Windows animasyon API'sı okuma belgeleri (https://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhaspriorityconclude"></a>  CAnimationController::OnHasPriorityConclude  
 Zamanlama çakışmaları çözümlemek için framework tarafından çağırılır.  
  
```  
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroupScheduled*  
 Şu anda zamanlanmış film şeridi sahibi olan grup.  
  
 *pGroupNew*  
 Sahip olan yeni bir film şeridi pGroupScheduled tarafından sahip olunan zamanlanmış görsel taslak çakışma planlamada gruptur.  
  
 *priorityEffect*  
 PGroupScheduled daha yüksek bir önceliğe sahipse pGroupNew potansiyel etkisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görsel taslak pGroupNew tarafından sahip olunan önceliği ise TRUE döndürmelidir. Görsel taslak pGroupScheduled tarafından sahip olunan önceliğine sahip değilse FALSE döndürmelidir.  
  
### <a name="remarks"></a>Açıklamalar  
 CAnimationController::EnablePriorityComparisonHandler kullanarak öncelik karşılaştırma olayları etkinleştirmektedir ve UI_ANIMATION_PHT_CONCLUDE'ı belirtirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir. Çakışma yönetimi hakkında daha fazla bilgi için Windows animasyon API'sı okuma belgeleri (https://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhasprioritytrim"></a>  CAnimationController::OnHasPriorityTrim  
 Zamanlama çakışmaları çözümlemek için framework tarafından çağırılır.  
  
```  
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroupScheduled*  
 Şu anda zamanlanmış film şeridi sahibi olan grup.  
  
 *pGroupNew*  
 Sahip olan yeni bir film şeridi pGroupScheduled tarafından sahip olunan zamanlanmış görsel taslak çakışma planlamada gruptur.  
  
 *priorityEffect*  
 PGroupScheduled daha yüksek bir önceliğe sahipse pGroupNew potansiyel etkisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görsel taslak pGroupNew tarafından sahip olunan önceliği ise TRUE döndürmelidir. Görsel taslak pGroupScheduled tarafından sahip olunan önceliğine sahip değilse FALSE döndürmelidir.  
  
### <a name="remarks"></a>Açıklamalar  
 CAnimationController::EnablePriorityComparisonHandler kullanarak öncelik karşılaştırma olayları etkinleştirmektedir ve UI_ANIMATION_PHT_TRIM'ı belirtirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir. Çakışma yönetimi hakkında daha fazla bilgi için Windows animasyon API'sı okuma belgeleri (https://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onstoryboardstatuschanged"></a>  CAnimationController::OnStoryboardStatusChanged  
 Görsel taslak durumu değiştiğinde framework tarafından çağırılır.  
  
```  
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,  
    UI_ANIMATION_STORYBOARD_STATUS newStatus,  
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroup*  
 Görsel taslak durumu sahip olduğu bir animasyon grubu için bir işaretçi değişti.  
  
 *newStatus*  
 Yeni durumu belirtir.  
  
 *previousStatus*  
 Önceki durumunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Görsel taslak olayları CAnimationController::EnableStoryboardEventHandler kullanarak etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir.  
  
##  <a name="onstoryboardupdated"></a>  CAnimationController::OnStoryboardUpdated  
 Görsel taslak güncellendiğinde framework tarafından çağırılır.  
  
```  
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroup*  
 Görsel taslak sahip bir grup için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Görsel taslak olayları CAnimationController::EnableStoryboardEventHandler kullanarak etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılabilir.  
  
##  <a name="removeallanimationgroups"></a>  CAnimationController::RemoveAllAnimationGroups  
 Tüm animasyon grupları animasyon denetleyicisinden kaldırır.  
  
```  
void RemoveAllAnimationGroups();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm grupları olacaktır silinmiş, işaretçi uygulama düzeyinde depolanırsa geçersiz kılınabilir olmalıdır. Silinen bir grup için CAnimationGroup::m_bAutodestroyAnimationObjects TRUE ise, o gruba ait tüm animasyon nesneleri silinir; Aksi halde üst animasyon denetleyicisine başvurularını NULL olarak ayarlanır ve başka bir denetleyiciye eklenebilir.  
  
##  <a name="removeanimationgroup"></a>  CAnimationController::RemoveAnimationGroup  
 Belirtilen Kimliğe sahip bir animasyon grubu animasyon denetleyicisinden kaldırır.  
  
```  
void RemoveAnimationGroup(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Animasyon Grup kimliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem iç gruplar listesinden bir animasyon grubunu kaldırır ve siler, bu nedenle bu animasyonu gruba bir işaretçi depolanırsa, bu geçersiz kılınabilir olmalıdır. CAnimationGroup::m_bAutodestroyAnimationObjects TRUE ise, o gruba ait tüm animasyon nesneleri silinir; Aksi halde üst animasyon denetleyicisine başvurularını NULL olarak ayarlanır ve başka bir denetleyiciye eklenebilir.  
  
##  <a name="removeanimationobject"></a>  CAnimationController::RemoveAnimationObject  
 Bir animasyon nesne animasyon denetleyicisinden kaldırın.  
  
```  
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,  
    BOOL bNoDelete = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 *pObject*  
 Bir animasyon nesnesine bir işaretçi.  
  
 *bNoDelete*  
 Bu parametre TRUE ise, nesne kaldırmayı silinmez.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir animasyon nesne animasyon denetleyicisini ve animasyon grubunu kaldırır. Belirli bir nesnenin artık animasyonu değil veya başka bir animasyon denetleyicisini nesneyi taşımak gerekiyorsa, bu işlevi çağırın. Son durum bNoDelete TRUE olması gerekir.  
  
##  <a name="removetransitions"></a>  CAnimationController::RemoveTransitions  
 Belirtilen gruba ait animasyon nesneleri geçişleri kaldırır.  
  
```  
void RemoveTransitions(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Grup kimliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Grup, animasyon nesnelerini döngü ve her bir animasyon nesne için ClearTransitions(FALSE) çağırır. Animasyon zamanlandıktan sonra bu yöntem framework tarafından çağırılır.  
  
##  <a name="schedulegroup"></a>  CAnimationController::ScheduleGroup  
 Bir animasyon zamanlar.  
  
```  
BOOL ScheduleGroup(
    UINT32 nGroupID,  
    UI_ANIMATION_SECONDS time = 0.0);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Animasyon zamanlama grubu kimliği belirtir.  
  
 *saat*  
 Zamanlama süresini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon başarıyla zamanlandı TRUE. FALSE film şeridi oluşturulmadı veya başka bir hata oluşur.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre bScheduleNow ayarlamak için FALSE önceki ScheduleGroup ile AnimateGroup çağırmanız gerekir. İstenen animasyon zaman IUIAnimationTimer::GetTime alınan belirtebilirsiniz. Süre parametresini 0.0 ise, animasyon geçerli saati için zamanlanır.  
  
##  <a name="setrelatedwnd"></a>  CAnimationController::SetRelatedWnd  
 Animasyon denetleyicisini ve bir pencere arasında bir ilişki kurar.  
  
```  
void SetRelatedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Ayarlanacak pencere nesnesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir ilgili CWnd nesnesine ayarlarsanız, animasyon denetleyicisini otomatik olarak güncelleştirebilir (WM_PAINT iletisini Gönder) ne zaman animasyon yöneticisinin durumu değiştirildi veya Zamanlayıcı post güncelleştirme olayı oluştu.  
  
##  <a name="updateanimationmanager"></a>  CAnimationController::UpdateAnimationManager  
 Tüm animasyon değişkenlerin değerleri güncelleştirmek için animasyon Yöneticisi yönlendirir.  
  
```  
virtual void UpdateAnimationManager();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem geçerli zamanı animasyon yöneticiye ilerler arama, gerektiği şekilde film şeritleri durumlarını değiştirme ve herhangi bir animasyon değişkenini uygun güncelleştirme değerleri ilişkilendirilmiş. Dahili olarak IUIAnimationTimer::GetTime(timeNow) ve IUIAnimationManager::Update(timeNow) bu yöntemi çağırır. Türetilen bir sınıfta bu davranışını özelleştirmek için bu yöntemi yok sayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
