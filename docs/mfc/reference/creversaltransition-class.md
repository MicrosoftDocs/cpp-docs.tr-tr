---
title: CReversalTransition Sınıf
ms.date: 11/04/2016
f1_keywords:
- CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::Create
- AFXANIMATIONCONTROLLER/CReversalTransition::m_duration
helpviewer_keywords:
- CReversalTransition [MFC], CReversalTransition
- CReversalTransition [MFC], Create
- CReversalTransition [MFC], m_duration
ms.assetid: e89516be-2d07-4885-95a8-fc278f46e3ad
ms.openlocfilehash: 73d12fb6bbaefcfac1437248ebe11f3a5c24c45b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368310"
---
# <a name="creversaltransition-class"></a>CReversalTransition Sınıf

Ters geçişi kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CReversalTransition : public CBaseTransition;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CreversalTransition::creversaltransition](#creversaltransition)|Ters geçiş nesnesi oluşturuyor ve süresini başharfe döndürer.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CReversalTransition::Create](#create)|Kapsüllü geçiş COM nesnesi oluşturmak için geçiş kitaplığını çağırır. (CBaseTransition geçersiz [kılar::Oluştur](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CReversalTransition::m_duration](#m_duration)|Geçiş süresi.|

## <a name="remarks"></a>Açıklamalar

Tersine çevirme geçişi, belirli bir süre boyunca yönünü sorunsuz bir şekilde değiştirir. Son değer ilk değerle aynı olacak ve son hız ilk hızın negatifi olacaktır. Tüm geçişler otomatik olarak temizlenerek, operatör yeni kullanılarak ayrılması önerilir. Kapsüllü IUIAnimationTransition COM nesnesi CAnimationController tarafından oluşturulur::AnimateGroup, o zamana kadar NULL' s. Bu COM nesnesinin oluşturulduktan sonra üye değişkenleri değiştirmenin hiçbir etkisi yoktur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CReversalTransition](../../mfc/reference/creversaltransition-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="creversaltransitioncreate"></a><a name="create"></a>CReversalTransition::Create

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

## <a name="creversaltransitioncreversaltransition"></a><a name="creversaltransition"></a>CreversalTransition::creversaltransition

Ters geçiş nesnesi oluşturuyor ve süresini başharfe döndürer.

```
CReversalTransition(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
Geçiş süresi.

## <a name="creversaltransitionm_duration"></a><a name="m_duration"></a>CReversalTransition::m_duration

Geçiş süresi.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
