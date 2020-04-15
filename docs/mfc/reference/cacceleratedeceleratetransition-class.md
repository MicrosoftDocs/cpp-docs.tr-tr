---
title: CAccelerateDecelerateGeçiş Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
ms.openlocfilehash: 356ba30e6d9a638672d2c356676735ebfaed8f3e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371144"
---
# <a name="cacceleratedeceleratetransition-class"></a>CAccelerateDecelerateGeçiş Sınıfı

Hızlandırılmış yavaşlama geçişi uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAccelerateDecelerateGeçiş::CAccelerateDecelerateGeçiş](#cacceleratedeceleratetransition)|Bir geçiş nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAccelerateDecelerateGeçiş::Oluştur](#create)|Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. (CBaseTransition geçersiz [kılar::Oluştur](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAccelerateDecelerateGeçiş::m_accelerationRatio](#m_accelerationratio)|Zamana hızlanma için harcanan zaman oranı.|
|[CAccelerateDecelerateGeçiş::m_decelerationRatio](#m_decelerationratio)|Yavaşlamak için harcanan zamanın süresine oranı.|
|[CAccelerateDecelerateGeçiş::m_duration](#m_duration)|Geçiş süresi.|
|[CAccelerateDecelerateGeçiş::m_finalValue](#m_finalvalue)|Geçişin sonundaki animasyon değişkeninin değeri.|

## <a name="remarks"></a>Açıklamalar

Hızlandırıcı yavaşlama geçişi sırasında, animasyon değişkeni hızlanır ve geçiş süresi boyunca yavaşlar ve belirli bir değerde sona erer. Farklı hızlanma ve yavaşlama oranları belirterek değişkenin bağımsız olarak ne kadar hızlı hızlanıp yavaşladığını kontrol edebilirsiniz. İlk hız sıfır olduğunda, hızlanma oranı değişkenin hızlanarak harcayacağı sürenin kesirdir; aynı şekilde yavaşlama oranı ile. İlk hız sıfır değilse, hız sıfıra ulaşan ve geçiş sonu arasındaki zaman kesirdir. Hızlanma oranı ve yavaşlama oranı maksimum 1.0 olarak karşılanmalıdır. Tüm geçişler otomatik olarak temizlenerek, operatör yeni kullanılarak ayrılması önerilir. Kapsüllü IUIAnimationTransition COM nesnesi CAnimationController tarafından oluşturulur::AnimateGroup, o zamana kadar NULL' s. Bu COM nesnesinin oluşturulduktan sonra üye değişkenleri değiştirmenin hiçbir etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="cacceleratedeceleratetransitioncacceleratedeceleratetransition"></a><a name="cacceleratedeceleratetransition"></a>CAccelerateDecelerateGeçiş::CAccelerateDecelerateGeçiş

Bir geçiş nesnesi oluşturuyor.

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
Geçiş süresi.

*finalValue*<br/>
Geçişin sonundaki animasyon değişkeninin değeri.

*Accelerationratio*<br/>
Zamana hızlanma için harcanan zaman oranı.

*Decelerationratio*<br/>
Yavaşlamak için harcanan zamanın süresine oranı.

## <a name="cacceleratedeceleratetransitioncreate"></a><a name="create"></a>CAccelerateDecelerateGeçiş::Oluştur

Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>Parametreler

*pKütüphane*<br/>
Standart geçişler kitaplığını tanımlayan [IUIAnimationTransitionLibrary arabirimine](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa DOĞRU; aksi takdirde YANLIŞ.

## <a name="cacceleratedeceleratetransitionm_accelerationratio"></a><a name="m_accelerationratio"></a>CAccelerateDecelerateGeçiş::m_accelerationRatio

Zamana hızlanma için harcanan zaman oranı.

```
DOUBLE m_accelerationRatio;
```

## <a name="cacceleratedeceleratetransitionm_decelerationratio"></a><a name="m_decelerationratio"></a>CAccelerateDecelerateGeçiş::m_decelerationRatio

Yavaşlamak için harcanan zamanın süresine oranı.

```
DOUBLE m_decelerationRatio;
```

## <a name="cacceleratedeceleratetransitionm_duration"></a><a name="m_duration"></a>CAccelerateDecelerateGeçiş::m_duration

Geçiş süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="cacceleratedeceleratetransitionm_finalvalue"></a><a name="m_finalvalue"></a>CAccelerateDecelerateGeçiş::m_finalValue

Geçişin sonundaki animasyon değişkeninin değeri.

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
