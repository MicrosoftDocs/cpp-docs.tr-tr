---
description: 'Daha fazla bilgi edinin: CAnimationBaseObject sınıfı'
title: CAnimationBaseObject sınıfı
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
ms.openlocfilehash: bc44d0e55b409f66648007eeb27fefd386640d9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318669"
---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject sınıfı

Tüm animasyon nesneleri için temel sınıf.

## <a name="syntax"></a>Syntax

```
class CAnimationBaseObject : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject:: CAnimationBaseObject](#canimationbaseobject)|Fazla Yüklendi. Bir animasyon nesnesi oluşturur.|
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#_dtorcanimationbaseobject)|Yok edicisi. Bir animasyon nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject:: Applygeçişleri](#applytransitions)|Encapsulated animasyon değişkeniyle görsel taslağa geçişler ekler.|
|[CAnimationBaseObject:: Cleargeçişler](#cleartransitions)|Tüm ilgili geçişleri kaldırır.|
|[CAnimationBaseObject:: ContainsVariable](#containsvariable)|Bir animasyon nesnesinin belirli bir animasyon değişkeni içerip içermediğini belirler.|
|[CAnimationBaseObject:: Creategeçişler](#createtransitions)|Bir animasyon nesnesiyle ilişkili geçişleri oluşturur.|
|[CAnimationBaseObject::D etachFromController](#detachfromcontroller)|Bir animasyon nesnesini üst animasyon denetleyicisinden ayırır.|
|[CAnimationBaseObject:: EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Tamsayı değeri değişti olay işleyicisini ayarlar.|
|[CAnimationBaseObject:: EnableValueChangedEvent](#enablevaluechangedevent)|Değer değişti olay işleyicisini ayarlar.|
|[CAnimationBaseObject:: Getautodestroygeçişler](#getautodestroytransitions)|İlgili geçişin otomatik olarak yok edildiğini söyler.|
|[CAnimationBaseObject:: Getgroupıd](#getgroupid)|Geçerli grup KIMLIĞINI döndürür.|
|[CAnimationBaseObject:: Getobjectıd](#getobjectid)|Geçerli nesne KIMLIĞINI döndürür.|
|[CAnimationBaseObject:: GetUserData](#getuserdata)|Kullanıcı tanımlı verileri döndürür.|
|[CAnimationBaseObject:: Setautodestroygeçişler](#setautodestroytransitions)|Geçişleri otomatik olarak yok etmek için bir bayrak ayarlar.|
|[CAnimationBaseObject:: SetID](#setid)|Yeni kimlikleri ayarlar.|
|[CAnimationBaseObject:: SetUserData](#setuserdata)|Kullanıcı tanımlı verileri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject:: GetAnimationVariableList](#getanimationvariablelist)|İçerilen animasyon değişkenlerine işaretçiler toplar.|
|[CAnimationBaseObject:: SetParentAnimationObjects](#setparentanimationobjects)|Animasyon değişkenleri, bir animasyon nesnesi ve bunların kapsayıcısı arasında ilişki kurar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationBaseObject:: m_bAutodestroyTransitions](#m_bautodestroytransitions)|İlgili geçişlerin otomatik olarak yok edilmesi gerekip gerekmediğini belirtir.|
|[CAnimationBaseObject:: m_dwUserData](#m_dwuserdata)|Kullanıcı tanımlı verileri depolar.|
|[CAnimationBaseObject:: m_nGroupID](#m_ngroupid)|Animasyon nesnesinin Grup KIMLIĞINI belirtir.|
|[CAnimationBaseObject:: m_nObjectID](#m_nobjectid)|Animasyon nesnesinin nesne KIMLIĞINI belirtir.|
|[CAnimationBaseObject:: m_pParentController](#m_pparentcontroller)|Üst animasyon denetleyicisine yönelik bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, tüm animasyon nesneleri için temel yöntemleri uygular. Animasyon nesnesi, bir uygulamadaki bir değeri, noktayı, boyutu, dikdörtgeni veya rengi ve herhangi bir özel varlığı temsil edebilir. Animasyon nesneleri animasyon gruplarında depolanır (bkz. CAnimationGroup). Her grup ayrı olarak animasyonlu ve bir analog bir film şeridi olarak değerlendirilebilirler. Animasyon nesnesi bir veya daha fazla animasyon değişkenini (bkz. CAnimationVariable), mantıksal gösterimine göre kapsüller. Örneğin, CAnimationRect, dikdörtgenin her tarafında bir değişken olmak üzere dört animasyon değişkeni içerir. Her animasyon nesne sınıfı, kapsüllenmiş animasyon değişkenlerine geçiş uygulamak için kullanılması gereken aşırı yüklenmiş AddTransition yöntemini kullanıma sunar. Animasyon nesnesi, nesne KIMLIĞI (isteğe bağlı) ve Grup KIMLIĞI ile tanımlanabilir. Grup KIMLIĞI, doğru gruba bir animasyon nesnesi yerleştirmek için gereklidir, ancak bir grup KIMLIĞI belirtilmemişse, KIMLIĞI 0 olan varsayılan gruba bir nesne yerleştirilir. Farklı GroupID ile SetID 'yi çağırırsanız, bir animasyon nesnesi başka bir gruba taşınır (gerekirse yeni bir grup oluşturulur).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationBaseObject`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="_dtorcanimationbaseobject"></a> CAnimationBaseObject:: ~ CAnimationBaseObject

Yok edicisi. Bir animasyon nesnesi yok edildiğinde çağırılır.

```
virtual ~CAnimationBaseObject();
```

## <a name="canimationbaseobjectapplytransitions"></a><a name="applytransitions"></a> CAnimationBaseObject:: Applygeçişleri

Encapsulated animasyon değişkeniyle görsel taslağa geçişler ekler.

```
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslağa yönelik işaretçi.

*bDependOnKeyframes*<br/>
FALSE olduğunda, bu yöntem yalnızca ana karelere bağımlı olmayan geçişleri ekler.

### <a name="return-value"></a>Dönüş Değeri

Geçişler başarıyla eklendiyse TRUE.

### <a name="remarks"></a>Açıklamalar

Görsel taslağa AddTransition (türetilmiş sınıflarda aşırı yüklenmiş yöntemler) eklenmiş ilişkili geçişleri ekler.

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="canimationbaseobject"></a> CAnimationBaseObject:: CAnimationBaseObject

Bir animasyon nesnesi oluşturur.

```
CAnimationBaseObject();

CAnimationBaseObject(
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*Ngroupıd*<br/>
Grup KIMLIĞINI belirtir.

*Nobjectıd*<br/>
Nesne KIMLIĞINI belirtir.

*dwUserData*<br/>
Animasyon nesnesiyle ilişkilendirilebilen ve daha sonra çalışma zamanında alınabilecek Kullanıcı tanımlı veriler.

### <a name="remarks"></a>Açıklamalar

Bir animasyon nesnesi oluşturur ve varsayılan nesne KIMLIĞI (0) ve Grup KIMLIĞI (0) atar.

## <a name="canimationbaseobjectcleartransitions"></a><a name="cleartransitions"></a> CAnimationBaseObject:: Cleargeçişler

Tüm ilgili geçişleri kaldırır.

```
virtual void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Parametreler

*bAutodestroy*<br/>
Geçiş nesnelerinin otomatik olarak yok edilip edilmeyeceğini belirtir veya yalnızca ilgili listeden kaldırın.

### <a name="remarks"></a>Açıklamalar

Tüm ilgili geçişleri kaldırır ve bAutodestroy veya m_bAutodestroyTransitions bayrağı TRUE ise onları yok eder. Geçişler yalnızca yığında ayrıldıklarında otomatik olarak yok edilmelidir. Yukarıdaki bayraklar YANLıŞSA, geçişler yalnızca ilgili geçişlerin iç listesinden kaldırılır.

## <a name="canimationbaseobjectcontainsvariable"></a><a name="containsvariable"></a> CAnimationBaseObject:: ContainsVariable

Bir animasyon nesnesinin belirli bir animasyon değişkeni içerip içermediğini belirler.

```
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametreler

*pVariable*<br/>
Animasyon değişkenine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Animasyon değişkeni animasyon nesnesinde içeriyorsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, pVariable tarafından belirtilen bir animasyon değişkeninin bir animasyon nesnesi içinde içerilip içerilmeyeceğini belirlemede kullanılabilir. Türüne bağlı olarak bir animasyon nesnesi birkaç animasyon değişkeni içerebilir. Örneğin, CAnimationColor her renk bileşeni için bir tane olmak üzere üç değişken içerir (kırmızı, yeşil ve mavi). Animasyon değişkeninin bir değeri değiştiğinde, Windows animasyon API 'SI ValueChanged veya IntegerValueChanged olayları gönderir (etkinse) ve bu olayın parametresi, Animasyon değişkeninin Interface IUIAnimationVariable öğesine yönelik bir işaretçidir. Bu yöntem, içerilen COM nesnesine bir işaretçiden animasyon işaretçisi edinmeye yardımcı olur.

## <a name="canimationbaseobjectcreatetransitions"></a><a name="createtransitions"></a> CAnimationBaseObject:: Creategeçişler

Bir animasyon nesnesiyle ilişkili geçişleri oluşturur.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Dönüş Değeri

Geçişler başarıyla oluşturulduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Türetilmiş bir animasyon nesnesinde kapsüllenmiş animasyon değişkenleri listesi üzerinden döngüler ve her bir animasyon değişkeniyle ilişkili geçişler oluşturur.

## <a name="canimationbaseobjectdetachfromcontroller"></a><a name="detachfromcontroller"></a> CAnimationBaseObject::D etachFromController

Bir animasyon nesnesini üst animasyon denetleyicisinden ayırır.

```cpp
void DetachFromController();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem dahili olarak kullanılır.

## <a name="canimationbaseobjectenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a> CAnimationBaseObject:: EnableIntegerValueChangedEvent

Tamsayı değeri değişti olay işleyicisini ayarlar.

```
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pController*<br/>
Üst denetleyiciye yönelik bir işaretçi.

*bEnable*<br/>
Tamsayı değeri değişti olayının etkinleştirilip etkinleştirilmeyeceğini veya devre dışı bırakılacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Tamsayı değeri değişti olay işleyicisi etkinse, bu olayı CAnimationController:: OnAnimationIntegerValueChanged yönteminde işleyebilir, bu da CAnimationController ile türetilmiş bir sınıfta geçersiz kılınmalıdır. Animasyon tamsayı değeri her değiştiğinde bu yöntem çağrılır.

## <a name="canimationbaseobjectenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a> CAnimationBaseObject:: EnableValueChangedEvent

Değer değişti olay işleyicisini ayarlar.

```
virtual void EnableValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pController*<br/>
Üst denetleyiciye yönelik bir işaretçi.

*bEnable*<br/>
Değer değiştirme olayının etkinleştirilip etkinleştirilmeyeceğini veya devre dışı bırakılacağını belirtir.

### <a name="remarks"></a>Açıklamalar

Olay işleyicisi değeri değiştiyse, bu olayı CAnimationController:: OnAnimationValueChanged yönteminde işleyebilir, bu da CAnimationController ile türetilmiş bir sınıfta geçersiz kılınmalıdır. Animasyon değeri her değiştiğinde bu yöntem çağrılır.

## <a name="canimationbaseobjectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationBaseObject:: GetAnimationVariableList

İçerilen animasyon değişkenlerine işaretçiler toplar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& list) = 0;
```

### <a name="parameters"></a>Parametreler

*list*<br/>
Animasyon nesnesinde bulunan animasyon değişkenleriyle doldurulması gereken bir liste.

### <a name="remarks"></a>Açıklamalar

Bu saf sanal yöntemin türetilmiş bir sınıfta geçersiz kılınması gerekir. Bir animasyon nesnesi türüne bağlı olarak bir veya daha fazla animasyon değişkeni içerir. Örneğin, CAnimationPoint sırasıyla X ve Y koordinatları için iki değişken içerir. CAnimationBaseObject temel sınıfı, bir animasyon değişkenleri listesi üzerinde davranan bazı genel yöntemleri uygular: Applygeçişleri, Cleargeçişleri, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Bu yöntemler, belirli bir animasyon nesnesinde bulunan gerçek animasyon değişkenlerine sahip türetilmiş bir sınıf içinde doldurulan GetAnimationVariableList öğesini çağırır, sonra listenin üzerinde döngü yapar ve gerekli eylemleri gerçekleştirir. Özel bir animasyon nesnesi oluşturursanız, bu nesnenin içerdiği tüm animasyon değişkenlerini *listelemek* için eklemeniz gerekir.

## <a name="canimationbaseobjectgetautodestroytransitions"></a><a name="getautodestroytransitions"></a> CAnimationBaseObject:: Getautodestroygeçişler

İlgili geçişin otomatik olarak yok edildiğini söyler.

```
BOOL GetAutodestroyTransitions() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE ise ilgili geçişler otomatik olarak yok edilir; FALSE ise, uygulama çağırarak geçiş nesneleri serbest bırakılmalıdır.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu bayrak doğrudur. Bu bayrağı yalnızca, yığında geçiş ayrıldıysanız ve/veya geçişlerin çağıran uygulama tarafından serbest bırakılmasının gerekip gerekmediğini ayarlayın.

## <a name="canimationbaseobjectgetgroupid"></a><a name="getgroupid"></a> CAnimationBaseObject:: Getgroupıd

Geçerli grup KIMLIĞINI döndürür.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli grup KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Grup KIMLIĞINI almak için bu yöntemi kullanın. Grup KIMLIĞI açıkça oluşturucuda veya SetID ile ayarlanmamışsa 0 ' dır.

## <a name="canimationbaseobjectgetobjectid"></a><a name="getobjectid"></a> CAnimationBaseObject:: Getobjectıd

Geçerli nesne KIMLIĞINI döndürür.

```
UINT32 GetObjectID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesne KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Nesne KIMLIĞINI almak için bu yöntemi kullanın. Nesne KIMLIĞI, Oluşturucu içinde veya SetID ile açıkça ayarlanmamışsa 0 ' dır.

## <a name="canimationbaseobjectgetuserdata"></a><a name="getuserdata"></a> CAnimationBaseObject:: GetUserData

Kullanıcı tanımlı verileri döndürür.

```
DWORD GetUserData() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özel verilerin bir değeri.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanında özel verileri almak için bu yöntemi çağırın. Döndürülen değer, oluşturucuda veya SetUserData ile açıkça başlatılmazsa 0 olur.

## <a name="canimationbaseobjectm_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a> CAnimationBaseObject:: m_bAutodestroyTransitions

İlgili geçişlerin otomatik olarak yok edilmesi gerekip gerekmediğini belirtir.

```
BOOL m_bAutodestroyTransitions;
```

## <a name="canimationbaseobjectm_dwuserdata"></a><a name="m_dwuserdata"></a> CAnimationBaseObject:: m_dwUserData

Kullanıcı tanımlı verileri depolar.

```
DWORD m_dwUserData;
```

## <a name="canimationbaseobjectm_ngroupid"></a><a name="m_ngroupid"></a> CAnimationBaseObject:: m_nGroupID

Animasyon nesnesinin Grup KIMLIĞINI belirtir.

```
UINT32 m_nGroupID;
```

## <a name="canimationbaseobjectm_nobjectid"></a><a name="m_nobjectid"></a> CAnimationBaseObject:: m_nObjectID

Animasyon nesnesinin nesne KIMLIĞINI belirtir.

```
UINT32 m_nObjectID;
```

## <a name="canimationbaseobjectm_pparentcontroller"></a><a name="m_pparentcontroller"></a> CAnimationBaseObject:: m_pParentController

Üst animasyon denetleyicisine yönelik bir işaretçi.

```
CAnimationController* m_pParentController;
```

## <a name="canimationbaseobjectsetautodestroytransitions"></a><a name="setautodestroytransitions"></a> CAnimationBaseObject:: Setautodestroygeçişler

Geçişleri otomatik olarak yok etmek için bir bayrak ayarlar.

```cpp
void SetAutodestroyTransitions(BOOL bValue);
```

### <a name="parameters"></a>Parametreler

*bDeğer*<br/>
Otomatik yok etme bayrağını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu bayrağı yalnızca New işlecini kullanarak geçiş nesnelerini ayırdıysanız ayarlayın. Yığın üzerinde bazı nedenler geçiş nesneleri ayrılmışsa otomatik yok etme bayrağı yanlış olmalıdır. Varsayılan olarak bu bayrak doğrudur.

## <a name="canimationbaseobjectsetid"></a><a name="setid"></a> CAnimationBaseObject:: SetID

Yeni kimlikleri ayarlar.

```cpp
void SetID(
    UINT32 nObjectID,
    UINT32 nGroupID = 0);
```

### <a name="parameters"></a>Parametreler

*Nobjectıd*<br/>
Yeni nesne KIMLIĞINI belirtir.

*Ngroupıd*<br/>
Yeni bir grup KIMLIĞI belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne KIMLIĞINI ve grup KIMLIĞINI değiştirmenize izin verir. Yeni Grup KIMLIĞI geçerli KIMLIKLE farklıysa, bir animasyon nesnesi başka bir gruba taşınır (gerekirse yeni bir grup oluşturulur).

## <a name="canimationbaseobjectsetparentanimationobjects"></a><a name="setparentanimationobjects"></a> CAnimationBaseObject:: SetParentAnimationObjects

Animasyon değişkenleri, bir animasyon nesnesi ve bunların kapsayıcısı arasında ilişki kurar.

```
virtual void SetParentAnimationObjects();
```

### <a name="remarks"></a>Açıklamalar

Bu yardımcı, bir animasyon nesnesinde bulunan animasyon değişkenleri ve bunların kapsayıcısı arasında bir ilişki oluşturmak için kullanılabilir. Animasyon değişkenleri üzerinde döngü yapar ve her animasyon değişkenine bir üst animasyon nesnesine bir geri işaretçi ayarlar. Geçerli uygulamada, CAnimationBaseObject:: Applygeçişler ' de gerçek ilişki oluşturulur, bu nedenle CAnimationGroup:: canlandır ' ı çağırana kadar geri işaretçiler ayarlanamaz. İlişkiyi bilmek, olayları işlerken ve CAnimationVariable öğesinden bir üst animasyon nesnesi almanız gerektiğinde yararlı olabilir. CAnimationVariable:: GetParentAnimationObject kullanın.

## <a name="canimationbaseobjectsetuserdata"></a><a name="setuserdata"></a> CAnimationBaseObject:: SetUserData

Kullanıcı tanımlı verileri ayarlar.

```cpp
void SetUserData (DWORD dwUserData);
```

### <a name="parameters"></a>Parametreler

*dwUserData*<br/>
Özel verileri belirtir.

### <a name="remarks"></a>Açıklamalar

Özel verileri bir animasyon nesnesiyle ilişkilendirmek için bu yöntemi kullanın. Bu veriler, daha sonra GetUserData tarafından çalışma zamanında alınabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
