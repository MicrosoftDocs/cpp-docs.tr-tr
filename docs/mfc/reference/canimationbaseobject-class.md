---
title: CAnimationBaseObject sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 6527abf5c91cf440bbbe76d0d5fe49ce2c5dbef7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430452"
---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject sınıfı

Tüm animasyon nesneleri için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationBaseObject : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|Fazla Yüklendi. Bir animasyon nesne oluşturur.|
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#canimationbaseobject__~canimationbaseobject)|Yıkıcı. Bir animasyon nesne yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject::ApplyTransitions](#applytransitions)|Kapsüllenmiş animasyon değişkenle görsel taslağa dönüştürme geçişleri ekler.|
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|Tüm ilgili geçişleri kaldırır.|
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|Bir animasyon nesne belirli bir animasyon değişkenini içerip içermediğini belirler.|
|[CAnimationBaseObject::CreateTransitions](#createtransitions)|Bir animasyon nesneyle ilişkili geçişleri oluşturur.|
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|Üst animasyon denetleyicisini animasyon nesneden çıkarır.|
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Tamsayı değeri değiştirilmiş olay işleyicisi ayarlar.|
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|Olay işleyicisi değeri ayarlar.|
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|İlgili geçiş yok edilir olup olmadığını otomatik olarak bildirir.|
|[CAnimationBaseObject::GetGroupID](#getgroupid)|Geçerli Grup IDsini döndürür.|
|[CAnimationBaseObject::GetObjectID](#getobjectid)|Geçerli nesne IDsini döndürür.|
|[CAnimationBaseObject::GetUserData](#getuserdata)|Kullanıcı tanımlı veri döndürür.|
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|Otomatik olarak geçiş yok etmek için siparişleri bir bayrak ayarlar.|
|[CAnimationBaseObject::SetID](#setid)|Yeni bir kimlik ayarlar.|
|[CAnimationBaseObject::SetUserData](#setuserdata)|Kullanıcı tanımlı kümeleri veri.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|İşaretçileri içerdiği animasyon değişkenlerini toplar.|
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|Bir animasyon nesne ve kendi kapsayıcı içerdiği animasyon değişkenleri arasında bir ilişki kurar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|İlgili geçişleri otomatik olarak yok olup olmadığını belirtir.|
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|Veriyi kullanıcı tanımlı depolar.|
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|Animasyon nesnesinin Grup Kimliğini belirtir.|
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|Animasyon nesnesinin nesne Kimliğini belirtir.|
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|Üst animasyon denetleyici için bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, tüm animasyon nesneleri için temel yöntemlerini uygular. Animasyon nesneyi temsil eden bir değer, nokta, boyutu, dikdörtgen ya da bir uygulama, yanı sıra herhangi bir özel varlık rengi. Animasyon nesneleri (CAnimationGroup bakın) animasyon gruplar halinde depolanır. Her grubu ayrı olarak animasyonu oluşturulabilen ve görsel Taslak'ın bir analog işlenebilir. Bir animasyon nesne (CAnimationVariable bakın) bir veya daha fazla animasyon değişkenleri, mantıksal gösterimine bağlı olarak saklar. Örneğin, dört animasyon değişkenler - bir değişken için her iki tarafındaki dikdörtgen CAnimationRect içerir. Her animasyonu nesne sınıfı, kapsüllenmiş animasyon değişkenlere geçişleri uygulamak için kullanılması gereken aşırı yüklenmiş AddTransition yöntemi gösterir. Bir animasyon nesne tarafından nesne kimliği (isteğe bağlı olarak) tanımlanabilir ve Grup kimliğine göre Bir animasyon nesneyi doğru gruba yerleştirmek için bir Grup Kimliği gereklidir, ancak bir grup kimliği belirtilmezse, bir nesne kimliği 0 varsayılan gruba yerleştirilir. Farklı GroupID ile SetID çağırırsanız, bir animasyon nesne (yeni bir grup gerekirse oluşturulur) başka bir gruba taşınır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationBaseObject`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="_dtorcanimationbaseobject"></a>  CAnimationBaseObject:: ~ CAnimationBaseObject

Yıkıcı. Bir animasyon nesne yok ediliyorken çağırılır.

```
virtual ~CAnimationBaseObject();
```

##  <a name="applytransitions"></a>  CAnimationBaseObject::ApplyTransitions

Kapsüllenmiş animasyon değişkenle görsel taslağa dönüştürme geçişleri ekler.

```
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslak için bir işaretçi.

*bDependOnKeyframes*<br/>
YANLIŞ, bu yöntem, üzerinde ana kareleri bağlı olmayan geçişler ekler.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla eklendi, TRUE.

### <a name="remarks"></a>Açıklamalar

Görsel taslağa dönüştürme AddTransition ile (aşırı yüklenmiş yöntemler türetilmiş sınıflarda) eklenmiş olan ilgili geçişleri ekler.

##  <a name="canimationbaseobject"></a>  CAnimationBaseObject::CAnimationBaseObject

Bir animasyon nesne oluşturur.

```
CAnimationBaseObject();

CAnimationBaseObject(
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*nGroupID*<br/>
Grup kimliğini belirtir.

*nObjectID*<br/>
Nesne kimliğini belirtir.

*dwUserData*<br/>
Animasyon nesneyle ilişkili ve daha sonra çalışma zamanında alınan kullanıcı tarafından tanımlanan verileri.

### <a name="remarks"></a>Açıklamalar

Bir animasyon nesneleri oluşturur ve varsayılan nesne kimliği (0) ve Grup Kimliği (0) atar.

##  <a name="cleartransitions"></a>  CAnimationBaseObject::ClearTransitions

Tüm ilgili geçişleri kaldırır.

```
virtual void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Parametreler

*bAutodestroy*<br/>
Otomatik olarak geçiş nesnelerini yok veya ilgili bir listeden kaldırın belirtir.

### <a name="remarks"></a>Açıklamalar

Tüm ilgili geçişleri kaldırır ve bAutodestroy veya m_bAutodestroyTransitions bayrağı TRUE ise bunlar yok eder. Yığında ayrılan değil yalnızca, geçişleri otomatik olarak yok. Yukarıdaki bayrakları FALSE ise, geçişler yalnızca ilgili geçişleri iç listesinden kaldırılır.

##  <a name="containsvariable"></a>  CAnimationBaseObject::ContainsVariable

Bir animasyon nesne belirli bir animasyon değişkenini içerip içermediğini belirler.

```
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametreler

*pVariable*<br/>
Animasyon değişkeninin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Animasyon değişkenin animasyon nesnesinde yer alıyorsa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, pVariable tarafından belirtilen bir animasyon değişkenini bir animasyon nesne içinde yer alan olup olmadığını belirlemek için kullanılabilir. Animasyon nesnenin kendi türüne bağlı olarak birkaç animasyon değişkenleri içerebilir. Örneğin, her renk bileşeni (kırmızı, yeşil ve mavi) için üç değişkenin CAnimationColor içerir. Animasyon değişkeninin bir değeri değiştirildiğinde Windows animasyon API'sı (etkinse) ValueChanged veya IntegerValueChanged olayları ve bu olay parametresi bir işaretçidir arabirimine animasyon değişkeninin IUIAnimationVariable gönderir. Bu yöntem, animasyon için bağımsız bir COM nesnesine bir işaretçi işaretçisi almak için yardımcı olur.

##  <a name="createtransitions"></a>  CAnimationBaseObject::CreateTransitions

Bir animasyon nesneyle ilişkili geçişleri oluşturur.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulduysa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bir türetilmiş animasyon nesnesinde kapsüllenir animasyon değişkenlerinin listesi üzerinden döngü ve her animasyon değişkeni ile ilişkili geçişleri oluşturur.

##  <a name="detachfromcontroller"></a>  CAnimationBaseObject::DetachFromController

Üst animasyon denetleyicisini animasyon nesneden çıkarır.

```
void DetachFromController();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemi dahili olarak kullanılır.

##  <a name="enableintegervaluechangedevent"></a>  CAnimationBaseObject::EnableIntegerValueChangedEvent

Tamsayı değeri değiştirilmiş olay işleyicisi ayarlar.

```
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pController*<br/>
Bir üst denetleyici için bir işaretçi.

*bSistemlerde*<br/>
Etkinleştirmek veya tamsayı değeri değiştirildi olayını devre dışı bırak belirtir.

### <a name="remarks"></a>Açıklamalar

Tamsayı değeri değiştirilmiş olay işleyicisi etkin olduğu, bu olay CAnimationController türetilen bir sınıfta geçersiz kılınmalıdır CAnimationController::OnAnimationIntegerValueChanged yönteminde başa çıkabilir. Animasyon tamsayı değeri değişti her zaman bu yöntem çağrılır.

##  <a name="enablevaluechangedevent"></a>  CAnimationBaseObject::EnableValueChangedEvent

Olay işleyicisi değeri ayarlar.

```
virtual void EnableValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pController*<br/>
Bir üst denetleyici için bir işaretçi.

*bSistemlerde*<br/>
Değer değiştirildi olayını devre dışı bırak veya belirtir.

### <a name="remarks"></a>Açıklamalar

Değer değiştiren olay işleyicisi etkin olduğu, bu olay CAnimationController türetilen bir sınıfta geçersiz kılınmalıdır CAnimationController::OnAnimationValueChanged yönteminde başa çıkabilir. Animasyon değeri değişti her zaman bu yöntem çağrılır.

##  <a name="getanimationvariablelist"></a>  CAnimationBaseObject::GetAnimationVariableList

İşaretçileri içerdiği animasyon değişkenlerini toplar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst) = 0;
```

### <a name="parameters"></a>Parametreler

*lst*<br/>
Bir animasyon nesnede bulunan animasyon değişkenleriyle doldurulması gereken bir liste.

### <a name="remarks"></a>Açıklamalar

Türetilen bir sınıfta geçersiz kılınması saf bir sanal yöntem budur. Bir veya daha fazla animasyon değişkenleri kendi türüne bağlı olarak bir animasyon nesne içerir. Örneğin, sırasıyla X ve Y koordinatları CAnimationPoint iki değişken içerir. Animasyon değişkenler listesini hareket bazı genel yöntemleri taban sınıf CAnimationBaseObject uygular: ApplyTransitions, ClearTransitions, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Bu yöntemler türetilen bir sınıfta, belirli bir animasyon bir nesnede bulunan gerçek animasyon değişkenleri ile doldurulan, GetAnimationVariableList çağırın, sonra liste üzerinde döngü ve gerekli eylemleri gerçekleştirin. Özel Animasyon nesne oluşturursanız, o nesnenin içerdiği tüm animasyon değişkenleri için lst eklemeniz gerekir.

##  <a name="getautodestroytransitions"></a>  CAnimationBaseObject::GetAutodestroyTransitions

İlgili geçiş yok edilir olup olmadığını otomatik olarak bildirir.

```
BOOL GetAutodestroyTransitions() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE ise, ilgili geçişleri otomatik olarak edilir; FALSE ise, uygulama çağırarak geçişi nesneleri kaldırılmamalıdır.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu bayrağı TRUE şeklindedir. Bu bayrağı yalnızca geçiş yığında ayrılan ve/veya geçişleri çağıran uygulama tarafından serbest bırakılması ayarlayın.

##  <a name="getgroupid"></a>  CAnimationBaseObject::GetGroupID

Geçerli Grup IDsini döndürür.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Grup Kimliği

### <a name="remarks"></a>Açıklamalar

Grubu kimliğini almak için bu yöntemi kullanın. Oluşturucuda veya SetId Grup Kimliği açıkça ayarlanmamış ise 0 güçlendirin.

##  <a name="getobjectid"></a>  CAnimationBaseObject::GetObjectID

Geçerli nesne IDsini döndürür.

```
UINT32 GetObjectID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesne kimliği

### <a name="remarks"></a>Açıklamalar

Nesne kimliğini almak için bu yöntemi kullanın. Oluşturucuda veya SetId, nesne kimliği açıkça ayarlanmamış ise 0 güçlendirin.

##  <a name="getuserdata"></a>  CAnimationBaseObject::GetUserData

Kullanıcı tanımlı veri döndürür.

```
DWORD GetUserData() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özel veri değeri.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanında özel verileri almak için bu yöntemi çağırın. Bunu açıkça Oluşturucusu veya SetUserData başlatılmadı ise, döndürülen değer 0 olur.

##  <a name="m_bautodestroytransitions"></a>  CAnimationBaseObject::m_bAutodestroyTransitions

İlgili geçişleri otomatik olarak yok olup olmadığını belirtir.

```
BOOL m_bAutodestroyTransitions;
```

##  <a name="m_dwuserdata"></a>  CAnimationBaseObject::m_dwUserData

Veriyi kullanıcı tanımlı depolar.

```
DWORD m_dwUserData;
```

##  <a name="m_ngroupid"></a>  CAnimationBaseObject::m_nGroupID

Animasyon nesnesinin Grup Kimliğini belirtir.

```
UINT32 m_nGroupID;
```

##  <a name="m_nobjectid"></a>  CAnimationBaseObject::m_nObjectID

Animasyon nesnesinin nesne Kimliğini belirtir.

```
UINT32 m_nObjectID;
```

##  <a name="m_pparentcontroller"></a>  CAnimationBaseObject::m_pParentController

Üst animasyon denetleyici için bir işaretçi.

```
CAnimationController* m_pParentController;
```

##  <a name="setautodestroytransitions"></a>  CAnimationBaseObject::SetAutodestroyTransitions

Otomatik olarak geçiş yok etmek için siparişleri bir bayrak ayarlar.

```
void SetAutodestroyTransitions(BOOL bValue);
```

### <a name="parameters"></a>Parametreler

*bDeğer*<br/>
Otomatik bayrağı yok belirtir.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı yalnızca işleci kullanarak yeni geçiş nesneleri ayırdığınızda ayarlayın. Otomatik geçiş nesneler yığında ayrılan herhangi bir nedenle yok bayrağı FALSE olmalıdır. Varsayılan olarak, bu bayrağı TRUE şeklindedir.

##  <a name="setid"></a>  CAnimationBaseObject::SetID

Yeni bir kimlik ayarlar.

```
void SetID(
    UINT32 nObjectID,
    UINT32 nGroupID = 0);
```

### <a name="parameters"></a>Parametreler

*nObjectID*<br/>
Yeni nesne kimliğini belirtir.

*nGroupID*<br/>
Yeni Grup kimliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne kimliği ve grup kimliği değiştirmesine olanak verir Yeni Grup Kimliği geçerli Kimliğinden farklı olması durumunda, animasyon nesneyi (yeni bir grup, gerekirse oluşturulur) başka bir gruba taşınır.

##  <a name="setparentanimationobjects"></a>  CAnimationBaseObject::SetParentAnimationObjects

Bir animasyon nesne ve kendi kapsayıcı içerdiği animasyon değişkenleri arasında bir ilişki kurar.

```
virtual void SetParentAnimationObjects();
```

### <a name="remarks"></a>Açıklamalar

Bir animasyon nesne ve kendi kapsayıcı içerdiği animasyon değişkenleri arasında ilişki kurmak için kullanılan bir yardımcı budur. Animasyon değişkenler üzerinde döngü ve her bir animasyon değişken için bir üst animasyon nesnesine geri işaretçisini ayarlar. CAnimationGroup::Animate çağırana kadar CAnimationBaseObject::ApplyTransitions gerçek bir ilişki kurulur geçerli uygulamada geri işaretçileri bu nedenle ayarlanmadı. CAnimationVariable (CAnimationVariable::GetParentAnimationObject kullanın) ', olayları ve üst animasyon almaya gerek işleme nesnesini ilişkiyi bilmek yararlı olabilir.

##  <a name="setuserdata"></a>  CAnimationBaseObject::SetUserData

Kullanıcı tanımlı kümeleri veri.

```
void SetUserData (DWORD dwUserData);
```

### <a name="parameters"></a>Parametreler

*dwUserData*<br/>
Özel verileri belirtir.

### <a name="remarks"></a>Açıklamalar

Özel veri bir animasyon nesnesiyle ilişkilendirmek için bu yöntemi kullanın. Bu veriler daha sonra çalışma zamanında GetUserData tarafından alınabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
