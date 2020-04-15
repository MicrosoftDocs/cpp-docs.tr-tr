---
title: CSinusoidalTransitionFromRange Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMaximumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMinimumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_period
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_slope
helpviewer_keywords:
- CSinusoidalTransitionFromRange [MFC], CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange [MFC], Create
- CSinusoidalTransitionFromRange [MFC], m_dblMaximumValue
- CSinusoidalTransitionFromRange [MFC], m_dblMinimumValue
- CSinusoidalTransitionFromRange [MFC], m_duration
- CSinusoidalTransitionFromRange [MFC], m_period
- CSinusoidalTransitionFromRange [MFC], m_slope
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
ms.openlocfilehash: 0612a4b365b928d3c9be6d76168a76b4ee1caa85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318251"
---
# <a name="csinusoidaltransitionfromrange-class"></a>CSinusoidalTransitionFromRange Sınıfı

Belirli bir salınım aralığına sahip bir sinüzoidal aralık lı geçişi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CSinusoidalTransitionFromRange : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|Bir geçiş nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSinusoidalTransitionFromRange::Oluştur](#create)|Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. (CBaseTransition geçersiz [kılar::Oluştur](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CSinusoidalTransitionFromRange::m_dblMaximumValue](#m_dblmaximumvalue)|Sinüzoidal dalganın zirvesindeki animasyon değişkeninin değeri.|
|[CSinusoidalTransitionFromRange::m_dblMinimumValue](#m_dblminimumvalue)|Sinüzoidal dalganın bir çukurundaki animasyon değişkeninin değeri.|
|[CSinusoidalTransitionFromRange::m_duration](#m_duration)|Geçiş süresi.|
|[CSinusoidalTransitionFromRange::m_period](#m_period)|Saniyeler içinde sinüzoidal dalganın salınım dönemi.|
|[CSinusoidalTransitionFromRange::m_slope](#m_slope)|Geçişin başlangıcındaki eğim.|

## <a name="remarks"></a>Açıklamalar

Animasyon değişkeninin değeri, sinüzoidal aralıklı geçişin tüm süresi boyunca belirtilen minimum ve maksimum değerler arasında dalgalandırılıyor. Eğim parametresi, diğer parametrelertarafından belirtilen iki olası sinüs dalgası arasında ayrıştırmak için kullanılır. Tüm geçişler otomatik olarak temizlenerek, operatör yeni kullanılarak ayrılması önerilir. Kapsüllü IUIAnimationTransition COM nesnesi CAnimationController tarafından oluşturulur::AnimateGroup, o zamana kadar NULL' s. Bu COM nesnesinin oluşturulduktan sonra üye değişkenleri değiştirmenin hiçbir etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="csinusoidaltransitionfromrangecreate"></a><a name="create"></a>CSinusoidalTransitionFromRange::Oluştur

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

## <a name="csinusoidaltransitionfromrangecsinusoidaltransitionfromrange"></a><a name="csinusoidaltransitionfromrange"></a>CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange

Bir geçiş nesnesi oluşturuyor.

```
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,
    DOUBLE dblMinimumValue,
    DOUBLE dblMaximumValue,
    UI_ANIMATION_SECONDS period,
    UI_ANIMATION_SLOPE slope);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
Geçiş süresi.

*dblMinimumValue*<br/>
Sinüzoidal dalganın bir çukurundaki animasyon değişkeninin değeri.

*dblMaximumValue*<br/>
Sinüzoidal dalganın zirvesindeki animasyon değişkeninin değeri.

*Dönem*<br/>
Saniyeler içinde sinüzoidal dalganın salınım dönemi.

*Eğim*<br/>
Geçişin başlangıcındaki eğim.

## <a name="csinusoidaltransitionfromrangem_dblmaximumvalue"></a><a name="m_dblmaximumvalue"></a>CSinusoidalTransitionFromRange::m_dblMaximumValue

Sinüzoidal dalganın zirvesindeki animasyon değişkeninin değeri.

```
DOUBLE m_dblMaximumValue;
```

## <a name="csinusoidaltransitionfromrangem_dblminimumvalue"></a><a name="m_dblminimumvalue"></a>CSinusoidalTransitionFromRange::m_dblMinimumValue

Sinüzoidal dalganın bir çukurundaki animasyon değişkeninin değeri.

```
DOUBLE m_dblMinimumValue;
```

## <a name="csinusoidaltransitionfromrangem_duration"></a><a name="m_duration"></a>CSinusoidalTransitionFromRange::m_duration

Geçiş süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromrangem_period"></a><a name="m_period"></a>CSinusoidalTransitionFromRange::m_period

Saniyeler içinde sinüzoidal dalganın salınım dönemi.

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="csinusoidaltransitionfromrangem_slope"></a><a name="m_slope"></a>CSinusoidalTransitionFromRange::m_slope

Geçişin başlangıcındaki eğim.

```
UI_ANIMATION_SLOPE m_slope;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
