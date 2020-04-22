---
title: CAnimationBaseObject Sınıfı
ms.date: 03/27/2019
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
ms.openlocfilehash: 1874ddfdd26b8dd371e32f7e68ea8f668c47d8e1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750214"
---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject Sınıfı

Tüm animasyon nesneleri için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationBaseObject : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|Fazla Yüklendi. Bir animasyon nesnesi oluşturuyor.|
|[CAnimationBaseObject::~CAnimationBaseObject](#_dtorcanimationbaseobject)|Yıkıcı. Animasyon nesnesi yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject::Geçişuygula](#applytransitions)|Kapsüllü animasyon değişkeni ile film şeridine geçişler ekler.|
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|İlgili tüm geçişleri kaldırır.|
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|Animasyon nesnesi belirli bir animasyon değişkeni bulunup bulunmayacağını belirler.|
|[CAnimationBaseObject::CreateTransitions](#createtransitions)|Animasyon nesnesi ile ilişkili geçişler oluşturur.|
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|Animasyon nesnesi üst animasyon denetleyicisinden ayrılır.|
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Integer Value Changed olay işleyicisi ayarlar.|
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|Değer Değiştirilen olay işleyicisi ayarlar.|
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|İlgili geçişin otomatik olarak yok edilip edilemeyeceğini söyler.|
|[CAnimationBaseObject::GetGroupID](#getgroupid)|Geçerli Grup Kimliğini döndürür.|
|[CAnimationBaseObject::GetObjectID](#getobjectid)|Geçerli Nesne Kimliğini döndürür.|
|[CAnimationBaseObject::GetUserData](#getuserdata)|Kullanıcı tanımlı verileri döndürür.|
|[CAnimationBaseObject::SetAutodestroyGeçişler](#setautodestroytransitions)|Geçişleri otomatik olarak yok etmek için bir bayrak ayarlar.|
|[CAnimationBaseObject::SetID](#setid)|Yeni tbm'ler ayarlar.|
|[CAnimationBaseObject::SetUserData](#setuserdata)|Kullanıcı tanımlı verileri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|İçerdiği animasyon değişkenleri için işaretçiler toplar.|
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|Animasyon nesnesinde bulunan animasyon değişkenleri ile bunların kapsayıcısı arasındaki ilişkiyi kurar.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|İlgili geçişlerin otomatik olarak yok edilip edilmeyeceğini belirtir.|
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|Kullanıcı tanımlı verileri depolar.|
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|Animasyon nesnesinin Grup Kimliğini belirtir.|
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|Animasyon nesnesinin Nesne Kimliğini belirtir.|
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|Üst animasyon denetleyicisine işaretçi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, tüm animasyon nesneleri için temel yöntemleri uygular. Animasyon nesnesi, bir uygulamadaki bir değeri, noktayı, boyutu, dikdörtgeni veya rengin yanı sıra herhangi bir özel varlığı temsil edebilir. Animasyon nesneleri animasyon gruplarında depolanır (Bkz. CAnimationGroup). Her grup ayrı ayrı animasyonlu olabilir ve film şeridinin bir analogu olarak kabul edilebilir. Animasyon nesnesi, mantıksal gösterimine bağlı olarak bir veya daha fazla animasyon değişkenini (Bkz. CAnimationVariable) kapsar. Örneğin, CAnimationRect dört animasyon değişkeni içerir - dikdörtgenin her iki tarafı için bir değişken. Her animasyon nesnesi sınıfı, kapsüllenmiş animasyon değişkenlerine geçişleri uygulamak için kullanılması gereken aşırı yüklü AddTransition yöntemini ortaya çıkarır. Animasyon nesnesi Object ID (isteğe bağlı olarak) ve Grup Kimliği ile tanımlanabilir. Grubu düzeltmek için animasyon nesnesi yerleştirmek için Grup Kimliği gereklidir, ancak Grup Kimliği belirtilmemişse, varsayılan gruba ID 0 ile bir nesne yerleştirilir. SetID'yi farklı GroupID'li olarak çağırırsanız, animasyon nesnesi başka bir gruba taşınır (gerekirse yeni bir grup oluşturulur).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CAnimationBaseObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="_dtorcanimationbaseobject"></a>CAnimationBaseObject::~CAnimationBaseObject

Yıkıcı. Animasyon nesnesi yok edilirken çağrılır.

```
virtual ~CAnimationBaseObject();
```

## <a name="canimationbaseobjectapplytransitions"></a><a name="applytransitions"></a>CAnimationBaseObject::Geçişuygula

Kapsüllü animasyon değişkeni ile film şeridine geçişler ekler.

```
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Bir film şeridi için bir işaretçi.

*bDependOnKeyframes*<br/>
FALSE olduğunda, bu yöntem yalnızca anahtar karelere bağlı olmayan geçişleri ekler.

### <a name="return-value"></a>Dönüş Değeri

Geçişler başarıyla eklenmiştirsa DOĞRU.

### <a name="remarks"></a>Açıklamalar

AddTransition (türemiş sınıflardaki aşırı yüklenen yöntemler) ile eklenen ilgili geçişleri film şeridine ekler.

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="canimationbaseobject"></a>CAnimationBaseObject::CAnimationBaseObject

Bir animasyon nesnesi oluşturuyor.

```
CAnimationBaseObject();

CAnimationBaseObject(
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*nGroupID*<br/>
Grup Kimliğini belirtir.

*nObjectID*<br/>
Nesne Kimliğini belirtir.

*dwUserData*<br/>
Animasyon nesnesi ile ilişkilendirilebilen ve daha sonra çalışma zamanında alınabilen kullanıcı tanımlı veriler.

### <a name="remarks"></a>Açıklamalar

Animasyon nesneleri oluşturuyor ve varsayılan Nesne Kimliği (0) ve Grup Kimliği (0) atar.

## <a name="canimationbaseobjectcleartransitions"></a><a name="cleartransitions"></a>CAnimationBaseObject::ClearTransitions

İlgili tüm geçişleri kaldırır.

```
virtual void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Parametreler

*bAutodestroy*<br/>
Geçiş nesnelerini otomatik olarak yok etmek mi yoksa yalnızca ilgili listeden mi kaldırılacak larını belirtir.

### <a name="remarks"></a>Açıklamalar

BAutodestroy veya m_bAutodestroyTransitions bayrağı DOĞRU ise ilgili tüm geçişleri kaldırır ve bunları yok eder. Geçişler yalnızca yığına ayrılmadıkları takdirde otomatik olarak yok edilmelidir. Yukarıdaki bayraklar FALSE ise, geçişler ilgili geçişlerin iç listesinden kaldırılır.

## <a name="canimationbaseobjectcontainsvariable"></a><a name="containsvariable"></a>CAnimationBaseObject::ContainsVariable

Animasyon nesnesi belirli bir animasyon değişkeni bulunup bulunmayacağını belirler.

```
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametreler

*pDeğişken*<br/>
Animasyon değişkenine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Animasyon değişkeni animasyon nesnesinde yer alırsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, pVariable tarafından belirtilen bir animasyon değişkeninin bir animasyon nesnesi içinde bulunup olmadığını belirlemek için kullanılabilir. Bir animasyon nesnesi, türüne bağlı olarak, birkaç animasyon değişkeni içerebilir. Örneğin, CAnimationColor her renk bileşeni (kırmızı, yeşil ve mavi) için bir tane olmak üzere üç değişken içerir. Animasyon değişkeninin değeri değiştiğinde, Windows Animasyon API'si ValueChanged veya IntegerValueChanged olayları gönderir (etkinse) ve bu olayın parametresi animasyon değişkeninin IUIAnimationVariable arabirimi için bir işaretçidir. Bu yöntem, com nesnesi içeren bir işaretçi animasyon için bir işaretçi elde etmek için yardımcı olur.

## <a name="canimationbaseobjectcreatetransitions"></a><a name="createtransitions"></a>CAnimationBaseObject::CreateTransitions

Animasyon nesnesi ile ilişkili geçişler oluşturur.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Dönüş Değeri

Geçişler başarıyla oluşturulduysa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Türemiş bir animasyon nesnesinde kapsüllenmiş animasyon değişkenleri listesi üzerinde döngüler ve her animasyon değişkeni ile ilişkili geçişler oluşturur.

## <a name="canimationbaseobjectdetachfromcontroller"></a><a name="detachfromcontroller"></a>CAnimationBaseObject::DetachFromController

Animasyon nesnesi üst animasyon denetleyicisinden ayrılır.

```cpp
void DetachFromController();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem dahili olarak kullanılır.

## <a name="canimationbaseobjectenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a>CAnimationBaseObject::EnableIntegerValueChangedEvent

Integer Value Changed olay işleyicisi ayarlar.

```
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pDenetleyici*<br/>
Bir üst denetleyici için bir işaretçi.

*bEtkinleştir*<br/>
Integer Value Changed olayını etkinleştirip etkinleştirmeyeceğini veya devre dışı düşürüp devre dışı düşürmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

Tamsayı Değeri Değiştirilen olay işleyicisi etkinse, bu olayı CAnimationController::OnAnimationIntegerValueChanged yönteminde işleyebilir ve canimationcontroller türetilmiş bir sınıfta geçersiz kılınmalıdır. Animasyon tamsayı değeri her değiştiğinde bu yöntem edenir.

## <a name="canimationbaseobjectenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a>CAnimationBaseObject::EnableValueChangedEvent

Değer Değiştirilen olay işleyicisi ayarlar.

```
virtual void EnableValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pDenetleyici*<br/>
Bir üst denetleyici için bir işaretçi.

*bEtkinleştir*<br/>
Değer Değiştirilen olayı etkinleştirip etkinleştirmeyeceğini veya devre dışı düşürüp devre dışı kölçüp devre tamayacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Değer Değiştirilen olay işleyicisi etkinse, bu olayı CAnimationController::OnAnimationValueChanged yönteminde işleyebilir ve cAnimationController türetilmiş bir sınıfta geçersiz kılınmalıdır. Bu yöntem, animasyon değeri her değiştiğinde çağrılır.

## <a name="canimationbaseobjectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationBaseObject::GetAnimationVariableList

İçerdiği animasyon değişkenleri için işaretçiler toplar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& list) = 0;
```

### <a name="parameters"></a>Parametreler

*list*<br/>
Animasyon nesnesinde bulunan animasyon değişkenleriyle doldurulması gereken liste.

### <a name="remarks"></a>Açıklamalar

Bu saf sanal yöntem türemiş bir sınıfta geçersiz kılınmalıdır. Bir animasyon nesnesi, türüne bağlı olarak bir veya daha fazla animasyon değişkeni içerir. Örneğin, CAnimationPoint sırasıyla X ve Y koordinatları için iki değişken içerir. Taban sınıf CAnimationBaseObject, animasyon değişkenleri listesinde hareket eden bazı genel yöntemleri uygular: Geçişler, ClearTransitions, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Bu yöntemler, belirli bir animasyon nesnesinde bulunan gerçek animasyon değişkenleri ile türemiş bir sınıfta doldurulan GetAnimationVariableList'i çağırır, ardından listenin üzerine döngü ve gerekli eylemleri gerçekleştirir. Özel bir animasyon nesnesi oluşturursanız, bu nesnede bulunan tüm animasyon değişkenlerini *listelemek* için eklemeniz gerekir.

## <a name="canimationbaseobjectgetautodestroytransitions"></a><a name="getautodestroytransitions"></a>CAnimationBaseObject::GetAutodestroyTransitions

İlgili geçişin otomatik olarak yok edilip edilemeyeceğini söyler.

```
BOOL GetAutodestroyTransitions() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE ise, ilgili geçişler otomatik olarak yok edilir; FALSE ise, geçiş nesneleri çağrı uygulaması tarafından tahsis edilmelidir.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu bayrak TRUE'dur. Bu bayrağı yalnızca yığına geçiş ayırdıysanız ve/veya geçişler arama uygulaması tarafından ayrılması gerekiyorsa ayarlayın.

## <a name="canimationbaseobjectgetgroupid"></a><a name="getgroupid"></a>CAnimationBaseObject::GetGroupID

Geçerli Grup Kimliğini döndürür.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Grup Kimliği.

### <a name="remarks"></a>Açıklamalar

Grup Kimliğini almak için bu yöntemi kullanın. Grup Kimliği açıkça oluşturucu veya SetID ile ayarlanmamıştır ysa 0'dır.

## <a name="canimationbaseobjectgetobjectid"></a><a name="getobjectid"></a>CAnimationBaseObject::GetObjectID

Geçerli Nesne Kimliğini döndürür.

```
UINT32 GetObjectID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Nesne Kimliği.

### <a name="remarks"></a>Açıklamalar

Nesne Kimliğini almak için bu yöntemi kullanın. Object ID oluşturucuda veya SetID'de açıkça ayarlanmadıysa 0'dır.

## <a name="canimationbaseobjectgetuserdata"></a><a name="getuserdata"></a>CAnimationBaseObject::GetUserData

Kullanıcı tanımlı verileri döndürür.

```
DWORD GetUserData() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özel verilerin değeri.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanında özel verileri almak için bu yöntemi arayın. Döndürülen değer, oluşturucuda veya SetUserData'da açıkça baş harfe döndürülmediyse 0 olacaktır.

## <a name="canimationbaseobjectm_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a>CAnimationBaseObject::m_bAutodestroyTransitions

İlgili geçişlerin otomatik olarak yok edilip edilmeyeceğini belirtir.

```
BOOL m_bAutodestroyTransitions;
```

## <a name="canimationbaseobjectm_dwuserdata"></a><a name="m_dwuserdata"></a>CAnimationBaseObject::m_dwUserData

Kullanıcı tanımlı verileri depolar.

```
DWORD m_dwUserData;
```

## <a name="canimationbaseobjectm_ngroupid"></a><a name="m_ngroupid"></a>CAnimationBaseObject::m_nGroupID

Animasyon nesnesinin Grup Kimliğini belirtir.

```
UINT32 m_nGroupID;
```

## <a name="canimationbaseobjectm_nobjectid"></a><a name="m_nobjectid"></a>CAnimationBaseObject::m_nObjectID

Animasyon nesnesinin Nesne Kimliğini belirtir.

```
UINT32 m_nObjectID;
```

## <a name="canimationbaseobjectm_pparentcontroller"></a><a name="m_pparentcontroller"></a>CAnimationBaseObject::m_pParentController

Üst animasyon denetleyicisine işaretçi.

```
CAnimationController* m_pParentController;
```

## <a name="canimationbaseobjectsetautodestroytransitions"></a><a name="setautodestroytransitions"></a>CAnimationBaseObject::SetAutodestroyGeçişler

Geçişleri otomatik olarak yok etmek için bir bayrak ayarlar.

```cpp
void SetAutodestroyTransitions(BOOL bValue);
```

### <a name="parameters"></a>Parametreler

*bDeğer*<br/>
Otomatik yok bayrağını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı yalnızca işleç yeni kullanarak geçiş nesnelerini ayırdıysanız ayarlayın. Herhangi bir nedenle geçiş nesneleri yığına ayrılmışsa, otomatik yok edilme bayrağı FALSE olmalıdır. Varsayılan olarak bu bayrak TRUE'dur.

## <a name="canimationbaseobjectsetid"></a><a name="setid"></a>CAnimationBaseObject::SetID

Yeni tbm'ler ayarlar.

```cpp
void SetID(
    UINT32 nObjectID,
    UINT32 nGroupID = 0);
```

### <a name="parameters"></a>Parametreler

*nObjectID*<br/>
Yeni Nesne Kimliği belirtir.

*nGroupID*<br/>
Yeni Grup Kimliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne Kimliği ve Grup Kimliği'ni değiştirmenize olanak tanır. Yeni Grup Kimliği geçerli kimlikten farklıysa, animasyon nesnesi başka bir gruba taşınır (gerekirse yeni bir grup oluşturulur).

## <a name="canimationbaseobjectsetparentanimationobjects"></a><a name="setparentanimationobjects"></a>CAnimationBaseObject::SetParentAnimationObjects

Animasyon nesnesinde bulunan animasyon değişkenleri ile bunların kapsayıcısı arasındaki ilişkiyi kurar.

```
virtual void SetParentAnimationObjects();
```

### <a name="remarks"></a>Açıklamalar

Bu yardımcı, animasyon nesnesinde bulunan animasyon değişkenleri ile kapsayıcıları arasında bir ilişki kurmak için kullanılabilir. Animasyon değişkenlerinin üzerine döngüler ve her animasyon değişkenine bir üst animasyon nesnesi için bir geri işaretçi ayarlar. Geçerli uygulamada, gerçek ilişki CAnimationBaseObject'te kurulur::Geçişleri Uygula, bu nedenle cAnimationGroup::Animate'i arayanakadar geri işaretçiler ayarlanmaz. Olayları işlerken ilişkiyi bilmek yararlı olabilir ve CAnimationVariable'ten bir üst animasyon nesnesi almanız gerekebilir. CAnimationVariable kullanın::GetParentAnimationObject.

## <a name="canimationbaseobjectsetuserdata"></a><a name="setuserdata"></a>CAnimationBaseObject::SetUserData

Kullanıcı tanımlı verileri ayarlar.

```cpp
void SetUserData (DWORD dwUserData);
```

### <a name="parameters"></a>Parametreler

*dwUserData*<br/>
Özel verileri belirtir.

### <a name="remarks"></a>Açıklamalar

Özel verileri animasyon nesnesiyle ilişkilendirmek için bu yöntemi kullanın. Bu veriler daha sonra GetUserData tarafından çalışma zamanında alınabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
