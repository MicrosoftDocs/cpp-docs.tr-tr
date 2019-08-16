---
title: CAnimationVariable sınıfı
ms.date: 03/27/2019
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
helpviewer_keywords:
- CAnimationVariable [MFC], CAnimationVariable
- CAnimationVariable [MFC], AddTransition
- CAnimationVariable [MFC], ApplyTransitions
- CAnimationVariable [MFC], ClearTransitions
- CAnimationVariable [MFC], Create
- CAnimationVariable [MFC], CreateTransitions
- CAnimationVariable [MFC], EnableIntegerValueChangedEvent
- CAnimationVariable [MFC], EnableValueChangedEvent
- CAnimationVariable [MFC], GetDefaultValue
- CAnimationVariable [MFC], GetParentAnimationObject
- CAnimationVariable [MFC], GetValue
- CAnimationVariable [MFC], GetVariable
- CAnimationVariable [MFC], SetDefaultValue
- CAnimationVariable [MFC], SetParentAnimationObject
- CAnimationVariable [MFC], m_bAutodestroyTransitions
- CAnimationVariable [MFC], m_dblDefaultValue
- CAnimationVariable [MFC], m_lstTransitions
- CAnimationVariable [MFC], m_pParentObject
- CAnimationVariable [MFC], m_variable
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
ms.openlocfilehash: b6767ed42d66aff467ef36bd2a7b5234ad181ced
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507538"
---
# <a name="canimationvariable-class"></a>CAnimationVariable sınıfı

Bir animasyon değişkenini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationVariable;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariable:: CAnimationVariable](#canimationvariable)|Bir animasyon değişken nesnesi oluşturur.|
|[CAnimationVariable:: ~ CAnimationVariable](#_dtorcanimationvariable)|Yok edicisi. Bir CAnimationVariable nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariable:: AddTransition](#addtransition)|Bir geçiş ekler.|
|[CAnimationVariable:: Applygeçişleri](#applytransitions)|İç listedeki geçişleri film şeridine ekler.|
|[CAnimationVariable:: Cleargeçişler](#cleartransitions)|Geçişleri temizler.|
|[CAnimationVariable:: Create](#create)|Temel animasyon değişkeni COM nesnesini oluşturur.|
|[CAnimationVariable:: Creategeçişler](#createtransitions)|Bu animasyon değişkenine uygulanacak tüm geçişleri oluşturur.|
|[CAnimationVariable:: EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|IntegerValueChanged olayını etkinleştirilir veya devre dışı bırakır.|
|[CAnimationVariable:: EnableValueChangedEvent](#enablevaluechangedevent)|ValueChanged olayını etkinleştirilir veya devre dışı bırakır.|
|[CAnimationVariable:: GetDefaultValue](#getdefaultvalue)|Varsayılan değeri döndürür.|
|[CAnimationVariable:: GetParentAnimationObject](#getparentanimationobject)|Üst animasyon nesnesini döndürür.|
|[CAnimationVariable:: GetValue](#getvalue)|Fazla Yüklendi. Animasyon değişkeninin geçerli değerini döndürür.|
|[CAnimationVariable:: GetVariable](#getvariable)|IUIAnimationVariable COM nesnesine bir işaretçi döndürür.|
|[CAnimationVariable:: SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar ve IUIAnimationVariable COM nesnesini yayınlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariable:: SetParentAnimationObject](#setparentanimationobject)|Animasyon değişkeni ve animasyon nesnesi arasındaki ilişkiyi ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariable:: m_bAutodestroyTransitions](#m_bautodestroytransitions)|İlgili geçiş nesnelerinin silinip silinmeyeceğini belirtir.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariable:: m_dblDefaultValue](#m_dbldefaultvalue)|IUIAnimationVariable öğesine yayılan varsayılan değeri belirtir.|
|[CAnimationVariable:: m_lstTransitions](#m_lsttransitions)|Bu animasyon değişkenine animasyon uygulayan geçişlerin bir listesini içerir.|
|[CAnimationVariable:: m_pParentObject](#m_pparentobject)|Bu animasyon değişkenini kapsülleyen animasyon nesnesine yönelik bir işaretçi.|
|[CAnimationVariable:: m_variable](#m_variable)|IUIAnimationVariable COM nesnesine bir işaretçi depolar. COM nesnesi henüz oluşturulmadıysa veya oluşturma başarısız olduysa NULL.|

## <a name="remarks"></a>Açıklamalar

CAnimationVariable sınıfı IUIAnimationVariable COM nesnesini kapsüller. Ayrıca film şeridinde animasyon değişkenine uygulanacak geçişlerin listesini de barındırır. CAnimationVariable nesneleri animasyon nesnelerine katıştırılır ve bu, bir uygulamada animasyonlu bir değer, nokta, boyut, renk ve dikdörtgen temsil edebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAnimationVariable`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

##  <a name="_dtorcanimationvariable"></a>CAnimationVariable:: ~ CAnimationVariable

Yok edicisi. Bir CAnimationVariable nesnesi yok edildiğinde çağırılır.

```
virtual ~CAnimationVariable();
```

##  <a name="addtransition"></a>CAnimationVariable:: AddTransition

Bir geçiş ekler.

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Parametreler

*pTransition*<br/>
Eklenecek geçişe yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, animasyon değişkenine uygulanacak geçişlerin iç listesine bir geçiş eklemek için çağrılır. Bu liste, bir animasyon zamanlandığı zaman temizlenmelidir.

##  <a name="applytransitions"></a>CAnimationVariable:: Applygeçişleri

İç listedeki geçişleri film şeridine ekler.

```
void ApplyTransitions(
    CAnimationController* pController,
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parametreler

*pController*<br/>
Üst animasyon denetleyicisine yönelik bir işaretçi.

*pStoryboard*<br/>
Görsel taslağa yönelik bir işaretçi.

*bDependOnKeyframes*<br/>
Bu yöntemin, ana karelere bağlı olan geçişleri eklemesi gerekiyorsa TRUE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç listeden film şeridine geçiş ekler. Ana karelerle ilgili olmayan geçişler eklemek ve ana karelere bağlı geçişler eklemek için en üst düzey koddan birkaç kez çağrılır. Temeldeki animasyon değişkeni COM nesnesi oluşturulmadıysa, bu yöntem bu aşamada oluşturur.

##  <a name="canimationvariable"></a>CAnimationVariable:: CAnimationVariable

Bir animasyon değişken nesnesi oluşturur.

```
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```

### <a name="parameters"></a>Parametreler

*dblDefaultValue*<br/>
Varsayılan değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Bir animasyon değişkeni nesnesi oluşturur ve varsayılan değerini ayarlar. Bir değişken canlandırılmaz veya canlandırılamıyorum, varsayılan değer kullanılır.

##  <a name="cleartransitions"></a>CAnimationVariable:: Cleargeçişler

Geçişleri temizler.

```
void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Parametreler

*bAutodestroy*<br/>
Bu yöntemin geçiş nesnelerini silip silmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tüm geçişleri iç geçiş listesinden kaldırır. BAutodestroy TRUE ise veya m_bAutodestroyTransitions TRUE ise, geçişler silinir. Aksi takdirde, çağıran geçiş nesnelerini serbest bırakabilir.

##  <a name="create"></a>CAnimationVariable:: Create

Temel animasyon değişkeni COM nesnesini oluşturur.

```
virtual BOOL Create(IUIAnimationManager* pManager);
```

### <a name="parameters"></a>Parametreler

*pManager*<br/>
Animasyon Yöneticisi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Animasyon değişkeni başarıyla oluşturulduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, temel alınan animasyon değişkeni COM nesnesini oluşturur ve varsayılan değerini ayarlar.

##  <a name="createtransitions"></a>CAnimationVariable:: Creategeçişler

Bu animasyon değişkenine uygulanacak tüm geçişleri oluşturur.

```
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Standart geçişlerin kitaplığını tanımlayan [ıuıanimationgeçişli Tionlibrary arabirimine](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçişler başarıyla oluşturulduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, değişkenin iç geçiş listesine eklenmiş geçişler oluşturması gerektiğinde Framework tarafından çağırılır.

##  <a name="enableintegervaluechangedevent"></a>CAnimationVariable:: EnableIntegerValueChangedEvent

IntegerValueChanged olayını etkinleştirilir veya devre dışı bırakır.

```
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pController*<br/>
Üst denetleyiciye yönelik bir işaretçi.

*bEnable*<br/>
TRUE-olayı etkinleştir, yanlış-olayı devre dışı bırak.

### <a name="remarks"></a>Açıklamalar

ValueChanged olayı etkinleştirildiğinde Framework, CAnimationController:: OnAnimationIntegerValueChanged sanal yöntemini çağırır. Bu olayı işlemek için CAnimationController sınıfından türetilmiş bir sınıfta geçersiz kılmanız gerekir. Bu yöntem, Animasyon değişkeninin tamsayı değeri her değiştirildiğinde çağrılır.

##  <a name="enablevaluechangedevent"></a>CAnimationVariable:: EnableValueChangedEvent

ValueChanged olayını etkinleştirilir veya devre dışı bırakır.

```
void EnableValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pController*<br/>
Üst denetleyiciye yönelik bir işaretçi.

*bEnable*<br/>
TRUE-olayı etkinleştir, yanlış-olayı devre dışı bırak.

### <a name="remarks"></a>Açıklamalar

ValueChanged olayı etkinleştirildiğinde Framework, CAnimationController:: OnAnimationValueChanged sanal yöntemini çağırır. Bu olayı işlemek için CAnimationController sınıfından türetilmiş bir sınıfta geçersiz kılmanız gerekir. Bu yöntem, Animasyon değişkeninin değeri her değiştirildiğinde çağrılır.

##  <a name="getdefaultvalue"></a>CAnimationVariable:: GetDefaultValue

Varsayılan değeri döndürür.

```
DOUBLE GetDefaultValue() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan değer.

### <a name="remarks"></a>Açıklamalar

Animasyon değişkeninin varsayılan değerini elde etmek için bu işlevi kullanın. Varsayılan değer oluşturucuda veya SetDefaultValue yöntemiyle ayarlanabilir.

##  <a name="getparentanimationobject"></a>CAnimationVariable:: GetParentAnimationObject

Üst animasyon nesnesini döndürür.

```
CAnimationBaseObject* GetParentAnimationObject();
```

### <a name="return-value"></a>Dönüş Değeri

İlişki oluşturulmuşsa üst animasyon nesnesine bir işaretçi, aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir üst animasyon nesnesine (kapsayıcı) yönelik bir işaretçi almak için çağrılabilir.

##  <a name="getvalue"></a>CAnimationVariable:: GetValue

Animasyon değişkeninin geçerli değerini döndürür.

```
HRESULT GetValue(DOUBLE& dblValue);
HRESULT GetValue(INT32& nValue);
```

### <a name="parameters"></a>Parametreler

*dblValue*<br/>
Animasyon değişkeninin geçerli değeri.

*nDeğer*<br/>
Animasyon değişkeninin geçerli değeri.

### <a name="return-value"></a>Dönüş Değeri

Değer başarıyla alınmışsa veya temeldeki animasyon değişkeni oluşturulmadıysa S_OK. Aksi takdirde HRESULT hata kodu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Animasyon değişkeninin geçerli değerini almak için çağrılabilir. Temel alınan COM nesnesi oluşturulmadıysa, işlev döndüğünde dblValue varsayılan bir değer içerir.

##  <a name="getvariable"></a>CAnimationVariable:: GetVariable

IUIAnimationVariable COM nesnesine bir işaretçi döndürür.

```
IUIAnimationVariable* GetVariable();
```

### <a name="return-value"></a>Dönüş Değeri

IUIAnimationVariable COM nesnesine yönelik geçerli bir işaretçi ya da animasyon değişkeni oluşturulmadıysa veya oluşturulanmadıysa NULL.

### <a name="remarks"></a>Açıklamalar

Temel IUIAnimationVariable COM nesnesine erişmek ve gerekirse yöntemlerini doğrudan çağırmak için bu işlevi kullanın.

##  <a name="m_bautodestroytransitions"></a>CAnimationVariable:: m_bAutodestroyTransitions

İlgili geçiş nesnelerinin silinip silinmeyeceğini belirtir.

```
BOOL m_bAutodestroyTransitions;
```

### <a name="remarks"></a>Açıklamalar

Geçiş nesnelerinin iç geçiş listesinden kaldırıldıklarında silinmesini zorlamak için bu değeri TRUE olarak ayarlayın. Bu değer FALSE ise, uygulama çağırarak geçişler silinmelidir. Geçişler listesi, bir animasyon zamanlandıktan sonra her zaman temizlenir. Varsayılan değer FALSE 'dur.

##  <a name="m_dbldefaultvalue"></a>CAnimationVariable:: m_dblDefaultValue

IUIAnimationVariable öğesine yayılan varsayılan değeri belirtir.

```
DOUBLE m_dblDefaultValue;
```

##  <a name="m_lsttransitions"></a>CAnimationVariable:: m_lstTransitions

Bu animasyon değişkenine animasyon uygulayan geçişlerin bir listesini içerir.

```
CObList m_lstTransitions;
```

##  <a name="m_pparentobject"></a>CAnimationVariable:: m_pParentObject

Bu animasyon değişkenini kapsülleyen animasyon nesnesine yönelik bir işaretçi.

```
CAnimationBaseObject* m_pParentObject;
```

##  <a name="m_variable"></a>CAnimationVariable:: m_variable

IUIAnimationVariable COM nesnesine bir işaretçi depolar. COM nesnesi henüz oluşturulmadıysa veya oluşturma başarısız olduysa NULL.

```
ATL::CComPtr<IUIAnimationVariable> m_variable;
```

##  <a name="setdefaultvalue"></a>CAnimationVariable:: SetDefaultValue

Varsayılan değeri ayarlar ve IUIAnimationVariable COM nesnesini yayınlar.

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Parametreler

*dblDefaultValue*<br/>
Yeni varsayılan değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan değeri sıfırlamak için bu yöntemi kullanın. Bu yöntem, iç IUIAnimationVariable COM nesnesini serbest bırakır, bu nedenle animasyon değişkeni yeniden oluşturulduğunda, temel alınan COM nesnesi yeni varsayılan değeri alır. Varsayılan değer, animasyon değişkenini temsil eden COM nesnesi oluşturulmadıysa veya değişken animasyon yoksa, GetValue tarafından döndürülür.

##  <a name="setparentanimationobject"></a>CAnimationVariable:: SetParentAnimationObject

Animasyon değişkeni ve animasyon nesnesi arasındaki ilişkiyi ayarlar.

```
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```

### <a name="parameters"></a>Parametreler

*pParentObject*<br/>
Bu değişkeni içeren bir animasyon nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir animasyon değişkeni ve onu kapsülleyen bir animasyon nesnesi arasında bire bir ilişki kurmak için dahili olarak çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
