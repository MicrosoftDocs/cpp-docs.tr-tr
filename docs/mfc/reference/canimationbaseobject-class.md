---
title: "CAnimationBaseObject sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
dev_langs: C++
helpviewer_keywords:
- CAnimationBaseObject [MFC], CAnimationBaseObject
- CAnimationBaseObject [MFC], ApplyTransitions
- CAnimationBaseObject [MFC], ClearTransitions
- CAnimationBaseObject [MFC], ContainsVariable
- CAnimationBaseObject [MFC], CreateTransitions
- CAnimationBaseObject [MFC], DetachFromController
- CAnimationBaseObject [MFC], EnableIntegerValueChangedEvent
- CAnimationBaseObject [MFC], EnableValueChangedEvent
- CAnimationBaseObject [MFC], GetAutodestroyTransitions
- CAnimationBaseObject [MFC], GetGroupID
- CAnimationBaseObject [MFC], GetObjectID
- CAnimationBaseObject [MFC], GetUserData
- CAnimationBaseObject [MFC], SetAutodestroyTransitions
- CAnimationBaseObject [MFC], SetID
- CAnimationBaseObject [MFC], SetUserData
- CAnimationBaseObject [MFC], GetAnimationVariableList
- CAnimationBaseObject [MFC], SetParentAnimationObjects
- CAnimationBaseObject [MFC], m_bAutodestroyTransitions
- CAnimationBaseObject [MFC], m_dwUserData
- CAnimationBaseObject [MFC], m_nGroupID
- CAnimationBaseObject [MFC], m_nObjectID
- CAnimationBaseObject [MFC], m_pParentController
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b1fb434158d263b57fb34d15d976d9bae41c4df
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject sınıfı
Tüm animasyon nesneleri için temel sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|Fazla Yüklendi. Bir animasyon nesnesi oluşturur.|  
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#canimationbaseobject__~canimationbaseobject)|Yok Edicisi. Bir animasyon nesne yok çağrılır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationBaseObject::ApplyTransitions](#applytransitions)|Kapsüllenmiş animasyon değişkenle film şeridi geçişleri ekler.|  
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|Tüm ilgili geçişleri kaldırır.|  
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|Bir animasyon nesne belirli animasyon değişkeni içerip içermediğini belirler.|  
|[CAnimationBaseObject::CreateTransitions](#createtransitions)|Bir animasyon nesneyle ilişkilendirilmiş geçişleri oluşturur.|  
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|Üst animasyon denetleyicisi animasyon nesneden çıkarır.|  
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Tamsayı değer değiştiren olay işleyicisini ayarlar.|  
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|Değer değiştiren olay işleyicisini ayarlar.|  
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|İlgili geçiş kaybolur olup olmadığını otomatik olarak bildirir.|  
|[CAnimationBaseObject::GetGroupID](#getgroupid)|Geçerli Grup Kimliği döndürür|  
|[CAnimationBaseObject::GetObjectID](#getobjectid)|Geçerli nesne kimliği döndürür|  
|[CAnimationBaseObject::GetUserData](#getuserdata)|Kullanıcı tanımlı veri döndürür.|  
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|Otomatik olarak geçişleri yok etmek için siparişler bir bayrak ayarlar.|  
|[CAnimationBaseObject::SetID](#setid)|Yeni kimlikleri ayarlar.|  
|[CAnimationBaseObject::SetUserData](#setuserdata)|Kullanıcı tanımlı kümeleri veri.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|İşaretçileri kapsanan animasyon değişkenlere toplar.|  
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|Animasyon değişkenleri, bir animasyon nesne ve bunların kapsayıcısında bulunan arasında ilişki kurar.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|İlgili geçişleri otomatik olarak yok edilmesi olup olmadığını belirtir.|  
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|Veriyi kullanıcı tanımlı depolar.|  
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|Animasyon nesnenin Grup Kimliğini belirtir.|  
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|Animasyon nesnenin nesne kimliği belirtir.|  
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|Üst animasyon denetleyici için bir işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın tüm animasyon nesneleri için temel yöntemlerini uygular. Animasyon nesneyi temsil eden bir değer, nokta, boyut, dikdörtgen veya bir uygulamayı, aynı zamanda herhangi bir özel varlık rengi. Animasyon nesneler (CAnimationGroup bakın) animasyon gruplarında depolanır. Her grubu ayrı ayrı animasyonlu ve bir film şeridi analog ele alınabilir. Bir animasyon nesne (CAnimationVariable bakın) bir veya daha fazla animasyon değişkenleri, mantıksal temsilini bağlı olarak yalıtır. Örneğin, dört animasyon değişkenleri - iki dikdörtgen tarafındaki için bir değişken CAnimationRect içerir. Her bir animasyon nesne sınıfı kapsüllenmiş animasyon değişkenlere geçişleri uygulamak için kullanılması gereken aşırı yüklenmiş AddTransition yöntemi gösterir. Bir animasyon nesne tarafından nesne kimliği (isteğe bağlı) tanımlanabilir ve Grup kimliğine göre Bir animasyon nesneyi doğru grubuna yerleştirmek için bir Grup Kimliği gereklidir, ancak bir grup kimliği belirtilmezse, bir nesne kimliği 0 varsayılan grubuyla yerleştirilir. Farklı GroupID ile SetID çağırırsanız, animasyon nesneyi (yeni bir grup gerekirse oluşturulur) başka bir gruba taşınır.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationBaseObject`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationbaseobject"></a>CAnimationBaseObject:: ~ CAnimationBaseObject  
 Yok Edicisi. Bir animasyon nesne yok çağrılır.  
  
```  
virtual ~CAnimationBaseObject();
```  
  
##  <a name="applytransitions"></a>CAnimationBaseObject::ApplyTransitions  
 Kapsüllenmiş animasyon değişkenle film şeridi geçişleri ekler.  
  
```  
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Parametreler  
 `pStoryboard`  
 Film şeridi gösteren bir işaretçi.  
  
 `bDependOnKeyframes`  
 YANLIŞ bu yöntem yalnızca ana kare üzerinde dayanmayan geçişleri ekler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçişleri başarıyla eklendi TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 Film şeridi için AddTransition ile (türetilen sınıflar aşırı yüklenmiş yöntemler) eklenmiş olan ilgili geçişleri ekler.  
  
##  <a name="canimationbaseobject"></a>CAnimationBaseObject::CAnimationBaseObject  
 Bir animasyon nesnesi oluşturur.  
  
```  
CAnimationBaseObject();

 
CAnimationBaseObject(
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `nGroupID`  
 Grup kimliğini belirtir.  
  
 `nObjectID`  
 Nesne kimliğini belirtir.  
  
 `dwUserData`  
 Animasyon nesneyle ilişkilendirilmiş ve daha sonra çalışma zamanında alınan kullanıcı tarafından tanımlanan verileri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir animasyon nesneleri oluşturur ve varsayılan nesne kimliği (0) ve Grup Kimliği (0) atar.  
  
##  <a name="cleartransitions"></a>CAnimationBaseObject::ClearTransitions  
 Tüm ilgili geçişleri kaldırır.  
  
```  
virtual void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>Parametreler  
 `bAutodestroy`  
 Geçiş nesneleri otomatik olarak yok ya da ilgili listeden kaldırana belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 İlgili tüm geçişler kaldırır ve bAutodestroy veya m_bAutodestroyTransitions bayrağı TRUE ise bunları yok eder. Yığında ayrılan değil yalnızca varsa geçişleri otomatik olarak yok edilmesi. Yukarıdaki bayrakları FALSE olduğunda ise geçişler yalnızca ilgili geçişleri iç listesinden kaldırılır.  
  
##  <a name="containsvariable"></a>CAnimationBaseObject::ContainsVariable  
 Bir animasyon nesne belirli animasyon değişkeni içerip içermediğini belirler.  
  
```  
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Parametreler  
 `pVariable`  
 Animasyon değişkeni için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyon değişkeni animasyon nesnesinde yer alıyorsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, pVariable tarafından belirtilen bir animasyon değişkenine bir animasyon nesnesi içinde yer alan olup olmadığını belirlemek için kullanılabilir. Bir animasyon nesne, kendi türüne bağlı olarak birkaç animasyon değişkenleri içerebilir. Örneğin, her renk bileşeni (kırmızı, yeşil ve mavi) için üç değişkenleri CAnimationColor içerir. Animasyon değişkenin değerini değiştiğinde Windows animasyon API (etkinse) ValueChanged veya IntegerValueChanged olaylar ve bu olay parametresi bir işaretçidir arabirimi animasyon değişkenin IUIAnimationVariable gönderir. Bu yöntem, bir işaretçi animasyonuna kapsanan COM nesnesi için bir işaretçi almak için yardımcı olur.  
  
##  <a name="createtransitions"></a>CAnimationBaseObject::CreateTransitions  
 Bir animasyon nesneyle ilişkilendirilmiş geçişleri oluşturur.  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçişleri başarıyla oluşturuldu, TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir türetilmiş animasyon nesnesinde kapsüllenmiş animasyon değişkenlerin listesini üzerinden döngüler ve her animasyon değişkeni ile ilişkilendirilmiş geçişleri oluşturur.  
  
##  <a name="detachfromcontroller"></a>CAnimationBaseObject::DetachFromController  
 Üst animasyon denetleyicisi animasyon nesneden çıkarır.  
  
```  
void DetachFromController();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem dahili olarak kullanılır.  
  
##  <a name="enableintegervaluechangedevent"></a>CAnimationBaseObject::EnableIntegerValueChangedEvent  
 Tamsayı değer değiştiren olay işleyicisini ayarlar.  
  
```  
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 `pController`  
 Bir üst denetleyici için bir işaretçi.  
  
 `bEnable`  
 Etkinleştirmek veya tamsayı değeri değişti olayını devre dışı bırakmayı belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Tamsayı değer değiştiren olay işleyicisi etkinleştirilirse, bu olay CAnimationController türetilen bir sınıfta geçersiz kılınmalıdır CAnimationController::OnAnimationIntegerValueChanged yönteminde işleyebilir. Animasyon tamsayı değeri değiştirildi her zaman bu yöntem çağrılır.  
  
##  <a name="enablevaluechangedevent"></a>CAnimationBaseObject::EnableValueChangedEvent  
 Değer değiştiren olay işleyicisini ayarlar.  
  
```  
virtual void EnableValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 `pController`  
 Bir üst denetleyici için bir işaretçi.  
  
 `bEnable`  
 Etkinleştirmek veya değer değişti olayını devre dışı bırakmayı belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Değer değiştiren olay işleyicisi etkinleştirilirse, bu olay CAnimationController türetilen bir sınıfta geçersiz kılınmalıdır CAnimationController::OnAnimationValueChanged yönteminde işleyebilir. Animasyon değeri değiştirildi her zaman bu yöntem çağrılır.  
  
##  <a name="getanimationvariablelist"></a>CAnimationBaseObject::GetAnimationVariableList  
 İşaretçileri kapsanan animasyon değişkenlere toplar.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst) = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lst`  
 Bir animasyon nesnede bulunan animasyon değişkenleri ile doldurulması gerekir listesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta geçersiz kılınmalıdır saf sanal bir yöntem budur. Kendi türüne bağlı olarak bir animasyon nesnesi bir veya daha fazla animasyon değişkenleri içerir. Örneğin, sırasıyla X ve Y koordinatları CAnimationPoint iki değişken içeriyor. Bir animasyon değişkenleri listesi hareket bazı genel yöntemler taban sınıf CAnimationBaseObject uygular: ApplyTransitions, ClearTransitions, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Bu yöntemleri türetilen bir sınıfta belirli animasyon nesnesinde yer alan gerçek animasyon değişkenleriyle girilir, GetAnimationVariableList çağrısı sonra listenin döngü ve gerekli eylemleri gerçekleştirin. Özel Animasyon nesne oluşturursanız, o nesnenin içerdiği tüm animasyon değişkenleri için lst eklemeniz gerekir.  
  
##  <a name="getautodestroytransitions"></a>CAnimationBaseObject::GetAutodestroyTransitions  
 İlgili geçiş kaybolur olup olmadığını otomatik olarak bildirir.  
  
```  
BOOL GetAutodestroyTransitions() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE ise, ilgili geçişleri otomatik olarak yok olur; FALSE ise, geçiş nesneleri uygulama çağrılmasıyla.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak bu bayrak true'dur. Bu bayrak, yalnızca geçiş yığında ayrılan ve/veya geçişleri çağıran uygulama tarafından bırakılmasına ayarlayın.  
  
##  <a name="getgroupid"></a>CAnimationBaseObject::GetGroupID  
 Geçerli Grup Kimliği döndürür  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli Grup Kimliği  
  
### <a name="remarks"></a>Açıklamalar  
 Grup Kimliği almak için bu yöntemi kullanın Oluşturucuda veya SetId Grup Kimliği açıkça ayarlanmamış ise 0 kullanıcının.  
  
##  <a name="getobjectid"></a>CAnimationBaseObject::GetObjectID  
 Geçerli nesne kimliği döndürür  
  
```  
UINT32 GetObjectID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli nesne kimliği  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne Kimliği almak için bu yöntemi kullanın Oluşturucuda veya SetId nesne kimliği açıkça ayarlanmamış ise 0 kullanıcının.  
  
##  <a name="getuserdata"></a>CAnimationBaseObject::GetUserData  
 Kullanıcı tanımlı veri döndürür.  
  
```  
DWORD GetUserData() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Özel veri değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanında özel verileri almak için bu yöntemi çağırın. Döndürülen değer, açıkça Oluşturucusu veya SetUserData başlatılmadı 0 olacaktır.  
  
##  <a name="m_bautodestroytransitions"></a>CAnimationBaseObject::m_bAutodestroyTransitions  
 İlgili geçişleri otomatik olarak yok edilmesi olup olmadığını belirtir.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
##  <a name="m_dwuserdata"></a>CAnimationBaseObject::m_dwUserData  
 Veriyi kullanıcı tanımlı depolar.  
  
```  
DWORD m_dwUserData;  
```  
  
##  <a name="m_ngroupid"></a>CAnimationBaseObject::m_nGroupID  
 Animasyon nesnenin Grup Kimliğini belirtir.  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_nobjectid"></a>CAnimationBaseObject::m_nObjectID  
 Animasyon nesnenin nesne kimliği belirtir.  
  
```  
UINT32 m_nObjectID;  
```  
  
##  <a name="m_pparentcontroller"></a>CAnimationBaseObject::m_pParentController  
 Üst animasyon denetleyici için bir işaretçi.  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="setautodestroytransitions"></a>CAnimationBaseObject::SetAutodestroyTransitions  
 Otomatik olarak geçişleri yok etmek için siparişler bir bayrak ayarlar.  
  
```  
void SetAutodestroyTransitions(BOOL bValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `bValue`  
 Otomatik destroy bayrağı belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca geçiş nesneleri işlecini kullanarak yeni ayırdığınızda bu bayrağını ayarlayın. Otomatik geçiş nesneleri yığında ayrılan nedenden dolayı destroy bayrağı FALSE olmalıdır. Varsayılan olarak bu bayrak true'dur.  
  
##  <a name="setid"></a>CAnimationBaseObject::SetID  
 Yeni kimlikleri ayarlar.  
  
```  
void SetID(
    UINT32 nObjectID,  
    UINT32 nGroupID = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `nObjectID`  
 Yeni nesne kimliğini belirtir.  
  
 `nGroupID`  
 Yeni Grup kimliğini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne kimliği ve grup kimliği değiştirmesine olanak verir Yeni Grup Kimliği geçerli Kimliğinden farklı olması durumunda bir animasyon nesne (yeni bir grup, gerekirse oluşturulacak) başka bir gruba taşınır.  
  
##  <a name="setparentanimationobjects"></a>CAnimationBaseObject::SetParentAnimationObjects  
 Animasyon değişkenleri, bir animasyon nesne ve bunların kapsayıcısında bulunan arasında ilişki kurar.  
  
```  
virtual void SetParentAnimationObjects();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bir animasyon nesne ve bunların kapsayıcısında bulunan animasyon değişkenleri arasında ilişki kurmak için kullanılan bir yardımcı olur. Animasyon değişkenlerinden döngüler ve her bir animasyon değişken için bir üst animasyon nesnesine geri işaretçi ayarlar. CAnimationGroup::Animate çağrısı tamamlanana kadar CAnimationBaseObject::ApplyTransitions gerçek ilişkisi geçerli uygulamasında arka işaretçileri bu nedenle ayarlanmadı. Olaylar ve üst animasyon almaya gerek işleme (kullanın CAnimationVariable::GetParentAnimationObject) CAnimationVariable nesnesini ilişki bilerek yararlı olabilir.  
  
##  <a name="setuserdata"></a>CAnimationBaseObject::SetUserData  
 Kullanıcı tanımlı kümeleri veri.  
  
```  
void SetUserData (DWORD dwUserData);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwUserData`  
 Özel veri belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bir veri olan bir animasyon nesne ilişkilendirmek için bu yöntemi kullanın. Bu veriler daha sonra çalışma zamanında GetUserData tarafından alınabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../mfc/reference/mfc-classes.md)
