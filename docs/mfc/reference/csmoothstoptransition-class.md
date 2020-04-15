---
title: CsmoothStopTransition Sınıfı
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
ms.openlocfilehash: 0ba550b4a0b9443d0681e17195687fb94c207ace
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318201"
---
# <a name="csmoothstoptransition-class"></a>CsmoothStopTransition Sınıfı

Sorunsuz bir geçişi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CSmoothStopTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CsmoothStopTransition::CsmoothStopTransition](#csmoothstoptransition)|Düzgün bir durdurma geçişi sağlar ve maksimum süresini ve son değerini başolarak değerlendirir.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CsmoothStopTransition::Oluştur](#create)|Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. (CBaseTransition geçersiz [kılar::Oluştur](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CSmoothStopGeçiş::m_dblFinalValue](#m_dblfinalvalue)|Geçişin sonundaki animasyon değişkeninin değeri.|
|[CSmoothStopGeçiş::m_maximumDuration](#m_maximumduration)|Geçişin maksimum süresi.|

## <a name="remarks"></a>Açıklamalar

Düzgün durma geçişi, belirli bir son değere yaklaştıkça yavaşlar ve sıfır hızıyla ona ulaşır. Geçiş süresi ilk hız, ilk ve son değerler arasındaki fark ve belirtilen maksimum süre tarafından belirlenir. Tek bir parabolik yaydan oluşan bir çözüm yoksa, bu yöntem kübik bir geçiş oluşturur. Tüm geçişler otomatik olarak temizlenerek, operatör yeni kullanılarak ayrılması önerilir. Kapsüllü IUIAnimationTransition COM nesnesi CAnimationController tarafından oluşturulur::AnimateGroup, o zamana kadar NULL' s. Bu COM nesnesinin oluşturulduktan sonra üye değişkenleri değiştirmenin hiçbir etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CsmoothStopGeçiş](../../mfc/reference/csmoothstoptransition-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="csmoothstoptransitioncreate"></a><a name="create"></a>CsmoothStopTransition::Oluştur

Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametreler

*pKütüphane*<br/>
Standart geçişlerin oluşturulmasından sorumlu geçiş kitaplığı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa DOĞRU; aksi takdirde YANLIŞ.

## <a name="csmoothstoptransitioncsmoothstoptransition"></a><a name="csmoothstoptransition"></a>CsmoothStopTransition::CsmoothStopTransition

Düzgün bir durdurma geçişi sağlar ve maksimum süresini ve son değerini başolarak değerlendirir.

```
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Parametreler

*maksimumSüre*<br/>
Geçişin maksimum süresi.

*dblFinalValue*<br/>
Geçişin sonundaki animasyon değişkeninin değeri.

## <a name="csmoothstoptransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>CSmoothStopGeçiş::m_dblFinalValue

Geçişin sonundaki animasyon değişkeninin değeri.

```
DOUBLE m_dblFinalValue;
```

## <a name="csmoothstoptransitionm_maximumduration"></a><a name="m_maximumduration"></a>CSmoothStopGeçiş::m_maximumDuration

Geçişin maksimum süresi.

```
UI_ANIMATION_SECONDS m_maximumDuration;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
