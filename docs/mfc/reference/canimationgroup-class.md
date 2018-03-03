---
title: "CAnimationGroup sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2d047940ac1ef3103168aa40b53c726ce0767b52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="canimationgroup-class"></a>CAnimationGroup sınıfı
Bir animasyon film şeridi, animasyon nesneler ve bir animasyon tanımlamak için geçişler birleştiren bir animasyon grubu uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimationGroup;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationGroup::CAnimationGroup](#canimationgroup)|Bir animasyon grubu oluşturur.|  
|[CAnimationGroup:: ~ CAnimationGroup](#canimationgroup__~canimationgroup)|Yok Edicisi. Bir animasyon grubu kaldırıldığı zaman çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationGroup::Animate](#animate)|Bir grup canlandırır.|  
|[CAnimationGroup::ApplyTransitions](#applytransitions)|Geçişleri animasyon nesnelere uygulanır.|  
|[CAnimationGroup::FindAnimationObject](#findanimationobject)|Belirtilen animasyon değişkeni içeren bir animasyon nesne bulur.|  
|[CAnimationGroup::GetGroupID](#getgroupid)|GroupID döndürür.|  
|[CAnimationGroup::RemoveKeyframes](#removekeyframes)|Kaldırır ve isteğe bağlı olarak bir animasyon gruba ait tüm anahtar kareleri yok eder.|  
|[CAnimationGroup::RemoveTransitions](#removetransitions)|Bir animasyon grubuna ait animasyon nesneleri geçişleri kaldırır.|  
|[CAnimationGroup::Schedule](#schedule)|Belirtilen zamanda bir animasyon zamanlar.|  
|[CAnimationGroup::SetAutodestroyTransitions](#setautodestroytransitions)|Otomatik olarak grubuna ait tüm animasyon nesneleri geçişleri yok yönlendirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationGroup::AddKeyframes](#addkeyframes)|Film şeridi için ana kare ekler Yardımcısı.|  
|[CAnimationGroup::AddTransitions](#addtransitions)|Geçişleri için film şeridi ekler Yardımcısı.|  
|[CAnimationGroup::CreateTransitions](#createtransitions)|COM geçiş nesneleri oluşturur Yardımcısı.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationGroup::m_bAutoclearTransitions](#m_bautocleartransitions)|Gruba ait animasyon nesneleri geçişler temizlemek nasıl belirtir. Bu üye TRUE ise, bir animasyon zamanlandığı geçişleri otomatik olarak kaldırılır. Aksi takdirde geçişleri el ile kaldırmanız gerekir.|  
|[CAnimationGroup::m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|Animasyon nesneleri yok etme belirtir. Bu parametre TRUE ise, grubun bozulduğunda animasyon nesneleri otomatik olarak yok edilir. Aksi takdirde animasyon nesneleri el ile yok edilmesi gerekir. Varsayılan değer FALSE olur. Bu değer yalnızca gruba ait tüm animasyon nesneleri işleci ile yeni dinamik olarak ayrılır varsa TRUE olarak ayarlayın.|  
|[CAnimationGroup::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|Ana kare yok etmek nasıl belirtir. Bu değeri TRUE ise, tüm ana kareleri kaldırılır ve yok; Aksi halde bunlar yalnızca listesinden kaldırılır. Varsayılan değer True'dur.|  
|[CAnimationGroup::m_lstAnimationObjects](#m_lstanimationobjects)|Animasyon nesnelerin bir listesini içerir.|  
|[CAnimationGroup::m_lstKeyFrames](#m_lstkeyframes)|Ana kare listesini içerir.|  
|[CAnimationGroup::m_pStoryboard](#m_pstoryboard)|Animasyon film şeridi noktalarına. Bu işaretçinin animasyon ekle çağrıda sonra yalnızca geçerli değil.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationGroup::m_nGroupID](#m_ngroupid)|Animasyon grubunun benzersiz tanımlayıcısı.|  
|[CAnimationGroup::m_pParentController](#m_pparentcontroller)|Bu grubun ait olduğu animasyon denetleyici için bir işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Animasyon nesneleri CAnimationController::AddAnimationObject kullanarak eklediğinizde animasyon grupları animasyon denetleyici (CAnimationController) tarafından otomatik olarak oluşturulur. Bir animasyon Grup animasyon grupları denetlemek için bir parametre olarak genellikle geçen GroupID tarafından tanımlanır. GroupID yeni bir animasyon grubuna eklenen ilk animasyon nesnesinden alınır. CAnimationController::AnimateGroup çağırın ve ortak üye m_pStoryboard erişilen sonra kapsüllenmiş animasyon film şeridi oluşturulur.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CAnimationGroup`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationgroup"></a>CAnimationGroup:: ~ CAnimationGroup  
 Yok Edicisi. Bir animasyon grubu kaldırıldığı zaman çağrılır.  
  
```  
~CAnimationGroup();
```  
  
##  <a name="addkeyframes"></a>CAnimationGroup::AddKeyframes  
 Film şeridi için ana kare ekler Yardımcısı.  
  
```  
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```  
  
### <a name="parameters"></a>Parametreler  
 `pStoryboard`  
 Film şeridi COM nesnesi için bir işaretçi.  
  
 `bAddDeep`  
 Bu yöntem diğer ana kare üzerinde bağımlı film şeridi ana kare eklemeniz gerekip gerekmediğini belirtir.  
  
##  <a name="addtransitions"></a>CAnimationGroup::AddTransitions  
 Geçişleri için film şeridi ekler Yardımcısı.  
  
```  
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Parametreler  
 `pStoryboard`  
 Film şeridi COM nesnesi için bir işaretçi.  
  
 `bDependOnKeyframes`  
  
##  <a name="animate"></a>CAnimationGroup::Animate  
 Bir grup canlandırır.  
  
```  
BOOL Animate(
    IUIAnimationManager* pManager,  
    IUIAnimationTimer* pTimer,  
    BOOL bScheduleNow);
```  
  
### <a name="parameters"></a>Parametreler  
 `pManager`  
 `pTimer`  
 `bScheduleNow`  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem iç film şeridi oluşturur, oluşturur ve geçişleri uygular ve bScheduleNow TRUE ise bir animasyon zamanlar. BScheduleNow FALSE ise, belirtilen zaman animasyonu başlatmak için zamanlama çağırması gerekir.  
  
##  <a name="applytransitions"></a>CAnimationGroup::ApplyTransitions  
 Geçişleri animasyon nesnelere uygulanır.  
  
```  
void ApplyTransitions();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, film şeridi oluşturulmadı, hata ayıklama modunda ONAYLAR. İlk olarak, tüm geçişleri oluşturur sonra "statik" ana kare (uzaklıkları üzerinde bağımlı ana kare) ekler, ana kare üzerinde dayanmayan geçişleri ekler, ana kare geçişleri bağlı olarak ve diğer ana kare ekler ve en son ana kare üzerinde bağımlı geçişleri ekler .  
  
##  <a name="canimationgroup"></a>CAnimationGroup::CAnimationGroup  
 Bir animasyon grubu oluşturur.  
  
```  
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentController`  
 Bir grup oluşturur animasyon denetleyici için bir işaretçi.  
  
 `nGroupID`  
 GroupID belirtir.  
  
##  <a name="createtransitions"></a>CAnimationGroup::CreateTransitions  
 COM geçiş nesneleri oluşturur Yardımcısı.  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 DOĞRU yöntem başarılı, aksi takdirde FALSE olur.  
  
##  <a name="findanimationobject"></a>CAnimationGroup::FindAnimationObject  
 Belirtilen animasyon değişkeni içeren bir animasyon nesne bulur.  
  
```  
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Parametreler  
 `pVariable`  
 Animasyon değişkeni için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon nesne ya da animasyon nesne bulunmazsa NULL işaretçi.  
  
##  <a name="getgroupid"></a>CAnimationGroup::GetGroupID  
 GroupID döndürür.  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir grup tanımlayıcısı.  
  
##  <a name="m_bautocleartransitions"></a>CAnimationGroup::m_bAutoclearTransitions  
 Gruba ait animasyon nesneleri geçişler temizlemek nasıl belirtir. Bu üye TRUE ise, bir animasyon zamanlandığı geçişleri otomatik olarak kaldırılır. Aksi takdirde geçişleri el ile kaldırmanız gerekir.  
  
```  
BOOL m_bAutoclearTransitions;  
```  
  
##  <a name="m_bautodestroyanimationobjects"></a>CAnimationGroup::m_bAutodestroyAnimationObjects  
 Animasyon nesneleri yok etme belirtir. Bu parametre TRUE ise, grubun bozulduğunda animasyon nesneleri otomatik olarak yok edilir. Aksi takdirde animasyon nesneleri el ile yok edilmesi gerekir. Varsayılan değer FALSE olur. Bu değer yalnızca gruba ait tüm animasyon nesneleri işleci ile yeni dinamik olarak ayrılır varsa TRUE olarak ayarlayın.  
  
```  
BOOL m_bAutodestroyAnimationObjects;  
```  
  
##  <a name="m_bautodestroykeyframes"></a>CAnimationGroup::m_bAutodestroyKeyframes  
 Ana kare yok etmek nasıl belirtir. Bu değeri TRUE ise, tüm ana kareleri kaldırılır ve yok; Aksi halde bunlar yalnızca listesinden kaldırılır. Varsayılan değer True'dur.  
  
```  
BOOL m_bAutodestroyKeyframes;  
```  
  
##  <a name="m_lstanimationobjects"></a>CAnimationGroup::m_lstAnimationObjects  
 Animasyon nesnelerin bir listesini içerir.  
  
```  
CObList m_lstAnimationObjects;  
```  
  
##  <a name="m_lstkeyframes"></a>CAnimationGroup::m_lstKeyFrames  
 Ana kare listesini içerir.  
  
```  
CObList m_lstKeyFrames;  
```  
  
##  <a name="m_ngroupid"></a>CAnimationGroup::m_nGroupID  
 Animasyon grubunun benzersiz tanımlayıcısı.  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_pparentcontroller"></a>CAnimationGroup::m_pParentController  
 Bu grubun ait olduğu animasyon denetleyici için bir işaretçi.  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="m_pstoryboard"></a>CAnimationGroup::m_pStoryboard  
 Animasyon film şeridi noktalarına. Bu işaretçinin animasyon ekle çağrıda sonra yalnızca geçerli değil.  
  
```  
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;  
```  
  
##  <a name="removekeyframes"></a>CAnimationGroup::RemoveKeyframes  
 Kaldırır ve isteğe bağlı olarak bir animasyon gruba ait tüm anahtar kareleri yok eder.  
  
```  
void RemoveKeyframes();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ana kare kaldırıldı ve yok etme, sonra m_bAutodestroyKeyframes üye TRUE ise, aksi takdirde ana kare ana kare iç listesinden hemen kaldırılır.  
  
##  <a name="removetransitions"></a>CAnimationGroup::RemoveTransitions  
 Bir animasyon grubuna ait animasyon nesneleri geçişleri kaldırır.  
  
```  
void RemoveTransitions();
```  
  
### <a name="remarks"></a>Açıklamalar  
 M_bAutoclearTransitions bayrağı TRUE olarak ayarlanırsa, bu yöntem gruba ait tüm animasyon nesneleri üzerinden döngü ve CAnimationObject::ClearTransitions(FALSE) çağırır.  
  
##  <a name="schedule"></a>CAnimationGroup::Schedule  
 Belirtilen zamanda bir animasyon zamanlar.  
  
```  
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```  
  
### <a name="parameters"></a>Parametreler  
 `pTimer`  
 Animasyon Zamanlayıcı için bir işaretçi.  
  
 `time`  
 Animasyonun zamanlamak için süreyi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa TRUE; FALSE yöntem başarısız olursa veya animasyon olarak oluşturmak, FALSE olarak ayarlanmış bScheduleNow ile çağrılmadı.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen zamanda bir animasyon zamanlamak için bu işlevini çağırın. Animasyon Ekle yanlış olarak ayarlayın bScheduleNow ile çağırmanız gerekir.  
  
##  <a name="setautodestroytransitions"></a>CAnimationGroup::SetAutodestroyTransitions  
 Otomatik olarak grubuna ait tüm animasyon nesneleri geçişleri yok yönlendirir.  
  
```  
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bAutoDestroy`  
 Geçişleri yok etmek nasıl belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değeri FALSE olarak yalnızca yığında geçişleri ayırdığınızda ayarlayın. Varsayılan değer doğru ise, bu nedenle, yüksek oranda işlecini kullanarak yeni geçiş nesneler tahsis önerilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar](../../mfc/reference/mfc-classes.md)
