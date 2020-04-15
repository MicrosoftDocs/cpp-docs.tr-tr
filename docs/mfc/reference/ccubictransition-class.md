---
title: CCubicTransition Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::Create
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalVelocity
- AFXANIMATIONCONTROLLER/CCubicTransition::m_duration
helpviewer_keywords:
- CCubicTransition [MFC], CCubicTransition
- CCubicTransition [MFC], Create
- CCubicTransition [MFC], m_dblFinalValue
- CCubicTransition [MFC], m_dblFinalVelocity
- CCubicTransition [MFC], m_duration
ms.assetid: 4fc30e9c-160c-45e1-bdbe-51adf8fee9c5
ms.openlocfilehash: de376503111dab157ca34744863fb1d35a58785e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369343"
---
# <a name="ccubictransition-class"></a>CCubicTransition Sınıfı

Kübik geçişi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CCubicTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CCubicTransition::CCubicTransition](#ccubictransition)|Bir geçiş nesnesi oluşturuyor ve parametrelerini başharfe doğru laştırır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CCubicTransition::Oluştur](#create)|Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. (CBaseTransition geçersiz [kılar::Oluştur](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CCubicTransition::m_dblFinalValue](#m_dblfinalvalue)|Geçişin sonundaki animasyon değişkeninin değeri.|
|[CCubicTransition::m_dblFinalVelocity](#m_dblfinalvelocity)|Geçiş sonundaki değişkenin hızı.|
|[CCubicTransition::m_duration](#m_duration)|Geçiş süresi.|

## <a name="remarks"></a>Açıklamalar

Bir kübik geçiş sırasında, animasyon değişkeninin değeri, geçiş süresi boyunca başlangıç değerinden belirli bir son değere dönüşür ve belirli bir hızda sona erer. Tüm geçişler otomatik olarak temizlenerek, operatör yeni kullanılarak ayrılması önerilir. Kapsüllü IUIAnimationTransition COM nesnesi CAnimationController tarafından oluşturulur::AnimateGroup, o zamana kadar NULL' s. Bu COM nesnesinin oluşturulduktan sonra üye değişkenleri değiştirmenin hiçbir etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCubicTransition`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="ccubictransitionccubictransition"></a><a name="ccubictransition"></a>CCubicTransition::CCubicTransition

Bir geçiş nesnesi oluşturuyor ve parametrelerini başharfe doğru laştırır.

```
CCubicTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE finalVelocity);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
Geçiş süresi.

*finalValue*<br/>
Geçişin sonundaki animasyon değişkeninin değeri.

*finalVelocity*<br/>
Geçiş sonundaki değişkenin hızı.

## <a name="ccubictransitioncreate"></a><a name="create"></a>CCubicTransition::Oluştur

Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametreler

*pKütüphane*<br/>
Standart geçişler kitaplığını tanımlayan [IUIAnimationTransitionLibrary arabirimine](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa DOĞRU; aksi takdirde YANLIŞ.

## <a name="ccubictransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>CCubicTransition::m_dblFinalValue

Geçişin sonundaki animasyon değişkeninin değeri.

```
DOUBLE m_dblFinalValue;
```

## <a name="ccubictransitionm_dblfinalvelocity"></a><a name="m_dblfinalvelocity"></a>CCubicTransition::m_dblFinalVelocity

Geçiş sonundaki değişkenin hızı.

```
DOUBLE m_dblFinalVelocity;
```

## <a name="ccubictransitionm_duration"></a><a name="m_duration"></a>CCubicTransition::m_duration

Geçiş süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
