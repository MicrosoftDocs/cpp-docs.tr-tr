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
ms.openlocfilehash: 42fd3ddc504e85ba3f69588bee54c6540b628129
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338278"
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
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|Bir animasyon değişkenini nesne oluşturur.|
|[CAnimationVariable:: ~ CAnimationVariable](#_dtorcanimationvariable)|Yıkıcı. CAnimationVariable nesne yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariable::AddTransition](#addtransition)|Bir geçiş ekler.|
|[CAnimationVariable::ApplyTransitions](#applytransitions)|Geçişler, film şeridi için iç listeden ekler.|
|[CAnimationVariable::ClearTransitions](#cleartransitions)|Geçişleri temizler.|
|[CAnimationVariable::Create](#create)|Temel animasyon değişken COM nesnesi oluşturur.|
|[CAnimationVariable::CreateTransitions](#createtransitions)|Bu animasyon değişkenin uygulanacak tüm geçişler oluşturur.|
|[CAnimationVariable::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Etkinleştirir veya IntegerValueChanged olay devre dışı bırakır.|
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|Etkinleştirir veya ValueChanged olay devre dışı bırakır.|
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|Varsayılan değeri döndürür.|
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|Üst döndürür animasyon nesne.|
|[CAnimationVariable::GetValue](#getvalue)|Fazla Yüklendi. Animasyon değişkeninin geçerli değerini döndürür.|
|[CAnimationVariable::GetVariable](#getvariable)|IUIAnimationVariable COM nesnesine bir işaretçi döndürür.|
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|Varsayılan değer olarak ayarlar ve IUIAnimationVariable COM nesnesi serbest bırakır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|Bir animasyon değişkenini ve animasyon nesne arasındaki ilişkiyi ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|İlgili geçiş nesneleri silinip silinmeyeceğini belirtir.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|İçin IUIAnimationVariable yayılır varsayılan değeri belirtir.|
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|Bu bir animasyon değişkenini animasyon geçişleri bir listesini içerir.|
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|Bu bir animasyon değişkenini kapsülleyen bir animasyon nesnenin bir işaretçi.|
|[CAnimationVariable::m_variable](#m_variable)|IUIAnimationVariable COM nesnesine bir işaretçi depolar. COM Nesne henüz oluşturulmadı veya oluşturma başarısız olursa NULL.|

## <a name="remarks"></a>Açıklamalar

CAnimationVariable sınıfı IUIAnimationVariable COM nesnesi kapsüller. Ayrıca, bir film şeridinde animasyon değişkeninde uygulanacak geçişleri listesini tutar. Bir uygulama bir animasyonlu değeri, noktası, boyutunu, rengini ve dikdörtgen gösterebilir animasyon nesnelere katıştırılmış CAnimationVariable nesneleri.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CAnimationVariable`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="_dtorcanimationvariable"></a>  CAnimationVariable:: ~ CAnimationVariable

Yıkıcı. CAnimationVariable nesne yok ediliyorken çağırılır.

```
virtual ~CAnimationVariable();
```

##  <a name="addtransition"></a>  CAnimationVariable::AddTransition

Bir geçiş ekler.

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Parametreler

*pTransition*<br/>
Bir geçiş eklemek için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir geçiş animasyon değişkene uygulanacak geçişleri iç listesine eklemek için çağrılır. Bu liste, animasyon zamanlandıysa temizlenmiş olması gerekir.

##  <a name="applytransitions"></a>  CAnimationVariable::ApplyTransitions

Geçişler, film şeridi için iç listeden ekler.

```
void ApplyTransitions(
    CAnimationController* pController,
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parametreler

*pController*<br/>
Üst animasyon denetleyicisini bir işaretçi.

*pStoryboard*<br/>
Görsel taslak için bir işaretçi.

*bDependOnKeyframes*<br/>
TRUE, bu yöntem, üzerinde ana kareleri bağımlı geçişleri eklemeniz gerekir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, film şeridi için iç listeden geçişleri ekler. Ana kareleri üzerinde bağlıdır ve ana kareleri üzerinde bağlı geçiş ekleme geçişleri eklemek için üst düzey kod birkaç kez çağrılır. Temel animasyon değişkenini COM nesnesi oluşturulmadı, bu yöntem bu aşamada oluşturur.

##  <a name="canimationvariable"></a>  CAnimationVariable::CAnimationVariable

Bir animasyon değişkenini nesne oluşturur.

```
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```

### <a name="parameters"></a>Parametreler

*dblDefaultValue*<br/>
Varsayılan değer belirtir.

### <a name="remarks"></a>Açıklamalar

Bir animasyon değişkenini nesne oluşturur ve varsayılan değerini ayarlar. Bir değişken değil animasyon veya hareketlendirilemeyebilir bir varsayılan değer kullanılır.

##  <a name="cleartransitions"></a>  CAnimationVariable::ClearTransitions

Geçişleri temizler.

```
void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Parametreler

*bAutodestroy*<br/>
Bu yöntem geçiş nesneleri silin olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tüm geçişler geçişleri iç listesinden kaldırır. BAutodestroy doğru veya m_bAutodestroyTransitions true'dur geçişleri silinir. Aksi takdirde çağıran geçiş nesneleri serbest bırakma.

##  <a name="create"></a>  CAnimationVariable::Create

Temel animasyon değişken COM nesnesi oluşturur.

```
virtual BOOL Create(IUIAnimationManager* pManager);
```

### <a name="parameters"></a>Parametreler

*pManager*<br/>
Animasyon Yöneticisi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Animasyon değişkenin başarıyla oluşturulursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, temel alınan animasyon değişkenini COM nesnesi oluşturur ve varsayılan değerini ayarlar.

##  <a name="createtransitions"></a>  CAnimationVariable::CreateTransitions

Bu animasyon değişkenin uygulanacak tüm geçişler oluşturur.

```
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Bir işaretçi bir [IUIAnimationTransitionLibrary arabirimi](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), standart geçişleri kitaplığını tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulduysa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem değişkenin iç geçiş listesine eklenmiş olan geçiş oluşturmak gerektiğinde framework tarafından çağırılır.

##  <a name="enableintegervaluechangedevent"></a>  CAnimationVariable::EnableIntegerValueChangedEvent

Etkinleştirir veya IntegerValueChanged olay devre dışı bırakır.

```
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pController*<br/>
Üst denetleyici için bir işaretçi.

*bSistemlerde*<br/>
TRUE - olay FALSE - devre dışı bırakma olay etkinleştirin.

### <a name="remarks"></a>Açıklamalar

ValueChanged olay etkinleştirildiğinde framework CAnimationController::OnAnimationIntegerValueChanged sanal bir yöntem çağırır. Bu olayı işlemek için CAnimationController türetilen bir sınıfta geçersiz gerekir. Animasyon değişkeninin tamsayı değeri değiştirildiğinde, bu yöntem çağrılır.

##  <a name="enablevaluechangedevent"></a>  CAnimationVariable::EnableValueChangedEvent

Etkinleştirir veya ValueChanged olay devre dışı bırakır.

```
void EnableValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*pController*<br/>
Üst denetleyici için bir işaretçi.

*bSistemlerde*<br/>
TRUE - olay FALSE - devre dışı bırakma olay etkinleştirin.

### <a name="remarks"></a>Açıklamalar

ValueChanged olay etkinleştirildiğinde framework CAnimationController::OnAnimationValueChanged sanal bir yöntem çağırır. Bu olayı işlemek için CAnimationController türetilen bir sınıfta geçersiz gerekir. Animasyon değişkeninin değeri değiştirildiğinde, bu yöntem çağrılır.

##  <a name="getdefaultvalue"></a>  CAnimationVariable::GetDefaultValue

Varsayılan değeri döndürür.

```
DOUBLE GetDefaultValue() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan değeri.

### <a name="remarks"></a>Açıklamalar

Animasyon değişkenin varsayılan değeri elde etmek için bu işlevi kullanın. Varsayılan değer, oluşturucu veya SetDefaultValue yöntemi tarafından ayarlanabilir.

##  <a name="getparentanimationobject"></a>  CAnimationVariable::GetParentAnimationObject

Üst döndürür animasyon nesne.

```
CAnimationBaseObject* GetParentAnimationObject();
```

### <a name="return-value"></a>Dönüş Değeri

İlişki kuruldu, üst animasyon nesnesine bir işaretçi bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir işaretçiyi bir üst animasyon nesneye (kapsayıcı) almak için çağrılabilir.

##  <a name="getvalue"></a>  CAnimationVariable::GetValue

Animasyon değişkeninin geçerli değerini döndürür.

```
HRESULT GetValue(DOUBLE& dblValue);
HRESULT GetValue(INT32& nValue);
```

### <a name="parameters"></a>Parametreler

*dblValue*<br/>
Animasyon değişkenin geçerli değeri.

*nDeğer*<br/>
Animasyon değişkenin geçerli değeri.

### <a name="return-value"></a>Dönüş Değeri

S_OK değeri başarıyla edinilen ya da temel alınan animasyon değişkenini oluşturulmadı. Aksi takdirde HRESULT hata kodu.

### <a name="remarks"></a>Açıklamalar

Animasyon değişkeninin geçerli değerini almak için bu yöntem çağrılabilir. COM nesnesini oluşturulmadı, dblValue işlevi döndüğünde varsayılan bir değer içerir.

##  <a name="getvariable"></a>  CAnimationVariable::GetVariable

IUIAnimationVariable COM nesnesine bir işaretçi döndürür.

```
IUIAnimationVariable* GetVariable();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi IUIAnimationVariable COM nesnesi ya da NULL animasyon değişkenini oluşturulmadı veya oluşturulamıyor.

### <a name="remarks"></a>Açıklamalar

Temel alınan IUIAnimationVariable COM nesnesi erişmek ve gerekirse kendi yöntemleri doğrudan çağırmak için bu işlevi kullanın.

##  <a name="m_bautodestroytransitions"></a>  CAnimationVariable::m_bAutodestroyTransitions

İlgili geçiş nesneleri silinip silinmeyeceğini belirtir.

```
BOOL m_bAutodestroyTransitions;
```

### <a name="remarks"></a>Açıklamalar

Geçişleri iç listesinden kaldırılmakta olan geçiş nesneleri zorla silinmesini true bu değere ayarlanır. Bu değer FALSE ise uygulama çağırarak geçişi silinmelidir. Geçişleri listesini, her zaman bir animasyon zamanlandıktan sonra temizlenir. Varsayılan değer FALSE olur.

##  <a name="m_dbldefaultvalue"></a>  CAnimationVariable::m_dblDefaultValue

İçin IUIAnimationVariable yayılır varsayılan değeri belirtir.

```
DOUBLE m_dblDefaultValue;
```

##  <a name="m_lsttransitions"></a>  CAnimationVariable::m_lstTransitions

Bu bir animasyon değişkenini animasyon geçişleri bir listesini içerir.

```
CObList m_lstTransitions;
```

##  <a name="m_pparentobject"></a>  CAnimationVariable::m_pParentObject

Bu bir animasyon değişkenini kapsülleyen bir animasyon nesnenin bir işaretçi.

```
CAnimationBaseObject* m_pParentObject;
```

##  <a name="m_variable"></a>  CAnimationVariable::m_variable

IUIAnimationVariable COM nesnesine bir işaretçi depolar. COM Nesne henüz oluşturulmadı veya oluşturma başarısız olursa NULL.

```
ATL::CComPtr<IUIAnimationVariable> m_variable;
```

##  <a name="setdefaultvalue"></a>  CAnimationVariable::SetDefaultValue

Varsayılan değer olarak ayarlar ve IUIAnimationVariable COM nesnesi serbest bırakır.

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Parametreler

*dblDefaultValue*<br/>
Yeni varsayılan değerini belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan değeri sıfırlamak için bu yöntemi kullanın. Animasyon değişkenin yeniden oluşturulduğunda bu yöntem iç IUIAnimationVariable COM nesnesi, bu nedenle sürümleri, yeni varsayılan değer COM nesnesini alır. Varsayılan değer, animasyon değişkenini temsil eden bir COM nesnesi oluşturulmadı veya değişkeni değil animasyonlu GetValue tarafından döndürülür.

##  <a name="setparentanimationobject"></a>  CAnimationVariable::SetParentAnimationObject

Bir animasyon değişkenini ve animasyon nesne arasındaki ilişkiyi ayarlar.

```
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```

### <a name="parameters"></a>Parametreler

*pParentObject*<br/>
Bu değişken içeren bir animasyon nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir animasyon değişkenini ve onu bir animasyon nesnesini arasında bire bir ilişki kurmak için dahili olarak çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
