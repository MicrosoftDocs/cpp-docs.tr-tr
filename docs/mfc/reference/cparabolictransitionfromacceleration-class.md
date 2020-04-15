---
title: CParabolicTransitionFromAcceleration Sınıf
ms.date: 11/04/2016
f1_keywords:
- CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::Create
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalVelocity
helpviewer_keywords:
- CParabolicTransitionFromAcceleration [MFC], CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration [MFC], Create
- CParabolicTransitionFromAcceleration [MFC], m_dblAcceleration
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalValue
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalVelocity
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
ms.openlocfilehash: 0aa5831e2262602ee46bd69031e5927a86b978e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364085"
---
# <a name="cparabolictransitionfromacceleration-class"></a>CParabolicTransitionFromAcceleration Sınıf

Parabolik ivme geçişini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CParabolicTransitionFromAcceleration : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CParaboicTransitionFromAcceleration::CParaboicTransitionFromAcceleration From](#cparabolictransitionfromacceleration)|Parabolik ivme geçişi kurar ve belirtilen parametrelerle başlatleştirir.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CParaboicTransitionFromAcceleration::Oluştur](#create)|Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. (CBaseTransition geçersiz [kılar::Oluştur](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CParaboicTransitionFromAcceleration::m_dblAcceleration](#m_dblacceleration)|Geçiş sırasında animasyon değişkeninin ivmesi.|
|[CParaboicTransitionFromAcceleration::m_dblFinalValue](#m_dblfinalvalue)|Geçişin sonundaki animasyon değişkeninin değeri.|
|[CParaboicTransitionFromAcceleration::m_dblFinalVelocity](#m_dblfinalvelocity)|Geçiş in sonundaanimasyon değişkeninin hızı.|

## <a name="remarks"></a>Açıklamalar

Parabolik ivme geçişi sırasında, animasyon değişkeninin değeri ilk değerden belirli bir hızda biten son değere değişir. Hızlanma oranını belirterek değişkenin son değere ne kadar hızlı ulaştığını kontrol edebilirsiniz. Tüm geçişler otomatik olarak temizlenerek, operatör yeni kullanılarak ayrılması önerilir. Kapsüllü IUIAnimationTransition COM nesnesi CAnimationController tarafından oluşturulur::AnimateGroup, o zamana kadar NULL' s. Bu COM nesnesinin oluşturulduktan sonra üye değişkenleri değiştirmenin hiçbir etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CParaboicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="cparabolictransitionfromaccelerationcparabolictransitionfromacceleration"></a><a name="cparabolictransitionfromacceleration"></a>CParaboicTransitionFromAcceleration::CParaboicTransitionFromAcceleration From

Parabolik ivme geçişi kurar ve belirtilen parametrelerle başlatleştirir.

```
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,
    DOUBLE dblFinalVelocity,
    DOUBLE dblAcceleration);
```

### <a name="parameters"></a>Parametreler

*dblFinalValue*<br/>
Geçişin sonundaki animasyon değişkeninin değeri.

*dblFinalVelocity*<br/>
Geçiş in sonundaanimasyon değişkeninin hızı.

*dblHızlanma*<br/>
Geçiş sırasında animasyon değişkeninin ivmesi.

## <a name="cparabolictransitionfromaccelerationcreate"></a><a name="create"></a>CParaboicTransitionFromAcceleration::Oluştur

Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* /* not used */);
```

### <a name="parameters"></a>Parametreler

*pKütüphane*<br/>
Standart geçişlerin oluşturulmasından sorumlu geçiş kitaplığı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa DOĞRU; aksi takdirde YANLIŞ.

## <a name="cparabolictransitionfromaccelerationm_dblacceleration"></a><a name="m_dblacceleration"></a>CParaboicTransitionFromAcceleration::m_dblAcceleration

Geçiş sırasında animasyon değişkeninin ivmesi.

```
DOUBLE m_dblAcceleration;
```

## <a name="cparabolictransitionfromaccelerationm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>CParaboicTransitionFromAcceleration::m_dblFinalValue

Geçişin sonundaki animasyon değişkeninin değeri.

```
DOUBLE m_dblFinalValue;
```

## <a name="cparabolictransitionfromaccelerationm_dblfinalvelocity"></a><a name="m_dblfinalvelocity"></a>CParaboicTransitionFromAcceleration::m_dblFinalVelocity

Geçiş in sonundaanimasyon değişkeninin hızı.

```
DOUBLE m_dblFinalVelocity;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
