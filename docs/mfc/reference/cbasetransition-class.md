---
title: CBaseTransition Sınıfı
ms.date: 03/27/2019
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
ms.openlocfilehash: 9abe4ae55d9d84ea435cd5d82925ff8b8a544480
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752962"
---
# <a name="cbasetransition-class"></a>CBaseTransition Sınıfı

Temel bir geçişi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CBaseTransition : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="public-enumerations"></a>Genel Hesaplamalar

|Adı|Açıklama|
|----------|-----------------|
|[CBaseTransition::TRANSITION_TYPE Numaralandırma](#transition_type_enumeration)|Şu anda Windows Animasyon API'sının MFC uygulaması tarafından desteklenen geçiş türlerini tanımlar.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CBaseTransition::CBaseTransition](#cbasetransition)|Bir temel geçiş nesnesi oluşturuyor.|
|[CBaseTransition::~CBaseTransition](#_dtorcbasetransition)|Yıkıcı. Bir geçiş nesnesi yok edilirken çağrılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|Film şeridine geçiş ekler.|
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|Film şeridine geçiş ekler.|
|[CBaseTransition::Clear](#clear)|Kapsüllü IUIAnimationGeçiş COM nesnesi bültenleri.|
|[CBaseTransition::Oluştur](#create)|Com geçişi oluşturur.|
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|Döndürür başlangıç anahtar çerçevesi.|
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|İlgili değişkene bir işaretçi döndürür.|
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|Döndürür başlangıç anahtar çerçevesi.|
|[CBaseTransition::GetTransition](#gettransition)|Fazla Yüklendi. Alttaki COM geçiş nesnesine bir işaretçi döndürür.|
|[CBaseTransition::GetType](#gettype)|Geçiş türünü döndürür.|
|[CbaseTransition::Isadded](#isadded)|Bir geçişin bir film şeridine eklenip eklenmediğini söyler.|
|[CBaseTransition::SetKeyframes](#setkeyframes)|Geçiş için anahtar çerçeveleri ayarlar.|
|[CbaseTransition::SetRelatedVariable](#setrelatedvariable)|Animasyon değişkeni ile geçiş arasında bir ilişki kurar.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CBaseTransition::m_bAdded](#m_badded)|Bir geçişin bir film şeridine eklenip eklenmediğini belirtir.|
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|Geçişin sonunu belirten anahtar çerçevesiiçin bir işaretçi depolar.|
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|m_transition depolanan geçişle animasyonlu bir animasyon değişkenine işaretçi.|
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|Geçişin başlangıcını belirten anahtar çerçevesiiçin bir işaretçi depolar.|
|[CBaseTransition::m_transition](#m_transition)|IUIAnimationTransition için bir işaretçi depolar. COM geçiş nesnesi oluşturulmamadıysa NULL.|
|[CBaseTransition::m_type](#m_type)|Geçiş türünü depolar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf IUIAnimationGeçiş arabirimini kapsüller ve tüm geçişler için bir taban sınıf olarak hizmet vermektedir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CBaseTransition`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="cbasetransitioncbasetransition"></a><a name="_dtorcbasetransition"></a>CBaseTransition::~CBaseTransition

Yıkıcı. Bir geçiş nesnesi yok edilirken çağrılır.

```
virtual ~CBaseTransition();
```

## <a name="cbasetransitionaddtostoryboard"></a><a name="addtostoryboard"></a>CBaseTransition::AddToStoryboard

Film şeridine geçiş ekler.

```
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
İlgili değişkeni canlandıracak bir işaretçi, film şeridi için.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU, geçiş başarıyla bir film şeridine eklendiyse.

### <a name="remarks"></a>Açıklamalar

Film şeridindeki ilgili değişkene geçişi uygular. Bu, bu film şeridinde bu değişkene uygulanan ilk geçişse, geçiş film şeridinin başlangıcında başlar. Aksi takdirde, geçiş değişkene en son eklenen geçişeklenir.

## <a name="cbasetransitionaddtostoryboardatkeyframes"></a><a name="addtostoryboardatkeyframes"></a>CBaseTransition::AddToStoryboardAtKeyframes

Film şeridine geçiş ekler.

```
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
İlgili değişkeni canlandıracak bir işaretçi, film şeridi için.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU, geçiş başarıyla bir film şeridine eklendiyse.

### <a name="remarks"></a>Açıklamalar

Film şeridindeki ilgili değişkene geçişi uygular. Başlangıç anahtar çerçevesi belirtilmişse, geçiş bu anahtar çerçevede başlar. Bitiş anahtar çerçevesi belirtilmişse, geçiş başlangıç anahtar çerçevesinde başlar ve son anahtar karede durur. Geçiş, belirtilen bir süre parametresi ile oluşturulduysa, bu süre başlangıç ve bitiş anahtar kareleri arasındaki süreyle birlikte üzerine yazılır. Anahtar çerçevesi belirtilmemişse, geçiş en son değişkene eklenen geçişe eklenir.

## <a name="cbasetransitioncbasetransition"></a><a name="cbasetransition"></a>CBaseTransition::CBaseTransition

Bir temel geçiş nesnesi oluşturuyor.

```
CBaseTransition();
```

## <a name="cbasetransitionclear"></a><a name="clear"></a>CBaseTransition::Clear

Kapsüllü IUIAnimationGeçiş COM nesnesi bültenleri.

```cpp
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, IUITransition arabirim sızıntısını önlemek için türemiş bir sınıfın Oluştur yönteminden çağrılmalıdır.

## <a name="cbasetransitioncreate"></a><a name="create"></a>CBaseTransition::Oluştur

Com geçişi oluşturur.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory) = 0;
```

### <a name="parameters"></a>Parametreler

*pKütüphane*<br/>
Standart geçişler oluşturan geçiş kitaplığı için bir işaretçi. Özel geçişler için NULL olabilir.

*pFactory*<br/>
Özel geçişler oluşturan geçiş fabrikasıiçin bir işaretçi. Standart geçişler için NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Bir geçiş COM nesnesi başarıyla oluşturulduysa TRUE; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu, türemiş bir sınıfta geçersiz kılınması gereken saf bir sanal işlevdir. Bu çerçeve tarafından temel COM geçiş nesnesi anlık olarak adlandırılır.

## <a name="cbasetransitiongetendkeyframe"></a><a name="getendkeyframe"></a>CBaseTransition::GetEndKeyframe

Döndürür başlangıç anahtar çerçevesi.

```
CBaseKeyFrame* GetEndKeyframe();
```

### <a name="return-value"></a>Dönüş Değeri

Anahtar kareler arasına geçiş eklenmemesi gerekiyorsa, anahtar kareiçin geçerli bir işaretçi veya NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, daha önce SetKeyframes tarafından ayarlanmış bir anahtar çerçeve nesnesine erişmek için kullanılabilir. Geçişler film şeridine eklendiğinde üst düzey kodla çağrılır.

## <a name="cbasetransitiongetrelatedvariable"></a><a name="getrelatedvariable"></a>CBaseTransition::GetRelatedVariable

İlgili değişkene bir işaretçi döndürür.

```
CAnimationVariable* GetRelatedVariable();
```

### <a name="return-value"></a>Dönüş Değeri

Bir animasyon değişkeni SetRelatedVariable tarafından ayarlanmadıysa, animasyon değişkenine geçerli bir işaretçi veya NULL.

### <a name="remarks"></a>Açıklamalar

Bu, ilgili animasyon değişkenine bir erişimdir.

## <a name="cbasetransitiongetstartkeyframe"></a><a name="getstartkeyframe"></a>CBaseTransition::GetStartKeyframe

Döndürür başlangıç anahtar çerçevesi.

```
CBaseKeyFrame* GetStartKeyframe();
```

### <a name="return-value"></a>Dönüş Değeri

Anahtar kareiçin geçerli bir işaretçi veya anahtar çerçeveden sonra geçiş başlamazsa NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, daha önce SetKeyframes tarafından ayarlanmış bir anahtar çerçeve nesnesine erişmek için kullanılabilir. Geçişler film şeridine eklendiğinde üst düzey kodla çağrılır.

## <a name="cbasetransitiongettransition"></a><a name="gettransition"></a>CBaseTransition::GetTransition

Alttaki COM geçiş nesnesine bir işaretçi döndürür.

```
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory);

IUIAnimationTransition* GetTransition();
```

### <a name="parameters"></a>Parametreler

*pKütüphane*<br/>
Standart geçişler oluşturan geçiş kitaplığı için bir işaretçi. Özel geçişler için NULL olabilir.

*pFactory*<br/>
Özel geçişler oluşturan geçiş fabrikasıiçin bir işaretçi. Standart geçişler için NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Temel geçiş oluşturulamazsa IUIAnimationTransition veya NULL için geçerli bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir işaretçiyi altta yatan COM geçiş nesnesine döndürür ve gerekirse oluşturur.

## <a name="cbasetransitiongettype"></a><a name="gettype"></a>CBaseTransition::GetType

Geçiş türünü döndürür.

```
TRANSITION_TYPE GetType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Numaralandırılmış TRANSITION_TYPE değerden biri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir geçiş nesnesini türüne göre tanımlamak için kullanılabilir. Tür, türemiş bir sınıfta bir oluşturucu olarak ayarlanır.

## <a name="cbasetransitionisadded"></a><a name="isadded"></a>CbaseTransition::Isadded

Bir geçişin bir film şeridine eklenip eklenmediğini söyler.

```
BOOL IsAdded();
```

### <a name="return-value"></a>Dönüş Değeri

Bir geçiş bir film şeridine eklenmiştir, aksi takdirde FALSE TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Üst düzey kod film şeridine geçişler eklendiğinde bu bayrak dahili olarak ayarlanır.

## <a name="cbasetransitionm_badded"></a><a name="m_badded"></a>CBaseTransition::m_bAdded

Bir geçişin bir film şeridine eklenip eklenmediğini belirtir.

```
BOOL m_bAdded;
```

## <a name="cbasetransitionm_pendkeyframe"></a><a name="m_pendkeyframe"></a>CBaseTransition::m_pEndKeyframe

Geçişin sonunu belirten anahtar çerçevesiiçin bir işaretçi depolar.

```
CBaseKeyFrame* m_pEndKeyframe;
```

## <a name="cbasetransitionm_prelatedvariable"></a><a name="m_prelatedvariable"></a>CBaseTransition::m_pRelatedVariable

m_transition depolanan geçişle animasyonlu bir animasyon değişkenine işaretçi.

```
CAnimationVariable* m_pRelatedVariable;
```

## <a name="cbasetransitionm_pstartkeyframe"></a><a name="m_pstartkeyframe"></a>CBaseTransition::m_pStartKeyframe

Geçişin başlangıcını belirten anahtar çerçevesiiçin bir işaretçi depolar.

```
CBaseKeyFrame* m_pStartKeyframe;
```

## <a name="cbasetransitionm_transition"></a><a name="m_transition"></a>CBaseTransition::m_transition

IUIAnimationTransition için bir işaretçi depolar. COM geçiş nesnesi oluşturulmamadıysa NULL.

```
ATL::CComPtr<IUIAnimationTransition> m_transition;
```

## <a name="cbasetransitionm_type"></a><a name="m_type"></a>CBaseTransition::m_type

Geçiş türünü depolar.

```
TRANSITION_TYPE m_type;
```

## <a name="cbasetransitionsetkeyframes"></a><a name="setkeyframes"></a>CBaseTransition::SetKeyframes

Geçiş için anahtar çerçeveleri ayarlar.

```cpp
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,
    CBaseKeyFrame* pEnd = NULL);
```

### <a name="parameters"></a>Parametreler

*Pstart*<br/>
Geçişin başlangıcını belirten bir anahtar çerçeve.

*Bekleme*<br/>
Geçişin sonunu belirten bir anahtar çerçeve.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, belirtilen anahtar çerçeveden sonra başletmek için geçiş söyler ve isteğe bağlı olarak, pEnd NULL değilse, belirtilen anahtar çerçevesi önce sona erer. Geçiş, belirtilen bir süre parametresi ile oluşturulduysa, bu süre başlangıç ve bitiş anahtar kareleri arasındaki süreyle birlikte üzerine yazılır.

## <a name="cbasetransitionsetrelatedvariable"></a><a name="setrelatedvariable"></a>CbaseTransition::SetRelatedVariable

Animasyon değişkeni ile geçiş arasında bir ilişki kurar.

```cpp
void SetRelatedVariable(CAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametreler

*pDeğişken*<br/>
İlgili animasyon değişkenine işaretçi.

### <a name="remarks"></a>Açıklamalar

Animasyon değişkeni ile geçiş arasında bir ilişki kurar. Geçiş yalnızca bir değişkene uygulanabilir.

## <a name="cbasetransitiontransition_type-enumeration"></a><a name="transition_type_enumeration"></a>CBaseTransition::TRANSITION_TYPE Numaralandırma

Şu anda Windows Animasyon API'sının MFC uygulaması tarafından desteklenen geçiş türlerini tanımlar.

```
enum TRANSITION_TYPE;
```

### <a name="remarks"></a>Açıklamalar

Belirli bir geçişin oluşturucusu bir geçiş türü ayarlanır. Örneğin, CSinusoidalTransitionFromRange SINUSOIDAL_FROM_RANGE türünü ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
