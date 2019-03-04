---
title: CLinearTransitionFromSpeed sınıfı
ms.date: 11/04/2016
f1_keywords:
- CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::Create
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblSpeed
helpviewer_keywords:
- CLinearTransitionFromSpeed [MFC], CLinearTransitionFromSpeed
- CLinearTransitionFromSpeed [MFC], Create
- CLinearTransitionFromSpeed [MFC], m_dblFinalValue
- CLinearTransitionFromSpeed [MFC], m_dblSpeed
ms.assetid: 8f159a1c-8893-4017-951e-09e5758aba7d
ms.openlocfilehash: 1efa9806267958b4221ee112e56f242c7e25a8f0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260705"
---
# <a name="clineartransitionfromspeed-class"></a>CLinearTransitionFromSpeed sınıfı

Bir doğrusal hızlı geçişi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CLinearTransitionFromSpeed : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CLinearTransitionFromSpeed::CLinearTransitionFromSpeed](#clineartransitionfromspeed)|Bir doğrusal hızlı geçişi nesnesi oluşturur ve hız ve son değer ile başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CLinearTransitionFromSpeed::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CLinearTransitionFromSpeed::m_dblFinalValue](#m_dblfinalvalue)|Geçiş sonunda animasyon değişkeninin değeri.|
|[CLinearTransitionFromSpeed::m_dblSpeed](#m_dblspeed)|Hız değişkenin mutlak değeri.|

## <a name="remarks"></a>Açıklamalar

Bir doğrusal hızlı geçişi sırasında belirtilen bir fiyat karşılığında animasyon değişkenin değerini değiştirir. Geçiş süresi başlangıç değeri belirtilen son değeri arasındaki farkı tarafından belirlenir. Tüm geçiş işlemleri otomatik olarak temizlenir olduğundan, bunları ayrılan önerilir işleci kullanarak yeni. NULL ise kapsüllenmiş IUIAnimationTransition COM nesnesi kadar CAnimationController::AnimateGroup tarafından oluşturulur. Üye değişkenleri tüketimi bu COM nesnesi oluşturulmasını etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CLinearTransitionFromSpeed](../../mfc/reference/clineartransitionfromspeed-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="clineartransitionfromspeed"></a>  CLinearTransitionFromSpeed::CLinearTransitionFromSpeed

Bir doğrusal hızlı geçişi nesnesi oluşturur ve hız ve son değer ile başlatır.

```
CLinearTransitionFromSpeed(
    DOUBLE dblSpeed,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Parametreler

*dblSpeed*<br/>
Hız değişkenin mutlak değeri.

*dblFinalValue*<br/>
Geçiş sonunda animasyon değişkeninin değeri.

##  <a name="create"></a>  CLinearTransitionFromSpeed::Create

Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Bir işaretçi bir [IUIAnimationTransitionLibrary arabirimi](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), standart geçişleri kitaplığını tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa TRUE; Aksi durumda FALSE.

##  <a name="m_dblfinalvalue"></a>  CLinearTransitionFromSpeed::m_dblFinalValue

Geçiş sonunda animasyon değişkeninin değeri.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_dblspeed"></a>  CLinearTransitionFromSpeed::m_dblSpeed

Hız değişkenin mutlak değeri.

```
DOUBLE m_dblSpeed;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
