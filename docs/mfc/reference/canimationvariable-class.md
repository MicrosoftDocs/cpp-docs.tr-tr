---
title: CAnimationVariable Sınıfı
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
ms.openlocfilehash: 51cc4732ee8ad5f954e5bd758484cec74cf00fe6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377047"
---
# <a name="canimationvariable-class"></a>CAnimationVariable Sınıfı

Animasyon değişkenini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationVariable;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|Animasyon değişken nesnesi oluşturuyor.|
|[CAnimationVariable::~CAnimationVariable](#_dtorcanimationvariable)|Yıkıcı. CAnimationVariable nesnesi yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationVariable::AddTransition](#addtransition)|Bir geçiş ekler.|
|[CAnimationVariable::Geçişuygula](#applytransitions)|Dahili listeden film şeridine geçişler ekler.|
|[CAnimationVariable::ClearTransitions](#cleartransitions)|Geçişleri temizler.|
|[CAnimationVariable::Oluştur](#create)|Altta yatan animasyon değişkeni COM nesnesini oluşturur.|
|[CAnimationVariable::CreateTransitions](#createtransitions)|Bu animasyon değişkenine uygulanacak tüm geçişleri oluşturur.|
|[CAnimationVariable::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|IntegerValueChanged olayını etkinleştirir veya devre dışı kılabilir.|
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|ValueChanged olayını etkinleştirer veya devre dışı kılabilir.|
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|Varsayılan değeri verir.|
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|Üst animasyon nesnesini döndürür.|
|[CAnimationVariable::GetValue](#getvalue)|Fazla Yüklendi. Animasyon değişkeninin geçerli değerini verir.|
|[CAnimationVariable::GetVariable](#getvariable)|IUIAnimationVariable COM nesnesine bir işaretçi döndürür.|
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar ve IUIAnimationVariable COM nesnesi salgılar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|Animasyon değişkeni ile animasyon nesnesi arasındaki ilişkiyi ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationDeğişken::m_bAutodestroyTransitions](#m_bautodestroytransitions)|İlişkili geçiş nesnelerinin silinip silinmeyeceğini belirtir.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|IUIAnimationVariable'e yayılan varsayılan değeri belirtir.|
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|Bu animasyon değişkenini canlandıran geçişlerin listesini içerir.|
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|Bu animasyon değişkenini kapsülleyen bir animasyon nesnesine işaretçi.|
|[CAnimationDeğişken::m_variable](#m_variable)|IUIAnimationVariable COM nesnesine bir işaretçi depolar. COM nesnesi henüz oluşturulmamışsa veya oluşturma başarısız olduysa NULL.|

## <a name="remarks"></a>Açıklamalar

CAnimationVariable sınıfı IUIAnimationVariable COM nesnesini kapsüller. Ayrıca, bir film şeridindeki animasyon değişkenine uygulanacak geçişlerin bir listesini de tutar. CAnimationVariable nesneleri animasyon nesneleri, bir uygulamada animasyonlu bir değer, nokta, boyut, renk ve dikdörtgen temsil edebilir gömülür.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAnimationVariable`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationvariablecanimationvariable"></a><a name="_dtorcanimationvariable"></a>CAnimationVariable::~CAnimationVariable

Yıkıcı. CAnimationVariable nesnesi yok edilirken çağrılır.

```
virtual ~CAnimationVariable();
```

## <a name="canimationvariableaddtransition"></a><a name="addtransition"></a>CAnimationVariable::AddTransition

Bir geçiş ekler.

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Parametreler

*pGeçiş*<br/>
Eklemek için bir geçiş için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, animasyon değişkenine uygulanacak iç geçişler listesine bir geçiş eklemek için adlandırılır. Animasyon zamanlandığında bu liste temizlenmelidir.

## <a name="canimationvariableapplytransitions"></a><a name="applytransitions"></a>CAnimationVariable::Geçişuygula

Dahili listeden film şeridine geçişler ekler.

```
void ApplyTransitions(
    CAnimationController* pController,
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parametreler

*pDenetleyici*<br/>
Üst animasyon denetleyicisine işaretçi.

*pStoryboard*<br/>
Film şeridi için bir işaretçi.

*bDependOnKeyframes*<br/>
DOĞRU, bu yöntem anahtar karelere bağlı geçişler eklemek gerekiyorsa.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iç listeden film şeridine geçişler ekler. Anahtar karelere bağlı olmayan geçişler eklemek ve anahtar karelere bağlı geçişler eklemek için üst düzey koddan birkaç kez çağrılır. Altta yatan animasyon değişkeni COM nesnesi oluşturulmazsa, bu yöntem bu aşamada oluşturur.

## <a name="canimationvariablecanimationvariable"></a><a name="canimationvariable"></a>CAnimationVariable::CAnimationVariable

Animasyon değişken nesnesi oluşturuyor.

```
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```

### <a name="parameters"></a>Parametreler

*dblDefaultValue*<br/>
Varsayılan değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon değişken nesnesi oluşturuyor ve varsayılan değerini ayarlar. Varsayılan değer, bir değişken animasyonlu olmadığında veya canlandırılamadıklarında kullanılır.

## <a name="canimationvariablecleartransitions"></a><a name="cleartransitions"></a>CAnimationVariable::ClearTransitions

Geçişleri temizler.

```
void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Parametreler

*bAutodestroy*<br/>
Bu yöntemin geçiş nesnelerini silip silmeyeceğini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tüm geçişleri iç geçişler listesinden kaldırır. bAutodestroy TRUE ise veya m_bAutodestroyTransitions DOĞRUise, geçişler silinir. Aksi takdirde arayan geçiş nesneleri yer almalıdır.

## <a name="canimationvariablecreate"></a><a name="create"></a>CAnimationVariable::Oluştur

Altta yatan animasyon değişkeni COM nesnesini oluşturur.

```
virtual BOOL Create(IUIAnimationManager* pManager);
```

### <a name="parameters"></a>Parametreler

*pManager*<br/>
Animasyon yöneticisi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Animasyon değişkeni başarıyla oluşturulduysa TRUE; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, temel animasyon değişkeni COM nesnesini oluşturur ve varsayılan değerini ayarlar.

## <a name="canimationvariablecreatetransitions"></a><a name="createtransitions"></a>CAnimationVariable::CreateTransitions

Bu animasyon değişkenine uygulanacak tüm geçişleri oluşturur.

```
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametreler

*pKütüphane*<br/>
Standart geçişler kitaplığını tanımlayan [IUIAnimationTransitionLibrary arabirimine](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçişler başarıyla oluşturulduysa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, değişkenin iç geçişler listesine eklenen geçişler oluşturması gerektiğinde çerçeve tarafından çağrılır.

## <a name="canimationvariableenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a>CAnimationVariable::EnableIntegerValueChangedEvent

IntegerValueChanged olayını etkinleştirir veya devre dışı kılabilir.

```
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pDenetleyici*<br/>
Üst denetleyiciiçin bir işaretçi.

*bEtkinleştir*<br/>
TRUE - olay etkinleştirmek, FALSE - olay devre dışı.

### <a name="remarks"></a>Açıklamalar

ValueChanged olayı etkinleştirildiğinde, çerçeve sanal yöntem cAnimationController çağırır::OnAnimationIntegerValueChanged. Bu olayı işlemek için CAnimationController'dan türetilen bir sınıfta geçersiz kılmanız gerekir. Bu yöntem, animasyon değişkeninin tamsayı değeri her değiştirilse çağrılır.

## <a name="canimationvariableenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a>CAnimationVariable::EnableValueChangedEvent

ValueChanged olayını etkinleştirer veya devre dışı kılabilir.

```
void EnableValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pDenetleyici*<br/>
Üst denetleyiciiçin bir işaretçi.

*bEtkinleştir*<br/>
TRUE - olay etkinleştirmek, FALSE - olay devre dışı.

### <a name="remarks"></a>Açıklamalar

ValueChanged olayı etkinleştirildiğinde, çerçeve sanal yöntem CAnimationController çağırır::OnAnimationValueChanged. Bu olayı işlemek için CAnimationController'dan türetilen bir sınıfta geçersiz kılmanız gerekir. Bu yöntem, animasyon değişkeninin değeri her değiştirilse çağrılır.

## <a name="canimationvariablegetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationVariable::GetDefaultValue

Varsayılan değeri verir.

```
DOUBLE GetDefaultValue() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan değer.

### <a name="remarks"></a>Açıklamalar

Animasyon değişkeninin varsayılan değerini elde etmek için bu işlevi kullanın. Varsayılan değer oluşturucu veya SetDefaultValue yöntemi ile ayarlanabilir.

## <a name="canimationvariablegetparentanimationobject"></a><a name="getparentanimationobject"></a>CAnimationVariable::GetParentAnimationObject

Üst animasyon nesnesini döndürür.

```
CAnimationBaseObject* GetParentAnimationObject();
```

### <a name="return-value"></a>Dönüş Değeri

İlişki kurulmuşsa, üst animasyon nesnesine işaretçi, aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir ana animasyon nesnesi (bir kapsayıcı) için bir işaretçi almak için çağrılabilir.

## <a name="canimationvariablegetvalue"></a><a name="getvalue"></a>CAnimationVariable::GetValue

Animasyon değişkeninin geçerli değerini verir.

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

değer başarıyla elde edilmişse veya temel animasyon değişkeni oluşturulmazsa S_OK. Aksi takdirde HRESULT hata kodu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem animasyon değişkeninin geçerli değerini almak için çağrılabilir. Temel COM nesnesi oluşturulmamadıysa, işlev döndüğünde dblValue varsayılan bir değer içerir.

## <a name="canimationvariablegetvariable"></a><a name="getvariable"></a>CAnimationVariable::GetVariable

IUIAnimationVariable COM nesnesine bir işaretçi döndürür.

```
IUIAnimationVariable* GetVariable();
```

### <a name="return-value"></a>Dönüş Değeri

IUIAnimationVariable COM nesnesine veya animasyon değişkeni oluşturulmazsa veya oluşturulamazsa NULL'a geçerli bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Altta yatan IUIAnimationVariable COM nesnesine erişmek ve gerekirse yöntemlerini doğrudan çağırmak için bu işlevi kullanın.

## <a name="canimationvariablem_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a>CAnimationDeğişken::m_bAutodestroyTransitions

İlişkili geçiş nesnelerinin silinip silinmeyeceğini belirtir.

```
BOOL m_bAutodestroyTransitions;
```

### <a name="remarks"></a>Açıklamalar

Geçiş nesnelerinin iç geçişler listesinden çıkarılırken silinmeye zorlamak için bu değeri TRUE olarak ayarlayın. Bu değer FALSE ise geçişler uygulama çağırılarak silinmelidir. Geçiş listesi, animasyon zamanlandıktan sonra her zaman temizlenir. Varsayılan değer FALSE'dur.

## <a name="canimationvariablem_dbldefaultvalue"></a><a name="m_dbldefaultvalue"></a>CAnimationVariable::m_dblDefaultValue

IUIAnimationVariable'e yayılan varsayılan değeri belirtir.

```
DOUBLE m_dblDefaultValue;
```

## <a name="canimationvariablem_lsttransitions"></a><a name="m_lsttransitions"></a>CAnimationVariable::m_lstTransitions

Bu animasyon değişkenini canlandıran geçişlerin listesini içerir.

```
CObList m_lstTransitions;
```

## <a name="canimationvariablem_pparentobject"></a><a name="m_pparentobject"></a>CAnimationVariable::m_pParentObject

Bu animasyon değişkenini kapsülleyen bir animasyon nesnesine işaretçi.

```
CAnimationBaseObject* m_pParentObject;
```

## <a name="canimationvariablem_variable"></a><a name="m_variable"></a>CAnimationDeğişken::m_variable

IUIAnimationVariable COM nesnesine bir işaretçi depolar. COM nesnesi henüz oluşturulmamışsa veya oluşturma başarısız olduysa NULL.

```
ATL::CComPtr<IUIAnimationVariable> m_variable;
```

## <a name="canimationvariablesetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationVariable::SetDefaultValue

Varsayılan değeri ayarlar ve IUIAnimationVariable COM nesnesi salgılar.

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Parametreler

*dblDefaultValue*<br/>
Yeni varsayılan değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan değeri sıfırlamak için bu yöntemi kullanın. Bu yöntem iç IUIAnimationVariable COM nesnesi salgılar, bu nedenle animasyon değişkeni yeniden oluşturulduğunda, temel COM nesnesi yeni varsayılan değeri alır. Animasyon değişkenini temsil eden COM nesnesi oluşturulmazsa veya değişken animasyonlu değilse varsayılan değer GetValue tarafından döndürülür.

## <a name="canimationvariablesetparentanimationobject"></a><a name="setparentanimationobject"></a>CAnimationVariable::SetParentAnimationObject

Animasyon değişkeni ile animasyon nesnesi arasındaki ilişkiyi ayarlar.

```
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```

### <a name="parameters"></a>Parametreler

*pParentObject*<br/>
Bu değişkeni içeren bir animasyon nesnesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir animasyon değişkeni ile onu kapsülleyen bir animasyon nesnesi arasında bire bir ilişki kurmak için dahili olarak adlandırılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
