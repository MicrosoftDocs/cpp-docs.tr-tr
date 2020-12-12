---
description: 'Daha fazla bilgi edinin: Csmootstoptransition sınıfı'
title: Csmootstoptransition sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::Create
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_maximumDuration
helpviewer_keywords:
- CSmoothStopTransition [MFC], CSmoothStopTransition
- CSmoothStopTransition [MFC], Create
- CSmoothStopTransition [MFC], m_dblFinalValue
- CSmoothStopTransition [MFC], m_maximumDuration
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
ms.openlocfilehash: 14ea7475c886201d6b9b72eefc62f41679e73008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264537"
---
# <a name="csmoothstoptransition-class"></a>Csmootstoptransition sınıfı

Kesintisiz bir geçişi kapsüller.

## <a name="syntax"></a>Syntax

```
class CSmoothStopTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Csmootstoptransition:: Csmootstoptransition](#csmoothstoptransition)|Kesintisiz bir geçiş oluşturur ve en uzun süre ile son değeri başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Csmootstoptransition:: Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. ( [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create)geçersiz kılar.)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Csmootstoptransition:: m_dblFinalValue](#m_dblfinalvalue)|Geçişin sonundaki animasyon değişkeninin değeri.|
|[Csmootstoptransition:: m_maximumDuration](#m_maximumduration)|Geçişin en uzun süresi.|

## <a name="remarks"></a>Açıklamalar

Kesintisiz durdurma geçişi, belirli bir son değere yaklaşırsa ve sıfıra bir hız ile ulaştığında yavaşlatır. Geçişin süresi ilk hız, ilk ve son değerleri arasındaki fark ve belirtilen en uzun süre ile belirlenir. Tek bir parametre yayı içeren bir çözüm yoksa, bu yöntem üçüncü dereceden bir geçiş oluşturur. Tüm geçişler otomatik olarak temizlendiğinden, Yeni işleç kullanılarak ayrılmaları önerilir. Encapsulated IUIAnimationTransition COM nesnesi, NULL olana kadar CAnimationController:: AnimateGroup tarafından oluşturulur. Bu COM nesnesi oluşturulduktan sonra üye değişkenlerinin değiştirilmesinin etkisi olmaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[Csmootstopgeçişi](../../mfc/reference/csmoothstoptransition-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="csmoothstoptransitioncreate"></a><a name="create"></a> Csmootstoptransition:: Create

Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Standart geçişlerin oluşturulmasından sorumlu olan geçiş kitaplığı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa doğru; Aksi halde yanlış.

## <a name="csmoothstoptransitioncsmoothstoptransition"></a><a name="csmoothstoptransition"></a> Csmootstoptransition:: Csmootstoptransition

Kesintisiz bir geçiş oluşturur ve en uzun süre ile son değeri başlatır.

```
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Parametreler

*maximumDuration*<br/>
Geçişin en uzun süresi.

*Dblfinaldeğeri*<br/>
Geçişin sonundaki animasyon değişkeninin değeri.

## <a name="csmoothstoptransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a> Csmootstoptransition:: m_dblFinalValue

Geçişin sonundaki animasyon değişkeninin değeri.

```
DOUBLE m_dblFinalValue;
```

## <a name="csmoothstoptransitionm_maximumduration"></a><a name="m_maximumduration"></a> Csmootstoptransition:: m_maximumDuration

Geçişin en uzun süresi.

```
UI_ANIMATION_SECONDS m_maximumDuration;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
