---
description: 'Daha fazla bilgi edinin: CBaseTransition sınıfı'
title: CBaseTransition sınıfı
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
ms.openlocfilehash: 16a7b5e7f88e292fd2b771c627f7169c70fec2c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122830"
---
# <a name="cbasetransition-class"></a>CBaseTransition sınıfı

Temel bir geçişi temsil eder.

## <a name="syntax"></a>Syntax

```
class CBaseTransition : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="public-enumerations"></a>Ortak numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[CBaseTransition:: TRANSITION_TYPE numaralandırması](#transition_type_enumeration)|Windows animasyon API 'sinin MFC uygulamasında şu anda desteklenen geçiş türlerini tanımlar.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBaseTransition:: CBaseTransition](#cbasetransition)|Temel geçiş nesnesi oluşturur.|
|[CBaseTransition:: ~ CBaseTransition](#_dtorcbasetransition)|Yok edicisi. Bir geçiş nesnesi yok edildiğinde çağırılır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBaseTransition:: AddToStoryboard](#addtostoryboard)|Görsel taslağa bir geçiş ekler.|
|[CBaseTransition:: Addtoöykü Boardatana kareleri](#addtostoryboardatkeyframes)|Görsel taslağa bir geçiş ekler.|
|[CBaseTransition:: Clear](#clear)|Encapsulated IUIAnimationTransition COM nesnesini yayınlar.|
|[CBaseTransition:: Create](#create)|Bir COM geçişi oluşturur.|
|[CBaseTransition:: GetEndKeyframe](#getendkeyframe)|Başlangıç ana karesini döndürür.|
|[CBaseTransition:: GetRelatedVariable](#getrelatedvariable)|İlgili değişkene yönelik bir işaretçi döndürür.|
|[CBaseTransition:: GetStartKeyframe](#getstartkeyframe)|Başlangıç ana karesini döndürür.|
|[CBaseTransition:: GetTransition](#gettransition)|Fazla Yüklendi. Temel alınan COM geçiş nesnesine bir işaretçi döndürür.|
|[CBaseTransition:: GetType](#gettype)|Geçiş türünü döndürür.|
|[CBaseTransition:: IsAdded](#isadded)|Bir görsel taslağa bir geçişin eklenip eklenmeyeceğini söyler.|
|[CBaseTransition:: Setana kareleri](#setkeyframes)|Bir geçiş için ana kareleri ayarlar.|
|[CBaseTransition:: Setrelateddeğişkeni](#setrelatedvariable)|Animasyon değişkeni ve geçişi arasında bir ilişki oluşturur.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CBaseTransition:: m_bAdded](#m_badded)|Bir görsel taslağa bir geçişin eklenip eklenmeyeceğini belirtir.|
|[CBaseTransition:: m_pEndKeyframe](#m_pendkeyframe)|Geçişin sonunu belirten ana kareye bir işaretçi depolar.|
|[CBaseTransition:: m_pRelatedVariable](#m_prelatedvariable)|M_transition depolanan geçişle animasyon eklenmiş animasyon değişkenine yönelik bir işaretçi.|
|[CBaseTransition:: m_pStartKeyframe](#m_pstartkeyframe)|Geçişin başlangıcını belirten ana kareye bir işaretçi depolar.|
|[CBaseTransition:: m_transition](#m_transition)|IUIAnimationTransition işaretçisini depolar. Bir COM geçiş nesnesi oluşturulmadıysa NULL.|
|[CBaseTransition:: m_type](#m_type)|Geçiş türünü depolar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf IUIAnimationTransition arabirimini kapsüller ve tüm geçişler için bir temel sınıf işlevi görür.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CBaseTransition`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="cbasetransitioncbasetransition"></a><a name="_dtorcbasetransition"></a> CBaseTransition:: ~ CBaseTransition

Yok edicisi. Bir geçiş nesnesi yok edildiğinde çağırılır.

```
virtual ~CBaseTransition();
```

## <a name="cbasetransitionaddtostoryboard"></a><a name="addtostoryboard"></a> CBaseTransition:: AddToStoryboard

Görsel taslağa bir geçiş ekler.

```
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslağa yönelik bir işaretçi, ilgili değişkeni canlandırır.

### <a name="return-value"></a>Dönüş Değeri

Eğer geçiş bir görsel taslağa başarıyla eklendiyse TRUE.

### <a name="remarks"></a>Açıklamalar

Film şeridinde ilgili değişkene geçişi uygular. Bu görsel taslakta bu değişkene uygulanan ilk geçiş ise, geçiş, film şeridinin başlangıcında başlar. Aksi takdirde, geçiş en son değişkene eklenen geçişe eklenir.

## <a name="cbasetransitionaddtostoryboardatkeyframes"></a><a name="addtostoryboardatkeyframes"></a> CBaseTransition:: Addtoöykü Boardatana kareleri

Görsel taslağa bir geçiş ekler.

```
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslağa yönelik bir işaretçi, ilgili değişkeni canlandırır.

### <a name="return-value"></a>Dönüş Değeri

Eğer geçiş bir görsel taslağa başarıyla eklendiyse TRUE.

### <a name="remarks"></a>Açıklamalar

Film şeridinde ilgili değişkene geçişi uygular. Başlangıç anahtar karesi belirtilmişse, geçiş bu ana karede başlar. Bitiş ana karesi belirtilmişse, geçiş başlangıç ana karesinde başlar ve bitiş ana karesine göre duraklar. Geçiş belirtilen bir Duration parametresi ile oluşturulduysa, başlangıç ve bitiş ana kareleri arasındaki süre ile bu sürenin üzerine yazılır. Hiçbir ana kare belirtilmemişse, geçiş en son değişkene eklenen geçişe eklenir.

## <a name="cbasetransitioncbasetransition"></a><a name="cbasetransition"></a> CBaseTransition:: CBaseTransition

Temel geçiş nesnesi oluşturur.

```
CBaseTransition();
```

## <a name="cbasetransitionclear"></a><a name="clear"></a> CBaseTransition:: Clear

Encapsulated IUIAnimationTransition COM nesnesini yayınlar.

```cpp
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, IUITransition arabirimi sızıntısını engellemek için türetilen sınıfın oluşturma yönteminden çağrılmalıdır.

## <a name="cbasetransitioncreate"></a><a name="create"></a> CBaseTransition:: Create

Bir COM geçişi oluşturur.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory) = 0;
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Standart geçişleri oluşturan geçiş kitaplığı işaretçisi. Özel geçişler için NULL olabilir.

*pFactory*<br/>
Özel geçişler oluşturan geçiş fabrikası işaretçisi. Standart geçişler için NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Bir geçiş COM nesnesi başarıyla oluşturulduysa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu, türetilmiş bir sınıfta geçersiz kılınabilmesi gereken saf bir sanal işlevdir. Temel alınan COM geçiş nesnesini örneklemek için Framework tarafından çağırılır.

## <a name="cbasetransitiongetendkeyframe"></a><a name="getendkeyframe"></a> CBaseTransition:: GetEndKeyframe

Başlangıç ana karesini döndürür.

```
CBaseKeyFrame* GetEndKeyframe();
```

### <a name="return-value"></a>Dönüş Değeri

Ana kareye yönelik geçerli bir işaretçi veya anahtar kareler arasında bir geçiş eklenmemelidir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, daha önce Setana kareleri tarafından ayarlanmış bir ana kare nesnesine erişmek için kullanılabilir. Görsel taslağa geçişler eklenirken üst düzey kod tarafından çağırılır.

## <a name="cbasetransitiongetrelatedvariable"></a><a name="getrelatedvariable"></a> CBaseTransition:: GetRelatedVariable

İlgili değişkene yönelik bir işaretçi döndürür.

```
CAnimationVariable* GetRelatedVariable();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir animasyon değişkeni işaretçisi veya bir animasyon değişkeni SetRelatedVariable tarafından ayarlanmamışsa NULL.

### <a name="remarks"></a>Açıklamalar

Bu, ilgili animasyon değişkenine yönelik bir erişimdir.

## <a name="cbasetransitiongetstartkeyframe"></a><a name="getstartkeyframe"></a> CBaseTransition:: GetStartKeyframe

Başlangıç ana karesini döndürür.

```
CBaseKeyFrame* GetStartKeyframe();
```

### <a name="return-value"></a>Dönüş Değeri

Bir anahtar kareden sonra bir geçiş başlamamalıdır, bir ana kareye yönelik geçerli bir işaretçi veya NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, daha önce Setana kareleri tarafından ayarlanmış bir ana kare nesnesine erişmek için kullanılabilir. Görsel taslağa geçişler eklenirken üst düzey kod tarafından çağırılır.

## <a name="cbasetransitiongettransition"></a><a name="gettransition"></a> CBaseTransition:: GetTransition

Temel alınan COM geçiş nesnesine bir işaretçi döndürür.

```
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory);

IUIAnimationTransition* GetTransition();
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Standart geçişleri oluşturan geçiş kitaplığı işaretçisi. Özel geçişler için NULL olabilir.

*pFactory*<br/>
Özel geçişler oluşturan geçiş fabrikası işaretçisi. Standart geçişler için NULL olabilir.

### <a name="return-value"></a>Dönüş Değeri

Temeldeki geçiş oluşturulanmadıysa IUIAnimationTransition için geçerli bir işaretçi veya NULL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, temel alınan COM geçiş nesnesine bir işaretçi döndürür ve gerekirse oluşturur.

## <a name="cbasetransitiongettype"></a><a name="gettype"></a> CBaseTransition:: GetType

Geçiş türünü döndürür.

```
TRANSITION_TYPE GetType() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRANSITION_TYPE numaralandırılmış değerlerden biri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir geçiş nesnesini türüne göre belirlemek için kullanılabilir. Tür, türetilmiş bir sınıftaki oluşturucuda ayarlanır.

## <a name="cbasetransitionisadded"></a><a name="isadded"></a> CBaseTransition:: IsAdded

Bir görsel taslağa bir geçişin eklenip eklenmeyeceğini söyler.

```
BOOL IsAdded();
```

### <a name="return-value"></a>Dönüş Değeri

Bir görsel taslağa bir geçiş eklendiyse TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Üst düzey kod görsel taslağa geçişler eklediğinde bu bayrak dahili olarak ayarlanır.

## <a name="cbasetransitionm_badded"></a><a name="m_badded"></a> CBaseTransition:: m_bAdded

Bir görsel taslağa bir geçişin eklenip eklenmeyeceğini belirtir.

```
BOOL m_bAdded;
```

## <a name="cbasetransitionm_pendkeyframe"></a><a name="m_pendkeyframe"></a> CBaseTransition:: m_pEndKeyframe

Geçişin sonunu belirten ana kareye bir işaretçi depolar.

```
CBaseKeyFrame* m_pEndKeyframe;
```

## <a name="cbasetransitionm_prelatedvariable"></a><a name="m_prelatedvariable"></a> CBaseTransition:: m_pRelatedVariable

M_transition depolanan geçişle animasyon eklenmiş animasyon değişkenine yönelik bir işaretçi.

```
CAnimationVariable* m_pRelatedVariable;
```

## <a name="cbasetransitionm_pstartkeyframe"></a><a name="m_pstartkeyframe"></a> CBaseTransition:: m_pStartKeyframe

Geçişin başlangıcını belirten ana kareye bir işaretçi depolar.

```
CBaseKeyFrame* m_pStartKeyframe;
```

## <a name="cbasetransitionm_transition"></a><a name="m_transition"></a> CBaseTransition:: m_transition

IUIAnimationTransition işaretçisini depolar. Bir COM geçiş nesnesi oluşturulmadıysa NULL.

```
ATL::CComPtr<IUIAnimationTransition> m_transition;
```

## <a name="cbasetransitionm_type"></a><a name="m_type"></a> CBaseTransition:: m_type

Geçiş türünü depolar.

```
TRANSITION_TYPE m_type;
```

## <a name="cbasetransitionsetkeyframes"></a><a name="setkeyframes"></a> CBaseTransition:: Setana kareleri

Bir geçiş için ana kareleri ayarlar.

```cpp
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,
    CBaseKeyFrame* pEnd = NULL);
```

### <a name="parameters"></a>Parametreler

*pStart*<br/>
Geçişin başlangıcını belirten bir ana kare.

*Bekleyen*<br/>
Geçişin sonunu belirten bir ana kare.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, geçişe belirtilen ana kareden sonra başlamasını söyler ve isteğe bağlı olarak, bekleme NULL değilse belirtilen ana kareden önce sonlandırın. Geçiş belirtilen bir Duration parametresi ile oluşturulduysa, başlangıç ve bitiş ana kareleri arasındaki süre ile bu sürenin üzerine yazılır.

## <a name="cbasetransitionsetrelatedvariable"></a><a name="setrelatedvariable"></a> CBaseTransition:: Setrelateddeğişkeni

Animasyon değişkeni ve geçişi arasında bir ilişki oluşturur.

```cpp
void SetRelatedVariable(CAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametreler

*pVariable*<br/>
İlgili animasyon değişkenine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Animasyon değişkeni ve geçişi arasında bir ilişki oluşturur. Bir geçiş yalnızca bir değişkene uygulanabilir.

## <a name="cbasetransitiontransition_type-enumeration"></a><a name="transition_type_enumeration"></a> CBaseTransition:: TRANSITION_TYPE numaralandırması

Windows animasyon API 'sinin MFC uygulamasında şu anda desteklenen geçiş türlerini tanımlar.

```
enum TRANSITION_TYPE;
```

### <a name="remarks"></a>Açıklamalar

Bir geçiş türü, belirli bir geçişin oluşturucusunda ayarlanır. Örneğin, Csinusoidalgeçişli Tionfromrange, türünü SINUSOIDAL_FROM_RANGE olarak ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
