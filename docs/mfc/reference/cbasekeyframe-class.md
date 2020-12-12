---
description: 'Daha fazla bilgi edinin: CBaseKeyFrame sınıfı'
title: CBaseKeyFrame sınıfı
ms.date: 11/04/2016
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
helpviewer_keywords:
- CBaseKeyFrame [MFC], CBaseKeyFrame
- CBaseKeyFrame [MFC], AddToStoryboard
- CBaseKeyFrame [MFC], GetAnimationKeyframe
- CBaseKeyFrame [MFC], IsAdded
- CBaseKeyFrame [MFC], IsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_bAdded
- CBaseKeyFrame [MFC], m_bIsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_keyframe
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
ms.openlocfilehash: 0bebd91183eab9be71e8df4928dc621565718cb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261267"
---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame sınıfı

, Bir ana karenin temel işlevlerini uygular.

## <a name="syntax"></a>Syntax

```
class CBaseKeyFrame : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBaseKeyFrame:: CBaseKeyFrame](#cbasekeyframe)|Bir ana kare nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBaseKeyFrame:: AddToStoryboard](#addtostoryboard)|Görsel taslağa bir ana kare ekler.|
|[CBaseKeyFrame:: GetAnimationKeyframe](#getanimationkeyframe)|Temeldeki ana kare değerini döndürür.|
|[CBaseKeyFrame:: IsAdded](#isadded)|Görsel taslağa bir ana kare eklenip eklenmeyeceğini söyler.|
|[CBaseKeyFrame:: ıskeyframeatoffset](#iskeyframeatoffset)|Ana karenin, uzaklığında veya geçişten sonra film şeridine eklenip eklenmeyeceğini belirtir.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CBaseKeyFrame:: m_bAdded](#m_badded)|Bu ana karenin bir görsel taslağa eklenip eklenmeyeceğini belirtir.|
|[CBaseKeyFrame:: m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Bu ana karenin, varolan başka bir ana kareden veya bazı geçişin sonundaki bir uzaklığa görsel taslağa eklenip eklenmeyeceğini belirtir.|
|[CBaseKeyFrame:: m_keyframe](#m_keyframe)|Bir Windows animasyon API 'SI ana karesini temsil eder. Bir ana kare başlatılmazsa UI_ANIMATION_KEYFRAME_STORYBOARD_START önceden tanımlanmış değere ayarlanır.|

## <a name="remarks"></a>Açıklamalar

UI_ANIMATION_KEYFRAME değişkenini kapsüller. Tüm ana kare uygulamaları için bir temel sınıf işlevi görür. Bir ana kare, bir film şeridi içinde zaman içindeki bir süreyi temsil eder ve geçişlerin başlangıç ve bitiş zamanlarını belirtmek için kullanılabilir. Görsel taslağa belirtilen uzaklığa (zamanında) veya belirtilen geçişten sonra eklenen ana karelere eklenen iki ana kare türü vardır. Bazı geçişlerin süreleri animasyon başlamadan önce tanınamadığından, bazı ana karelerin gerçek değerleri yalnızca çalışma zamanında belirlenir. Ana kareler, bağımlılarına bağlı olabileceğinden, ana kare zincirlerini oluştururken sonsuz yinelenen işlemleri engellemek önemlidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CBaseKeyFrame`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="cbasekeyframeaddtostoryboard"></a><a name="addtostoryboard"></a> CBaseKeyFrame:: AddToStoryboard

Görsel taslağa bir ana kare ekler.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslağa yönelik işaretçi.

*Boderin ekleme*<br/>
Bu parametre TRUE ise ve eklenmekte olan ana kare diğer bir ana kareye veya geçişe göre farklılık gösteriyorsa, bu yöntem, önce bu ana kareyi veya geçişi bir film şeridine eklemeye çalışır.

### <a name="return-value"></a>Dönüş Değeri

Ana kare, görsel taslağa başarıyla eklendiyse TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, görsel taslağa bir ana kare eklemek için çağırılır.

## <a name="cbasekeyframecbasekeyframe"></a><a name="cbasekeyframe"></a> CBaseKeyFrame:: CBaseKeyFrame

Bir ana kare nesnesi oluşturur.

```
CBaseKeyFrame();
```

## <a name="cbasekeyframegetanimationkeyframe"></a><a name="getanimationkeyframe"></a> CBaseKeyFrame:: GetAnimationKeyframe

Temeldeki ana kare değerini döndürür.

```
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir ana kare. Varsayılan değer UI_ANIMATION_KEYFRAME_STORYBOARD_START.

### <a name="remarks"></a>Açıklamalar

Bu, temeldeki ana kare değerine yönelik bir erişimcidir.

## <a name="cbasekeyframeisadded"></a><a name="isadded"></a> CBaseKeyFrame:: IsAdded

Görsel taslağa bir ana kare eklenip eklenmeyeceğini söyler.

```
BOOL IsAdded() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görsel taslağa bir ana kare eklenirse doğru; otehrwise yanlış.

### <a name="remarks"></a>Açıklamalar

Temel sınıfta IsAdded her zaman TRUE değerini döndürür, ancak türetilmiş sınıflarda geçersiz kılınır.

## <a name="cbasekeyframeiskeyframeatoffset"></a><a name="iskeyframeatoffset"></a> CBaseKeyFrame:: ıskeyframeatoffset

Ana karenin, uzaklığında veya geçişten sonra film şeridine eklenip eklenmeyeceğini belirtir.

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bir uzaklığa göre ana karenin görsel taslağa eklenmesi gerekiyorsa TRUE. Bir geçişten sonra ana karenin görsel taslağa eklenmesi gerekiyorsa FALSE.

### <a name="remarks"></a>Açıklamalar

Ana karenin, uzaklığında görsel taslağa eklenip eklenmeyeceğini belirtir. Türetilmiş bir sınıfta, fark veya geçiş belirtilmesi gerekir.

## <a name="cbasekeyframem_badded"></a><a name="m_badded"></a> CBaseKeyFrame:: m_bAdded

Bu ana karenin bir görsel taslağa eklenip eklenmeyeceğini belirtir.

```
BOOL m_bAdded;
```

## <a name="cbasekeyframem_biskeyframeatoffset"></a><a name="m_biskeyframeatoffset"></a> CBaseKeyFrame:: m_bIsKeyframeAtOffset

Bu ana karenin, varolan başka bir ana kareden veya bazı geçişin sonundaki bir uzaklığa görsel taslağa eklenip eklenmeyeceğini belirtir.

```
BOOL m_bIsKeyframeAtOffset;
```

## <a name="cbasekeyframem_keyframe"></a><a name="m_keyframe"></a> CBaseKeyFrame:: m_keyframe

Bir Windows animasyon API 'SI ana karesini temsil eder. Bir ana kare başlatılmazsa UI_ANIMATION_KEYFRAME_STORYBOARD_START önceden tanımlanmış değere ayarlanır.

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
