---
description: 'Daha fazla bilgi edinin: CInstantaneousTransition Class'
title: CInstantaneousTransition sınıfı
ms.date: 11/04/2016
f1_keywords:
- CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::Create
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::m_dblFinalValue
helpviewer_keywords:
- CInstantaneousTransition [MFC], CInstantaneousTransition
- CInstantaneousTransition [MFC], Create
- CInstantaneousTransition [MFC], m_dblFinalValue
ms.assetid: c3d5121f-2c6b-4221-9e57-10e082a31120
ms.openlocfilehash: 1152d7ed6317b5f1d0c30929cc908266594deb1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143578"
---
# <a name="cinstantaneoustransition-class"></a>CInstantaneousTransition sınıfı

Anlık bir geçişi kapsüller.

## <a name="syntax"></a>Syntax

```
class CInstantaneousTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInstantaneousTransition:: CInstantaneousTransition](#cinstantaneoustransition)|Bir geçiş nesnesi oluşturur ve son değerini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CInstantaneousTransition:: Create](#create)|Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. ( [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create)geçersiz kılar.)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CInstantaneousTransition:: m_dblFinalValue](#m_dblfinalvalue)|Geçişin sonundaki animasyon değişkeninin değeri.|

## <a name="remarks"></a>Açıklamalar

Anında geçiş sırasında animasyon değişkeninin değeri, geçerli değerinden belirtilen bir son değere anında değişir. Bu geçişin süresi her zaman sıfırdır. Tüm geçişler otomatik olarak temizlendiğinden, Yeni işleç kullanılarak ayrılmaları önerilir. Encapsulated IUIAnimationTransition COM nesnesi, NULL olana kadar CAnimationController:: AnimateGroup tarafından oluşturulur. Bu COM nesnesi oluşturulduktan sonra üye değişkenlerinin değiştirilmesinin etkisi olmaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CInstantaneousTransition](../../mfc/reference/cinstantaneoustransition-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="cinstantaneoustransitioncinstantaneoustransition"></a><a name="cinstantaneoustransition"></a> CInstantaneousTransition:: CInstantaneousTransition

Bir geçiş nesnesi oluşturur ve son değerini başlatır.

```
CInstantaneousTransition(DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Parametreler

*Dblfinaldeğeri*<br/>
Geçişin sonundaki animasyon değişkeninin değeri.

## <a name="cinstantaneoustransitioncreate"></a><a name="create"></a> CInstantaneousTransition:: Create

Kapsüllenmiş geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametreler

*pLibrary*<br/>
Standart geçişlerin kitaplığını tanımlayan [ıuıanimationgeçişli Tionlibrary arabirimine](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Geçiş başarıyla oluşturulursa doğru; Aksi halde yanlış.

## <a name="cinstantaneoustransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a> CInstantaneousTransition:: m_dblFinalValue

Geçişin sonundaki animasyon değişkeninin değeri.

```
DOUBLE m_dblFinalValue;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
