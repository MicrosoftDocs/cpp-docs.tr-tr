---
title: CBaseTransition sınıfı
ms.date: 11/04/2016
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
helpviewer_keywords:
- CBaseTransition [MFC], CBaseTransition
- CBaseTransition [MFC], AddToStoryboard
- CBaseTransition [MFC], AddToStoryboardAtKeyframes
- CBaseTransition [MFC], Clear
- CBaseTransition [MFC], Create
- CBaseTransition [MFC], GetEndKeyframe
- CBaseTransition [MFC], GetRelatedVariable
- CBaseTransition [MFC], GetStartKeyframe
- CBaseTransition [MFC], GetTransition
- CBaseTransition [MFC], GetType
- CBaseTransition [MFC], IsAdded
- CBaseTransition [MFC], SetKeyframes
- CBaseTransition [MFC], SetRelatedVariable
- CBaseTransition [MFC], m_bAdded
- CBaseTransition [MFC], m_pEndKeyframe
- CBaseTransition [MFC], m_pRelatedVariable
- CBaseTransition [MFC], m_pStartKeyframe
- CBaseTransition [MFC], m_transition
- CBaseTransition [MFC], m_type
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
ms.openlocfilehash: b4c15be574700730e847bce06aaa4a6f82aed4b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539132"
---
# <a name="cbasetransition-class"></a>CBaseTransition sınıfı

Temel bir geçişi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CBaseTransition : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="public-enumerations"></a>Ortak numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[CBaseTransition::TRANSITION_TYPE numaralandırması](#transition_type_enumeration)|Şu anda Windows animasyon API'sı MFC uygulaması tarafından desteklenen geçiş türleri tanımlar.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBaseTransition::CBaseTransition](#cbasetransition)|Temel transtion bir nesne oluşturur.|
|[CBaseTransition:: ~ CBaseTransition](#cbasetransition__~cbasetransition)|Yıkıcı. Bir geçiş nesnesi yok ediliyorken çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|Geçiş için görsel taslak ekler.|
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|Geçiş için görsel taslak ekler.|
|[CBaseTransition::Clear](#clear)|Yayınları IUIAnimationTransition COM nesnesi kapsüllenir.|
|[CBaseTransition::Create](#create)|COM geçişi oluşturur.|
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|Ana kare döndürür başlatın.|
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|İlgili değişkenine bir işaretçi döndürür.|
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|Ana kare döndürür başlatın.|
|[CBaseTransition::GetTransition](#gettransition)|Fazla Yüklendi. Temel alınan COM geçiş nesnesine bir işaretçi döndürür.|
|[CBaseTransition::GetType](#gettype)|Geçiş türü döndürür.|
|[CBaseTransition::IsAdded](#isadded)|Geçiş için görsel taslak eklenip eklenmediğini belirtir.|
|[CBaseTransition::SetKeyframes](#setkeyframes)|Ana kareleri geçiş ayarlar.|
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|Animasyon değişkenin ve geçiş arasında bir ilişki kurar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CBaseTransition::m_bAdded](#m_badded)|Geçiş için görsel taslak eklenip eklenmediğini belirtir.|
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|Geçiş sonuna belirten bir anahtar kare işaretçi depolar.|
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|M_transition içinde depolanan geçişte hareketli animasyon değişkenin bir işaretçi.|
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|Geçiş başlangıcını belirtir ana kare işaretçi depolar.|
|[CBaseTransition::m_transition](#m_transition)|IUIAnimationTransition bir işaretçi depolar. Bir COM Nesne geçiş yoksa NULL oluşturulmadı.|
|[CBaseTransition::m_type](#m_type)|Geçiş türü depolar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf IUIAnimationTransition arabirimini kapsüller ve tüm geçişler için temel sınıf olarak görev yapar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CBaseTransition`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="_dtorcbasetransition"></a>  CBaseTransition:: ~ CBaseTransition

Yıkıcı. Bir geçiş nesnesi yok ediliyorken çağırılır.

```
virtual ~CBaseTransition();
```

##  <a name="addtostoryboard"></a>  CBaseTransition::AddToStoryboard

Geçiş için görsel taslak ekler.

```
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
İlgili değişkeni animasyon uygular, film şeridi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

TRUE, geçiş için görsel taslak başarıyla eklendi.

### <a name="remarks"></a>Açıklamalar

Görsel taslak ilgili değişkeninde geçişi uygular. Bu film şeridini bu değişkende uygulanan ilk geçiş buysa, geçiş film şeridi başlangıcında başlar. Aksi takdirde, geçiş değişkenine en son eklenen geçiş eklenir.

##  <a name="addtostoryboardatkeyframes"></a>  CBaseTransition::AddToStoryboardAtKeyframes

Geçiş için görsel taslak ekler.

```
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
İlgili değişkeni animasyon uygular, film şeridi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

TRUE, geçiş için görsel taslak başarıyla eklendi.

### <a name="remarks"></a>Açıklamalar

Görsel taslak ilgili değişkeninde geçişi uygular. Başlangıç ana kare belirtilmemişse, geçiş sırasında ana kare başlar. Son ana kare belirtilmemişse, geçiş başlangıç kareden başlar ve son ana kareyi durdurur. Geçiş belirtilen bir süre parametresini ile oluşturulmuş olsa bile, bu süre başlangıç ve bitiş ana kareler arasındaki süre üzerine yazılır. Bir ana kareye belirtilmemişse, geçiş değişkenine en son eklenen geçiş eklenir.

##  <a name="cbasetransition"></a>  CBaseTransition::CBaseTransition

Temel transtion bir nesne oluşturur.

```
CBaseTransition();
```

##  <a name="clear"></a>  CBaseTransition::Clear

Yayınları IUIAnimationTransition COM nesnesi kapsüllenir.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, türetilmiş bir sınıfın oluşturma yöntemi IUITransition arabirimi sızıntısını önlemek için çağrılmalıdır.

##  <a name="create"></a>  CBaseTransition::Create

COM geçişi oluşturur.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory) = 0;
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Standart geçişleri oluşturan geçiş kitaplığı için bir işaretçi. Özel geçişleri için NULL olabilir.

*pFactory*<br/>
Özel geçişleri oluşturan geçiş fabrikası için bir işaretçi. Standart geçişleri için NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Bir geçiş COM nesnesi başarılı bir şekilde oluşturulduysa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Türetilen bir sınıfta geçersiz kılınması saf bir sanal işlev budur. COM geçiş nesnesini oluşturmak için framework tarafından çağırılır.

##  <a name="getendkeyframe"></a>  CBaseTransition::GetEndKeyframe

Ana kare döndürür başlatın.

```
CBaseKeyFrame* GetEndKeyframe();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi bir ana kare veya bir geçiş ana kareler arasında eklenmesi gereken değil yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından SetKeyframes önceden ayarlanmış bir ana kare nesneye erişmek için kullanılabilir. Görsel taslağa dönüştürme geçişleri eklenirken, üst düzey kod tarafından çağrılır.

##  <a name="getrelatedvariable"></a>  CBaseTransition::GetRelatedVariable

İlgili değişkenine bir işaretçi döndürür.

```
CAnimationVariable* GetRelatedVariable();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi animasyon değişkenine veya bir animasyon değişkenini SetRelatedVariable tarafından ayarlanmadı yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Erişimci ilgili animasyon değişkenin budur.

##  <a name="getstartkeyframe"></a>  CBaseTransition::GetStartKeyframe

Ana kare döndürür başlatın.

```
CBaseKeyFrame* GetStartKeyframe();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi bir ana kare veya bir geçiş bir anahtar kare başlamamalıdır yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından SetKeyframes önceden ayarlanmış bir ana kare nesneye erişmek için kullanılabilir. Görsel taslağa dönüştürme geçişleri eklenirken, üst düzey kod tarafından çağrılır.

##  <a name="gettransition"></a>  CBaseTransition::GetTransition

Temel alınan COM geçiş nesnesine bir işaretçi döndürür.

```
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory);

IUIAnimationTransition* GetTransition();
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Standart geçişleri oluşturan geçiş kitaplığı için bir işaretçi. Özel geçişleri için NULL olabilir.

*pFactory*<br/>
Özel geçişleri oluşturan geçiş fabrikası için bir işaretçi. Standart geçişleri için NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi IUIAnimationTransition veya geçiş temel oluşturulamıyorsa boş.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, temel alınan COM geçiş nesnesine bir işaretçi döndürür ve gerekirse oluşturur.

##  <a name="gettype"></a>  CBaseTransition::GetType

Geçiş türü döndürür.

```
TRANSITION_TYPE GetType() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRANSITION_TYPE birini numaralandırılmış değerlerinin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, türü tarafından geçiş nesneyi tanımlamak için kullanılabilir. Türetilmiş bir sınıftaki bir oluşturucunun türü ayarlayın.

##  <a name="isadded"></a>  CBaseTransition::IsAdded

Geçiş için görsel taslak eklenip eklenmediğini belirtir.

```
BOOL IsAdded();
```

### <a name="return-value"></a>Dönüş Değeri

Bir görsel taslak Aksi takdirde FALSE geçiş eklenmişse TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu bayrak, üst düzey kod görsel taslağa dönüştürme geçişleri eklediğinde dahili olarak ayarlanır.

##  <a name="m_badded"></a>  CBaseTransition::m_bAdded

Geçiş için görsel taslak eklenip eklenmediğini belirtir.

```
BOOL m_bAdded;
```

##  <a name="m_pendkeyframe"></a>  CBaseTransition::m_pEndKeyframe

Geçiş sonuna belirten bir anahtar kare işaretçi depolar.

```
CBaseKeyFrame* m_pEndKeyframe;
```

##  <a name="m_prelatedvariable"></a>  CBaseTransition::m_pRelatedVariable

M_transition içinde depolanan geçişte hareketli animasyon değişkenin bir işaretçi.

```
CAnimationVariable* m_pRelatedVariable;
```

##  <a name="m_pstartkeyframe"></a>  CBaseTransition::m_pStartKeyframe

Geçiş başlangıcını belirtir ana kare işaretçi depolar.

```
CBaseKeyFrame* m_pStartKeyframe;
```

##  <a name="m_transition"></a>  CBaseTransition::m_transition

IUIAnimationTransition bir işaretçi depolar. Bir COM Nesne geçiş yoksa NULL oluşturulmadı.

```
ATL::CComPtr<IUIAnimationTransition> m_transition;
```

##  <a name="m_type"></a>  CBaseTransition::m_type

Geçiş türü depolar.

```
TRANSITION_TYPE m_type;
```

##  <a name="setkeyframes"></a>  CBaseTransition::SetKeyframes

Ana kareleri geçiş ayarlar.

```
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,
    CBaseKeyFrame* pEnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pStart*<br/>
Geçiş başlangıcını belirtir bir ana kare.

*Bekleme*<br/>
Geçiş sonuna belirten bir anahtar kare.

### <a name="remarks"></a>Açıklamalar

Geçiş bekleme NULL değilse belirtilen ana kare sonra başlamalı ve isteğe bağlı olarak, bu yöntem söyler belirtilen ana kare önce. Geçiş belirtilen bir süre parametresini ile oluşturulmuş olsa bile, bu süre başlangıç ve bitiş ana kareler arasındaki süre üzerine yazılır.

##  <a name="setrelatedvariable"></a>  CBaseTransition::SetRelatedVariable

Animasyon değişkenin ve geçiş arasında bir ilişki kurar.

```
void SetRelatedVariable(CAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametreler

*pVariable*<br/>
İlgili animasyon değişkeninin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Animasyon değişkenin ve geçiş arasında bir ilişki kurar. Geçiş yalnızca bir değişkene uygulanabilir.

##  <a name="transition_type_enumeration"></a>  CBaseTransition::TRANSITION_TYPE numaralandırması

Şu anda Windows animasyon API'sı MFC uygulaması tarafından desteklenen geçiş türleri tanımlar.

```
enum TRANSITION_TYPE;
```

### <a name="remarks"></a>Açıklamalar

Bir geçiş türü, belirli bir geçiş oluşturucuda ayarlanır. Örneğin, CSinusoidalTransitionFromRange için SINUSOIDAL_FROM_RANGE türünü ayarlar.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
