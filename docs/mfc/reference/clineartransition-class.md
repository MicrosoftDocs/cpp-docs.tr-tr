---
title: CLinearTransition sınıfı
ms.date: 11/04/2016
f1_keywords:
- CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::Create
- AFXANIMATIONCONTROLLER/CLinearTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransition::m_duration
helpviewer_keywords:
- CLinearTransition [MFC], CLinearTransition
- CLinearTransition [MFC], Create
- CLinearTransition [MFC], m_dblFinalValue
- CLinearTransition [MFC], m_duration
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
ms.openlocfilehash: 4aa2d9955d2bbf98d2d7829806c4bcbd76340847
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270806"
---
# <a name="clineartransition-class"></a>CLinearTransition sınıfı

Bir doğrusal geçişi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CLinearTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CLinearTransition::CLinearTransition](#clineartransition)|Bir doğrusal geçişi nesnesi oluşturur ve onu süresi ve son değer ile başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CLinearTransition::Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığı çağırır. (Geçersiz kılmaları [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CLinearTransition::m_dblFinalValue](#m_dblfinalvalue)|Geçiş sonunda animasyon değişkeninin değeri.|
|[CLinearTransition::m_duration](#m_duration)|Geçiş süresi.|

## <a name="remarks"></a>Açıklamalar

Bir doğrusal geçişi sırasında animasyon değişkenin değerini belirtilen son değer için başlangıç değerinden doğrusal olarak geçer. Tüm geçiş işlemleri otomatik olarak temizlenir olduğundan, bunları ayrılan önerilir işleci kullanarak yeni. NULL ise kapsüllenmiş IUIAnimationTransition COM nesnesi kadar CAnimationController::AnimateGroup tarafından oluşturulur. Üye değişkenleri tüketimi bu COM nesnesi oluşturulmasını etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CLinearTransition](../../mfc/reference/clineartransition-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="clineartransition"></a>  CLinearTransition::CLinearTransition

Bir doğrusal geçişi nesnesi oluşturur ve onu süresi ve son değer ile başlatır.

```
CLinearTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Parametreler

*Süresi*<br/>
Geçiş süresi.

*dblFinalValue*<br/>
Geçiş sonunda animasyon değişkeninin değeri.

##  <a name="create"></a>  CLinearTransition::Create

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

##  <a name="m_dblfinalvalue"></a>  CLinearTransition::m_dblFinalValue

Geçiş sonunda animasyon değişkeninin değeri.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_duration"></a>  CLinearTransition::m_duration

Geçiş süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
