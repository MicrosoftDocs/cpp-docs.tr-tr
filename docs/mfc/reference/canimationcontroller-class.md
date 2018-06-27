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
ms.openlocfilehash: b91acd3537477e4213ea87dec77a97822b9e3d98
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955121"
---
# <a name="canimationcontroller-class"></a>CAnimationController sınıfı
Oluşturma ve animasyonları yönetmek için merkezi bir arabirim sağlar animasyon denetleyicisi uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimationController : public CObject;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationController::CAnimationController](#canimationcontroller)|Bir animasyon denetleyicisi oluşturur.|  
|[CAnimationController:: ~ CAnimationController](#canimationcontroller__~canimationcontroller)|Yok Edicisi. Animasyon denetleyicisi nesnesi yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationController::AddAnimationObject](#addanimationobject)|Animasyon denetleyiciye ait bir gruba bir animasyon nesnesi ekler.|  
|[CAnimationController::AddKeyframeToGroup](#addkeyframetogroup)|Bir ana kare grubuna ekler.|  
|[CAnimationController::AnimateGroup](#animategroup)|Animasyon çalıştırmak için bir grup hazırlar ve isteğe bağlı olarak zamanlar.|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Fazla Yüklendi. Animasyon zamanlandığı grubu oluşturan temizlemeye çerçevesi tarafından çağrılır.|  
|[CAnimationController::CreateKeyframe](#createkeyframe)|Fazla Yüklendi. Geçişi bağlıdır ve belirtilen gruba ekleyen bir anahtar kare oluşturur.|  
|[CAnimationController::EnableAnimationManagerEvent](#enableanimationmanagerevent)|Animasyon Yöneticisi'nin durumu değiştiğinde çağırmak için bir işleyici serbest veya ayarlar.|  
|[CAnimationController::EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|Ayarlar veya zamanlama olayları için bir işleyici ve güncelleştirmeleri zamanlama için işleyici serbest bırakır.|  
|[CAnimationController::EnablePriorityComparisonHandler](#enableprioritycomparisonhandler)|Ayarlar veya zamanlanmış film şeridi iptal edildi, sonuçları, kırpılmış sıkıştırılmış veya kaldırılabilir olup olmadığını belirlemek için çağrısı yapmak için öncelik karşılaştırma işleyicisi serbest bırakır.|  
|[CAnimationController::EnableStoryboardEventHandler](#enablestoryboardeventhandler)|Ayarlar veya film şeridi durumunu ve güncelleştirme olaylar için bir işleyici serbest bırakır.|  
|[CAnimationController::FindAnimationGroup](#findanimationgroup)|Fazla Yüklendi. Bir animasyon grubu şeridini göre bulur.|  
|[CAnimationController::FindAnimationObject](#findanimationobject)|Belirtilen animasyon değişkenini içeren animasyon nesnesi bulur.|  
|[CAnimationController::GetKeyframeStoryboardStart](#getkeyframestoryboardstart)|Film şeridi başlangıcı tanımlayan bir anahtar kare döndürür.|  
|[CAnimationController::GetUIAnimationManager](#getuianimationmanager)|Kapsüllenmiş IUIAnimationManager nesnesine erişim sağlar.|  
|[CAnimationController::GetUIAnimationTimer](#getuianimationtimer)|Kapsüllenmiş IUIAnimationTimer nesnesine erişim sağlar.|  
|[CAnimationController::GetUITransitionFactory](#getuitransitionfactory)|Bir işaretçi IUIAnimationTransitionFactory arabirimi veya geçiş kitaplığı oluşturulmasını başarısız olursa NULL.|  
|[CAnimationController::GetUITransitionLibrary](#getuitransitionlibrary)|Kapsüllenmiş IUIAnimationTransitionLibrary nesnesine erişim sağlar.|  
|[CAnimationController::IsAnimationInProgress](#isanimationinprogress)|En az bir grup animasyon yürütmeyi olup olmadığını bildirir.|  
|[CAnimationController::IsValid](#isvalid)|Animasyon denetleyicisi geçerli olup olmadığını bildirir.|  
|[CAnimationController::OnAnimationIntegerValueChanged](#onanimationintegervaluechanged)|Animasyon değişkenin tamsayı değeri değiştiğinde çerçevesi tarafından çağrılır.|  
|[CAnimationController::OnAnimationManagerStatusChanged](#onanimationmanagerstatuschanged)|Olaya yanıt olarak StatusChanged animasyon Yöneticisi'nden çerçevesi tarafından çağrılır.|  
|[CAnimationController::OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|Bir animasyon Güncelleştirme tamamlandıktan sonra çerçevesi tarafından çağrılır.|  
|[CAnimationController::OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|Bir animasyon güncelleştirme başlamadan önce çerçevesi tarafından çağrılır.|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](#onanimationtimerrenderingtooslow)|Bir animasyon işleme çerçeve oranı minimum arzu kare hızının altına düştüğünde çerçevesi tarafından çağrılır.|  
|[CAnimationController::OnAnimationValueChanged](#onanimationvaluechanged)|Animasyon değişkeninin değeri değiştiğinde çerçevesi tarafından çağrılır.|  
|[CAnimationController::OnBeforeAnimationStart](#onbeforeanimationstart)|Animasyonun zamanlanmadan önce çerçevesi tarafından sağ çağrılır.|  
|[CAnimationController::OnHasPriorityCancel](#onhasprioritycancel)|Zamanlama çakışmalarını çözmek için çerçevesi tarafından çağrılır.|  
|[CAnimationController::OnHasPriorityCompress](#onhasprioritycompress)|Zamanlama çakışmalarını çözmek için çerçevesi tarafından çağrılır.|  
|[CAnimationController::OnHasPriorityConclude](#onhaspriorityconclude)|Zamanlama çakışmalarını çözmek için çerçevesi tarafından çağrılır.|  
|[CAnimationController::OnHasPriorityTrim](#onhasprioritytrim)|Zamanlama çakışmalarını çözmek için çerçevesi tarafından çağrılır.|  
|[CAnimationController::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Film şeridi durumu değiştiğinde çerçevesi tarafından çağrılır.|  
|[CAnimationController::OnStoryboardUpdated](#onstoryboardupdated)|Film şeridi güncelleştirildiği çerçevesi tarafından çağrılır.|  
|[CAnimationController::RemoveAllAnimationGroups](#removeallanimationgroups)|Tüm animasyon grupları animasyon denetleyicisinden kaldırır.|  
|[CAnimationController::RemoveAnimationGroup](#removeanimationgroup)|Belirtilen Kimliğe sahip bir animasyon grubu animasyon denetleyicisinden kaldırır.|  
|[CAnimationController::RemoveAnimationObject](#removeanimationobject)|Bir animasyon nesne animasyon denetleyicisinden kaldırın.|  
|[CAnimationController::RemoveTransitions](#removetransitions)|Belirtilen gruba ait animasyon nesneleri geçişleri kaldırır.|  
|[CAnimationController::ScheduleGroup](#schedulegroup)|Bir animasyon zamanlar.|  
|[CAnimationController::SetRelatedWnd](#setrelatedwnd)|Animasyon denetleyicisi ve bir pencere arasında bir ilişki kurar.|  
|[CAnimationController::UpdateAnimationManager](#updateanimationmanager)|Tüm animasyon değişkenlerin değerleri güncelleştirmek için animasyon Yöneticisi yönlendirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|Fazla Yüklendi. Grubu oluşturan temizler Yardımcısı.|  
|[CAnimationController::OnAfterSchedule](#onafterschedule)|Belirtilen grup için bir animasyon yalnızca zamanlandığı çerçevesi tarafından çağrılır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationController::gkeyframeStoryboardStart](#g_keyframestoryboardstart)|Film şeridi başlangıcı temsil eden bir anahtar kare.|  
|[CAnimationController::m_bIsValid](#m_bisvalid)|Bir animasyon denetleyicisi geçerli olup olmadığını belirtir. Geçerli işletim Sisteminin Windows animasyon API desteklemiyorsa, bu üye FALSE olarak ayarlanır.|  
|[CAnimationController::m_lstAnimationGroups](#m_lstanimationgroups)|Bu animasyon denetleyiciye ait animasyon gruplarının listesi.|  
|[CAnimationController::m_pAnimationManager](#m_panimationmanager)|Animasyon Yöneticisi COM nesnesi için bir işaretçi depolar.|  
|[CAnimationController::m_pAnimationTimer](#m_panimationtimer)|Animasyon Zamanlayıcı COM nesnesi için bir işaretçi depolar.|  
|[CAnimationController::m_pRelatedWnd](#m_prelatedwnd)|Otomatik olarak animasyon Yöneticisi durum değiştirildi ya da post güncelleştirme olay oluştu çizilebilir ilgili bir CWnd nesnesine bir işaretçi. NULL olabilir.|  
|[CAnimationController::m_pTransitionFactory](#m_ptransitionfactory)|Geçiş Fabrika COM nesnesi için bir işaretçi depolar.|  
|[CAnimationController::m_pTransitionLibrary](#m_ptransitionlibrary)|Geçiş kitaplığı COM nesnesi için bir işaretçi depolar.|  
  
## <a name="remarks"></a>Açıklamalar  
 CAnimationController sınıfı animasyonları yöneten anahtar sınıftır. Animasyon denetleyicisi bir veya daha fazla örneğini bir uygulamada oluşturabilir ve, isteğe bağlı olarak, animasyon denetleyici örneği CAnimationController::SetRelatedWnd kullanarak CWnd nesnesine bağlanın. Bu bağlantı WM_PAINT iletileri ilgili penceresine otomatik olarak animasyon Yöneticisi durumu değişti veya animasyon Zamanlayıcı güncelleştirildiğinde göndermek için gereklidir. Bu ilişki etkinleştirmezseniz, elle bir animasyon görüntüleyen bir pencere yeniden boyutlandırmaya gerekir. Bu amaçla CAnimationController bir sınıf türetin ve OnAnimationManagerStatusChanged ve/veya OnAnimationTimerPostUpdate geçersiz kılabilir ve gerektiğinde bir veya daha fazla windows geçersiz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationController`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationcontroller"></a>  CAnimationController:: ~ CAnimationController  
 Yok Edicisi. Animasyon denetleyicisi nesnesi yok çağrılır.  
  
```  
virtual ~CAnimationController(void);
```   
  
##  <a name="addanimationobject"></a>  CAnimationController::AddAnimationObject  
 Animasyon denetleyiciye ait bir gruba bir animasyon nesnesi ekler.  
  
```  
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```  
  
### <a name="parameters"></a>Parametreler  
 *pObject*  
 Bir animasyon nesne için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi işlevi başarılı olursa nerede pObject eklenmiş olan mevcut veya yeni animasyon grubuna; PObject zaten başka bir animasyon denetleyiciye ait bir gruba eklenmiş yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon denetleyiciye animasyon nesne eklemek için bu yöntemi çağırın. Bir nesne, nesnenin GroupID göre bir gruba eklenir (CAnimationBaseObject::SetID bakın). İle belirtilen GroupID eklenmekte olan ilk nesne ise animasyon denetleyicisi yeni bir grup oluşturun. Bir animasyon nesne yalnızca bir animasyon denetleyiciye eklenebilir. Bir nesne başka bir denetleyiciye eklemeniz gerekiyorsa, RemoveAnimationObject çağırın. Bir gruba zaten eklenmiş bir nesne için yeni GroupID ile SetID çağırırsanız, nesne eski grubundan kaldırıldı ve belirtilen kimliğe sahip başka bir gruba eklenen  
  
##  <a name="addkeyframetogroup"></a>  CAnimationController::AddKeyframeToGroup  
 Bir ana kare grubuna ekler.  
  
```  
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,  
    CBaseKeyFrame* pKeyframe);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Grup kimliğini belirtir.  
  
 *pKeyframe*  
 Bir ana kare bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, bu yöntemi çağırabilmeniz için CAnimationController::CreateKeyframe bunun yerine, kullanın oluşturur ve oluşturulan ana kareyi otomatik olarak bir gruba ekler gerek yoktur.  
  
##  <a name="animategroup"></a>  CAnimationController::AnimateGroup  
 Animasyon çalıştırmak için bir grup hazırlar ve isteğe bağlı olarak zamanlar.  
  
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
 TRUE animasyon başarılı bir şekilde zamanlanır ve çalıştırın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem film şeridi oluşturarak, animasyon değişkenleri ekleme, geçişleri uygulama ve ana kare ayarlayarak asıl işi yapar. BScheduleNow FALSE olarak ayarlarsanız zamanlama gecikme mümkündür. Bu durumda belirtilen grup için animasyon ayarlanmış bir film şeridi tutar. Bu noktada film şeridi ve animasyon değişkenlerinin olayları ayarlayabilirsiniz. Ne zaman, aslında animasyon çağrısı CAnimationController::ScheduleGroup çalıştırmanız gerekir.  
  
##  <a name="canimationcontroller"></a>  CAnimationController::CAnimationController  
 Bir animasyon denetleyicisi oluşturur.  
  
```  
CAnimationController(void);
```   
  
##  <a name="cleanupgroup"></a>  CAnimationController::CleanUpGroup  
 Animasyon zamanlandığı grubu oluşturan temizlemeye çerçevesi tarafından çağrılır.  
  
```  
void CleanUpGroup(UINT32 nGroupID);  
void CleanUpGroup(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 GroupID belirtir.  
  
 *pGroup*  
 Animasyon Grup temizlemek için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir animasyon zamanlanmış sonra ilgili değildir çünkü bu yöntem, tüm geçişler ve ana kare belirtilen gruptan kaldırır.  
  
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
 Grup için ana kare oluşturulduğu Kimliğini belirtir.  
  
 *pTransition*  
 Geçiş için bir işaretçi. Bu geçişten sonra film şeridi için ana kare eklenir.  
  
 *pKeyframe*  
 Bu ana kare için temel ana kareyi gösteren bir işaretçi.  
  
 *uzaklık*  
 PKeyframe tarafından belirtilen temel kareyi gelen saniye cinsinden uzaklık.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olursa yeni oluşturulan ana kare bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen işaretçi depolamak ve diğer ana kare üzerinde yeni oluşturulan kareyi temel (ikinci aşırı bakın). Geçişleri durdurursunuz başlamak - CBaseTransition::SetKeyframes bkz mümkündür. Animasyon grupları tarafından otomatik olarak silindiği için bu yolla oluşturulan ana kareleri silme gerek yoktur. Diğer ana kare ve geçişleri göre ana kare oluştururken dikkatli olun ve döngüsel başvurulara kaçının.  
  
##  <a name="enableanimationmanagerevent"></a>  CAnimationController::EnableAnimationManagerEvent  
 Animasyon Yöneticisi'nin durumu değiştiğinde çağırmak için bir işleyici serbest veya ayarlar.  
  
```  
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bSistemlerde*  
 Ayarlayın veya bir işleyici serbest belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleyicinin başarılı bir şekilde ayarlamak veya yayımlanan TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleyici (etkin) olarak ayarlandığında animasyon Yöneticisi'nin durumu değiştiğinde Windows animasyon OnAnimationManagerStatusChanged çağırır.  
  
##  <a name="enableanimationtimereventhandler"></a>  CAnimationController::EnableAnimationTimerEventHandler  
 Ayarlar veya zamanlama olayları için bir işleyici ve güncelleştirmeleri zamanlama için işleyici serbest bırakır.  
  
```  
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,  
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bSistemlerde*  
 Ayarlanamadı veya serbest işleyicileri belirtir.  
  
 *idleBehavior*  
 Zamanlayıcı güncelleştirme işleyicisi için boşta davranışını belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleyicileri başarılı bir şekilde ayarlamak veya yayımlanan TRUE; YANLIŞ bu yöntemi işleyiciler ilk bırakmadan ikinci bir kez çağrılır veya diğer hata oluşur.  
  
### <a name="remarks"></a>Açıklamalar  
 Ne zaman işleyicileri (etkin) Windows animasyon API çağrıları OnAnimationTimerPreUpdate, OnAnimationTimerPostUpdate, OnRenderingTooSlow yöntemleri ayarlanır. Animasyon zamanlayıcılar Windows animasyon API güncelleştirme film şeritleri izin vermek etkinleştirmeniz gerekir. Aksi takdirde tüm animasyon değişkenlerin değerleri güncelleştirmek için Yöneticisi animasyonun yönlendirmek için CAnimationController::UpdateAnimationManager çağırmak gerekir.  
  
##  <a name="enableprioritycomparisonhandler"></a>  CAnimationController::EnablePriorityComparisonHandler  
 Ayarlar veya zamanlanmış film şeridi iptal edildi, sonuçları, kırpılmış sıkıştırılmış veya kaldırılabilir olup olmadığını belirlemek için çağrısı yapmak için öncelik karşılaştırma işleyicisi serbest bırakır.  
  
```  
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwHandlerType*  
 UI_ANIMATION_PHT_ birleşimi (açıklamalar bakın), ayarlanamadı veya serbest hangi işleyicileri belirten işaretler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleyicinin başarılı bir şekilde ayarlamak veya yayımlanan TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleyici (etkin) olarak ayarlandığında Windows animasyon dwHandlerType bağlı olarak aşağıdaki sanal yöntemler çağırır: OnHasPriorityCancel, OnHasPriorityConclude, OnHasPriorityTrim, OnHasPriorityCompress. dwHandler aşağıdaki bayraklar birleşimi olabilir: UI_ANIMATION_PHT_NONE - sürüm tüm işleyiciler UI_ANIMATION_PHT_CANCEL - ayarlamak iptal karşılaştırma işleyici UI_ANIMATION_PHT_CONCLUDE - küme Conclude karşılaştırma işleyici UI_ANIMATION_PHT_COMPRESS - ayarlayın Sıkıştırma karşılaştırma işleyici - kümesi kırpma karşılaştırma işleyicisi UI_ANIMATION_PHT_CANCEL_REMOVE - iptal karşılaştırma işleyici UI_ANIMATION_PHT_CONCLUDE_REMOVE Kaldır - UI_ANIMATION_PHT_TRIM Conclude karşılaştırma işleyici UI_ANIMATION_PHT_COMPRESS_ Kaldır REMOVE - sıkıştırma karşılaştırma işleyici UI_ANIMATION_PHT_TRIM_REMOVE - Kaldır kırpma karşılaştırma işleyici Kaldır  
  
##  <a name="enablestoryboardeventhandler"></a>  CAnimationController::EnableStoryboardEventHandler  
 Ayarlar veya film şeridi durumunu ve güncelleştirme olaylar için bir işleyici serbest bırakır.  
  
```  
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Grup kimliğini belirtir.  
  
 *bSistemlerde*  
 Ayarlayın veya bir işleyici serbest belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleyicinin başarılı bir şekilde ayarlamak veya yayımlanan TRUE; Belirtilen animasyon Grup şimdi bulunamadı veya belirtilen grup için animasyon başlatılmaz ve iç şeridini NULL ise FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işleyici olarak ayarlandığında (etkin) Windows animasyon API OnStoryboardStatusChanges ve OnStoryboardUpdated sanal yöntemleri çağırır. Belirtilen animasyon grubu için CAnimationController::Animate çağrıldıktan sonra kapsüllenmiş IUIAnimationStoryboard nesne oluşturduğundan bir işleyici ayarlamanız gerekir.  
  
##  <a name="findanimationgroup"></a>  CAnimationController::FindAnimationGroup  
 Bir animasyon grupla Grup Kimliği bulur  
  
```  
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);  
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Bir GroupID belirtir.  
  
 *pStoryboard*  
 Film şeridi gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi animasyon Grup ya da belirtilen Kimliğe sahip grup bulunmazsa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanında bir animasyon grubunu bulmak için bu yöntemi kullanın. Bir grup oluşturulur ve belirli GroupID ilk animasyon nesnesiyle animasyon denetleyiciye eklendiğinde animasyon grupları iç listesine eklenir.  
  
##  <a name="findanimationobject"></a>  CAnimationController::FindAnimationObject  
 Belirtilen animasyon değişkenini içeren animasyon nesnesi bulur.  
  
```  
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,  
    CAnimationBaseObject** ppObject,  
    CAnimationGroup** ppGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 *pVariable*  
 Animasyon değişkeni için bir işaretçi.  
  
 *ppObject*  
 Çıktı. Animasyon nesne ya da NULL bir işaretçi içeriyor.  
  
 *ppGroup*  
 Çıktı. Animasyon nesne ya da NULL tutan animasyon grup için bir işaretçi içeriyor.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne bulunduysa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon nesneden gelen animasyon değişkeni bulmak için gerekli olan olay işleyicilerini çağrılır.  
  
##  <a name="g_keyframestoryboardstart"></a>  CAnimationController::gkeyframeStoryboardStart  
 Film şeridi başlangıcı temsil eden bir anahtar kare.  
  
```  
static CBaseKeyFrame gkeyframeStoryboardStart;  
```  
  
##  <a name="getkeyframestoryboardstart"></a>  CAnimationController::GetKeyframeStoryboardStart  
 Film şeridi başlangıcı tanımlayan bir anahtar kare döndürür.  
  
```  
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Film şeridi başlangıcı tanımlayan temel ana kare bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ana kare film şeridi başladığı zaman birazdan herhangi bir ana kare veya geçişleri temel alın.  
  
##  <a name="getuianimationmanager"></a>  CAnimationController::GetUIAnimationManager  
 Kapsüllenmiş IUIAnimationManager nesnesine erişim sağlar.  
  
```  
IUIAnimationManager* GetUIAnimationManager();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi IUIAnimationManager arabirimi veya animasyon Yöneticisi oluşturma başarısız olursa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli işletim Sisteminin Windows animasyon API desteklemiyorsa, bu yöntem NULL döndürür ve bundan sonra CAnimationController::IsValid üzerinde tüm sonraki çağrılar false değerini döndürür. Animasyon denetleyicisi tarafından Sarmalanan değil, arabirim yöntemleri çağırmak için IUIAnimationManager erişim gerekebilir.  
  
##  <a name="getuianimationtimer"></a>  CAnimationController::GetUIAnimationTimer  
 Kapsüllenmiş IUIAnimationTimer nesnesine erişim sağlar.  
  
```  
IUIAnimationTimer* GetUIAnimationTimer();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi IUIAnimationTimer arabirimi veya animasyon Zamanlayıcı oluşturma başarısız olursa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli işletim Sisteminin Windows animasyon API desteklemiyorsa, bu yöntem NULL döndürür ve bundan sonra CAnimationController::IsValid üzerinde tüm sonraki çağrılar false değerini döndürür.  
  
##  <a name="getuitransitionfactory"></a>  CAnimationController::GetUITransitionFactory  
 Bir işaretçi IUIAnimationTransitionFactory arabirimi veya geçiş kitaplığı oluşturulmasını başarısız olursa NULL.  
  
```  
IUIAnimationTransitionFactory* GetUITransitionFactory();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi IUIAnimationTransitionFactory veya geçiş Factory oluşturma başarısız olursa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli işletim Sisteminin Windows animasyon API desteklemiyorsa, bu yöntem NULL döndürür ve bundan sonra CAnimationController::IsValid üzerinde tüm sonraki çağrılar false değerini döndürür.  
  
##  <a name="getuitransitionlibrary"></a>  CAnimationController::GetUITransitionLibrary  
 Kapsüllenmiş IUIAnimationTransitionLibrary nesnesine erişim sağlar.  
  
```  
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi IUIAnimationTransitionLibrary arabirimi veya geçiş kitaplığı oluşturulmasını başarısız olursa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli işletim Sisteminin Windows animasyon API desteklemiyorsa, bu yöntem NULL döndürür ve bundan sonra CAnimationController::IsValid üzerinde tüm sonraki çağrılar false değerini döndürür.  
  
##  <a name="isanimationinprogress"></a>  CAnimationController::IsAnimationInProgress  
 En az bir grup animasyon yürütmeyi olup olmadığını bildirir.  
  
```  
virtual BOOL IsAnimationInProgress();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu animasyon denetleyici için devam eden bir animasyon ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon Yöneticisi durumunu denetler ve durum UI_ANIMATION_MANAGER_BUSY ise TRUE değerini döndürür.  
  
##  <a name="isvalid"></a>  CAnimationController::IsValid  
 Animasyon denetleyicisi geçerli olup olmadığını bildirir.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon denetleyicisi geçerli ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıtlı için bu yöntemi döndürür yalnızca Windows animasyon API geçerli işletim sistemi ve animasyon Yöneticisi oluşturulmasını desteklenmiyorsa FALSE başarısız oldu. En az bir kez bu bayrağın ayarını neden COM kitaplıkları başlatma GetUIAnimationManager çağırmanız gerekir.  
  
##  <a name="m_bisvalid"></a>  CAnimationController::m_bIsValid  
 Bir animasyon denetleyicisi geçerli olup olmadığını belirtir. Geçerli işletim Sisteminin Windows animasyon API desteklemiyorsa, bu üye FALSE olarak ayarlanır.  
  
```  
BOOL m_bIsValid;  
```  
  
##  <a name="m_lstanimationgroups"></a>  CAnimationController::m_lstAnimationGroups  
 Bu animasyon denetleyiciye ait animasyon gruplarının listesi.  
  
```  
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;  
```  
  
##  <a name="m_panimationmanager"></a>  CAnimationController::m_pAnimationManager  
 Animasyon Yöneticisi COM nesnesi için bir işaretçi depolar.  
  
```  
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;  
```  
  
##  <a name="m_panimationtimer"></a>  CAnimationController::m_pAnimationTimer  
 Animasyon Zamanlayıcı COM nesnesi için bir işaretçi depolar.  
  
```  
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;  
```  
  
##  <a name="m_prelatedwnd"></a>  CAnimationController::m_pRelatedWnd  
 Otomatik olarak animasyon Yöneticisi durum değiştirildi ya da post güncelleştirme olay oluştu çizilebilir ilgili bir CWnd nesnesine bir işaretçi. NULL olabilir.  
  
```  
CWnd* m_pRelatedWnd;  
```  
  
##  <a name="m_ptransitionfactory"></a>  CAnimationController::m_pTransitionFactory  
 Geçiş Fabrika COM nesnesi için bir işaretçi depolar.  
  
```  
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;  
```  
  
##  <a name="m_ptransitionlibrary"></a>  CAnimationController::m_pTransitionLibrary  
 Geçiş kitaplığı COM nesnesi için bir işaretçi depolar.  
  
```  
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;  
```  
  
##  <a name="onafterschedule"></a>  CAnimationController::OnAfterSchedule  
 Belirtilen grup için bir animasyon yalnızca zamanlandığı çerçevesi tarafından çağrılır.  
  
```  
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroup*  
 Zamanlanmış bir animasyon grubu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama ana kare belirtilen gruptan kaldırır ve belirtilen gruba ait animasyon değişkenlerden geçiş. Animasyon zamanlamaya bağlı tüm ek eylemleri uygulamak için bir türetilmiş sınıfta geçersiz kılınabilir.  
  
##  <a name="onanimationintegervaluechanged"></a>  CAnimationController::OnAnimationIntegerValueChanged  
 Animasyon değişkenin tamsayı değeri değiştiğinde çerçevesi tarafından çağrılır.  
  
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
 Bir animasyon nesne değerini tutan bir animasyon grubu için bir işaretçi değişti.  
  
 *pObject*  
 Bir işaretçi animasyon nesneye değeri değişti bir animasyon değişken içeriyor.  
  
 *Değişken*  
 Bir animasyon değişkeni için bir işaretçi.  
  
 *newValue*  
 Yeni değer belirtir.  
  
 *prevValue*  
 Önceki bir değer belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel Animasyon değişken veya animasyon nesne için adlı EnableIntegerValueChangedEvent ile animasyon değişken olayları etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir.  
  
##  <a name="onanimationmanagerstatuschanged"></a>  CAnimationController::OnAnimationManagerStatusChanged  
 Olaya yanıt olarak StatusChanged animasyon Yöneticisi'nden çerçevesi tarafından çağrılır.  
  
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
 Animasyon Yöneticisi olaylarını EnableAnimationManagerEvent ile etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir. Varsayılan uygulama ile SetRelatedWnd ayarlarsanız ilgili pencere güncelleştirir.  
  
##  <a name="onanimationtimerpostupdate"></a>  CAnimationController::OnAnimationTimerPostUpdate  
 Bir animasyon Güncelleştirme tamamlandıktan sonra çerçevesi tarafından çağrılır.  
  
```  
virtual void OnAnimationTimerPostUpdate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Zamanlayıcı olay işleyicileri EnableAnimationTimerEventHandler kullanarak etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir.  
  
##  <a name="onanimationtimerpreupdate"></a>  CAnimationController::OnAnimationTimerPreUpdate  
 Bir animasyon güncelleştirme başlamadan önce çerçevesi tarafından çağrılır.  
  
```  
virtual void OnAnimationTimerPreUpdate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Zamanlayıcı olay işleyicileri EnableAnimationTimerEventHandler kullanarak etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir.  
  
##  <a name="onanimationtimerrenderingtooslow"></a>  CAnimationController::OnAnimationTimerRenderingTooSlow  
 Bir animasyon işleme çerçeve oranı minimum arzu kare hızının altına düştüğünde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```  
  
### <a name="parameters"></a>Parametreler  
 *fps*  
 Saniyedeki çerçeve geçerli kare hızı.  
  
### <a name="remarks"></a>Açıklamalar  
 Zamanlayıcı olay işleyicileri EnableAnimationTimerEventHandler kullanarak etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir. Minimum arzu kare hızı IUIAnimationTimer::SetFrameRateThreshold çağırarak belirtilir.  
  
##  <a name="onanimationvaluechanged"></a>  CAnimationController::OnAnimationValueChanged  
 Animasyon değişkeninin değeri değiştiğinde çerçevesi tarafından çağrılır.  
  
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
 Bir animasyon nesne değerini tutan bir animasyon grubu için bir işaretçi değişti.  
  
 *pObject*  
 Bir işaretçi animasyon nesneye değeri değişti bir animasyon değişken içeriyor.  
  
 *Değişken*  
 Bir animasyon değişkeni için bir işaretçi.  
  
 *newValue*  
 Yeni değer belirtir.  
  
 *prevValue*  
 Önceki bir değer belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel Animasyon değişken veya animasyon nesne için adlı EnableValueChangedEvent ile animasyon değişken olayları etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir.  
  
##  <a name="onbeforeanimationstart"></a>  CAnimationController::OnBeforeAnimationStart  
 Animasyonun zamanlanmadan önce çerçevesi tarafından sağ çağrılır.  
  
```  
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroup*  
 Başlamak için animasyon olan bir animasyon grubu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu çağrı için ilgili CWnd yönlendirilir ve belirtilen grup için animasyon başlamadan önce ek eylemleri gerçekleştirmek için bir türetilmiş sınıfta geçersiz kılınabilir.  
  
##  <a name="onhasprioritycancel"></a>  CAnimationController::OnHasPriorityCancel  
 Zamanlama çakışmalarını çözmek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroupScheduled*  
 Şu anda zamanlanmış film şeridi sahip grup.  
  
 *pGroupNew*  
 Yeni film şeridi sahibi tarafından pGroupScheduled ait zamanlanmış film şeridi ile çakışma planlamada grubudur.  
  
 *priorityEffect*  
 PGroupScheduled daha yüksek öncelik varsa pGroupNew potansiyel etkisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Film şeridi tarafından pGroupNew ait öncelik varsa TRUE değerini döndürmelidir. Film şeridi pGroupScheduled tarafından sahip olunan önceliği ise FALSE değerini döndürmelidir.  
  
### <a name="remarks"></a>Açıklamalar  
 Öncelik karşılaştırma olayları CAnimationController::EnablePriorityComparisonHandler kullanarak etkinleştirin ve UI_ANIMATION_PHT_CANCEL belirtirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir. Windows animasyon API belgelerini okuma çakışma yönetimi hakkında daha fazla bilgi için (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhasprioritycompress"></a>  CAnimationController::OnHasPriorityCompress  
 Zamanlama çakışmalarını çözmek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroupScheduled*  
 Şu anda zamanlanmış film şeridi sahip grup.  
  
 *pGroupNew*  
 Yeni film şeridi sahibi tarafından pGroupScheduled ait zamanlanmış film şeridi ile çakışma planlamada grubudur.  
  
 *priorityEffect*  
 PGroupScheduled daha yüksek öncelik varsa pGroupNew potansiyel etkisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Film şeridi tarafından pGroupNew ait öncelik varsa TRUE değerini döndürmelidir. Film şeridi pGroupScheduled tarafından sahip olunan önceliği ise FALSE değerini döndürmelidir.  
  
### <a name="remarks"></a>Açıklamalar  
 Öncelik karşılaştırma olayları CAnimationController::EnablePriorityComparisonHandler kullanarak etkinleştirin ve UI_ANIMATION_PHT_COMPRESS belirtirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir. Windows animasyon API belgelerini okuma çakışma yönetimi hakkında daha fazla bilgi için (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhaspriorityconclude"></a>  CAnimationController::OnHasPriorityConclude  
 Zamanlama çakışmalarını çözmek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroupScheduled*  
 Şu anda zamanlanmış film şeridi sahip grup.  
  
 *pGroupNew*  
 Yeni film şeridi sahibi tarafından pGroupScheduled ait zamanlanmış film şeridi ile çakışma planlamada grubudur.  
  
 *priorityEffect*  
 PGroupScheduled daha yüksek öncelik varsa pGroupNew potansiyel etkisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Film şeridi tarafından pGroupNew ait öncelik varsa TRUE değerini döndürmelidir. Film şeridi pGroupScheduled tarafından sahip olunan önceliği ise FALSE değerini döndürmelidir.  
  
### <a name="remarks"></a>Açıklamalar  
 Öncelik karşılaştırma olayları CAnimationController::EnablePriorityComparisonHandler kullanarak etkinleştirin ve UI_ANIMATION_PHT_CONCLUDE belirtirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir. Windows animasyon API belgelerini okuma çakışma yönetimi hakkında daha fazla bilgi için (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onhasprioritytrim"></a>  CAnimationController::OnHasPriorityTrim  
 Zamanlama çakışmalarını çözmek için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroupScheduled*  
 Şu anda zamanlanmış film şeridi sahip grup.  
  
 *pGroupNew*  
 Yeni film şeridi sahibi tarafından pGroupScheduled ait zamanlanmış film şeridi ile çakışma planlamada grubudur.  
  
 *priorityEffect*  
 PGroupScheduled daha yüksek öncelik varsa pGroupNew potansiyel etkisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Film şeridi tarafından pGroupNew ait öncelik varsa TRUE değerini döndürmelidir. Film şeridi pGroupScheduled tarafından sahip olunan önceliği ise FALSE değerini döndürmelidir.  
  
### <a name="remarks"></a>Açıklamalar  
 Öncelik karşılaştırma olayları CAnimationController::EnablePriorityComparisonHandler kullanarak etkinleştirin ve UI_ANIMATION_PHT_TRIM belirtirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir. Windows animasyon API belgelerini okuma çakışma yönetimi hakkında daha fazla bilgi için (http://msdn.microsoft.com/library/dd371759(VS.85).aspx).  
  
##  <a name="onstoryboardstatuschanged"></a>  CAnimationController::OnStoryboardStatusChanged  
 Film şeridi durumu değiştiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,  
    UI_ANIMATION_STORYBOARD_STATUS newStatus,  
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroup*  
 Film şeridi durumu sahibi olan bir animasyon grubu için bir işaretçi değişti.  
  
 *newStatus*  
 Yeni durumu belirtir.  
  
 *previousStatus*  
 Önceki durumunu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 CAnimationController::EnableStoryboardEventHandler kullanarak film şeridi olayları etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir.  
  
##  <a name="onstoryboardupdated"></a>  CAnimationController::OnStoryboardUpdated  
 Film şeridi güncelleştirildiği çerçevesi tarafından çağrılır.  
  
```  
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 *pGroup*  
 Film şeridi sahip bir grup için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 CAnimationController::EnableStoryboardEventHandler kullanarak film şeridi olayları etkinleştirirseniz, bu yöntem çağrılır. Uygulamaya özgü eylemleri için türetilen bir sınıfta geçersiz kılınabilir.  
  
##  <a name="removeallanimationgroups"></a>  CAnimationController::RemoveAllAnimationGroups  
 Tüm animasyon grupları animasyon denetleyicisinden kaldırır.  
  
```  
void RemoveAllAnimationGroups();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm grupları olacaktır silinmiş, kendi işaretçi uygulama düzeyinde depoladıysanız geçersiz kılınan gerekir. Silinen bir grup için CAnimationGroup::m_bAutodestroyAnimationObjects TRUE ise, bu gruba ait tüm animasyon nesneler silinecek; Aksi takdirde başvurularını üst animasyon denetleyicisine NULL olarak ayarlanacak ve başka bir denetleyiciye eklenebilir.  
  
##  <a name="removeanimationgroup"></a>  CAnimationController::RemoveAnimationGroup  
 Belirtilen Kimliğe sahip bir animasyon grubu animasyon denetleyicisinden kaldırır.  
  
```  
void RemoveAnimationGroup(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Animasyon Grup kimliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir animasyon grubu grupları iç listeden kaldırır ve siler, bu nedenle bu animasyon grup için bir işaretçi depolanırsa, bu geçersiz kılınan gerekir. CAnimationGroup::m_bAutodestroyAnimationObjects TRUE ise, bu gruba ait tüm animasyon nesneler silinecek; Aksi takdirde başvurularını üst animasyon denetleyicisine NULL olarak ayarlanacak ve başka bir denetleyiciye eklenebilir.  
  
##  <a name="removeanimationobject"></a>  CAnimationController::RemoveAnimationObject  
 Bir animasyon nesne animasyon denetleyicisinden kaldırın.  
  
```  
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,  
    BOOL bNoDelete = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 *pObject*  
 Bir animasyon nesne için bir işaretçi.  
  
 *bNoDelete*  
 Bu parametre TRUE ise, nesne kaldırmayı silinmez.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir animasyon nesne animasyon denetleyicisi ve animasyon grup kaldırır. Belirli bir nesne artık animasyonlu yok veya nesne başka bir animasyon denetleyiciye taşımanız gerekirse, bu işlevini çağırın. Son servis talebi bNoDelete TRUE olması gerekir.  
  
##  <a name="removetransitions"></a>  CAnimationController::RemoveTransitions  
 Belirtilen gruba ait animasyon nesneleri geçişleri kaldırır.  
  
```  
void RemoveTransitions(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Grup kimliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Grup kendi animasyon nesneler üzerinde döngüler ve her bir animasyon nesne için ClearTransitions(FALSE) çağırır. Animasyon zamanlanmış sonra bu yöntem çerçevesi tarafından çağrılır.  
  
##  <a name="schedulegroup"></a>  CAnimationController::ScheduleGroup  
 Bir animasyon zamanlar.  
  
```  
BOOL ScheduleGroup(
    UINT32 nGroupID,  
    UI_ANIMATION_SECONDS time = 0.0);
```  
  
### <a name="parameters"></a>Parametreler  
 *nGroupID*  
 Animasyon zamanlamak için Grup Kimliği belirtir.  
  
 *Saat*  
 Zamanlamak için süreyi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon başarıyla zamanlandı TRUE. Film şeridi oluşturulmadı veya başka bir hata oluştuğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre bScheduleNow için FALSE önceki ScheduleGroup ayarlama ile AnimateGroup çağırmanız gerekir. İstenen animasyon süresi IUIAnimationTimer::GetTime alınan belirtebilirsiniz. Time parametresi 0,0 ise, animasyonun geçerli saati için zamanlanır.  
  
##  <a name="setrelatedwnd"></a>  CAnimationController::SetRelatedWnd  
 Animasyon denetleyicisi ve bir pencere arasında bir ilişki kurar.  
  
```  
void SetRelatedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Pencere nesnesi ayarlamak için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir ilişkili CWnd nesne ayarlarsanız, animasyon denetleyicisi otomatik olarak güncelleştirebilir (WM_PAINT ileti gönder) ne zaman animasyon Yöneticisi durum değiştirildi ya da Zamanlayıcı post güncelleştirme olayı oluştu.  
  
##  <a name="updateanimationmanager"></a>  CAnimationController::UpdateAnimationManager  
 Tüm animasyon değişkenlerin değerleri güncelleştirmek için animasyon Yöneticisi yönlendirir.  
  
```  
virtual void UpdateAnimationManager();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem geçerli saati animasyon yöneticiye ilerler arama, gerektiğinde film şeritleri durumlarını değiştirme ve herhangi bir animasyon değişkeni için uygun güncelleştirme değerleri Ara değerli. Dahili olarak IUIAnimationTimer::GetTime(timeNow) ve IUIAnimationManager::Update(timeNow) bu yöntemi çağırır. Bu davranış özelleştirmek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
