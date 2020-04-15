---
title: CBaseKeyFrame Sınıfı
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
ms.openlocfilehash: 3fcd55f6a157f4b837090a3608fb509b870aae5d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352985"
---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame Sınıfı

Anahtar çerçevenin temel işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CBaseKeyFrame : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|Anahtar kare nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|Film şeridine bir anahtar çerçevesi ekler.|
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|Temel anahtar kare değerini verir.|
|[CbaseKeyFrame::Isadded](#isadded)|Film şeridine bir anahtar çerçevesi eklenip eklenmediğini söyler.|
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|Anahtar çerçevesinin ofset'te veya geçişten sonra film şeridine eklenip eklenmeyeceğini belirtir.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CBaseKeyFrame::m_bAdded](#m_badded)|Bu anahtar çerçevenin bir film şeridine eklenip eklenmediğini belirtir.|
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Bu anahtar çerçevenin, varolan başka bir anahtar çerçeveden bir ofsette mi yoksa bazı geçişin sonunda mı bir ofset olarak film şeridine eklenmesi gerektiğini belirtir.|
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Windows Animasyon API anahtar çerçeveyi temsil eder. Bir anahtar çerçevesi baş harfe başlatıldığında, önceden tanımlanmış değer UI_ANIMATION_KEYFRAME_STORYBOARD_START olarak ayarlanır.|

## <a name="remarks"></a>Açıklamalar

UI_ANIMATION_KEYFRAME değişkeni kapsüller. Herhangi bir anahtar kare uygulaması için bir taban sınıf olarak hizmet vermektedir. Anahtar çerçevesi, bir film şeridi içindeki bir anı temsil eder ve geçişlerin başlangıç ve bitiş saatlerini belirtmek için kullanılabilir. İki tür anahtar kare vardır : belirtilen ofsette (zaman içinde) film şeridine eklenen anahtar kareler veya belirtilen geçişten sonra eklenen anahtar kareler. Animasyon başlamadan önce bazı geçişlerin süreleri bilinemediğinden, bazı anahtar karelerin gerçek değerleri yalnızca çalışma zamanında belirlenir. Anahtar kareler geçişlere bağlı olabileceğinden, anahtar kareler sırayla anahtar çerçevelerine bağlıdır, anahtar kare zincirleri inşa ederken sonsuz yinelemeleri önlemek önemlidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CBaseKeyFrame`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="cbasekeyframeaddtostoryboard"></a><a name="addtostoryboard"></a>CBaseKeyFrame::AddToStoryboard

Film şeridine bir anahtar çerçevesi ekler.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Bir film şeridi için bir işaretçi.

*bDeepAdd*<br/>
Bu parametre TRUE ise ve eklenen anahtar çerçeve başka bir anahtar çerçeveye veya geçişe bağlıysa, bu yöntem önce bu anahtar çerçevesi veya geçiş şeridine eklemeye çalışır.

### <a name="return-value"></a>Dönüş Değeri

Anahtar çerçevesi film şeridine başarıyla eklenmiştirsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, film şeridine bir anahtar çerçevesi eklemek için adlandırılır.

## <a name="cbasekeyframecbasekeyframe"></a><a name="cbasekeyframe"></a>CBaseKeyFrame::CBaseKeyFrame

Anahtar kare nesnesi oluşturuyor.

```
CBaseKeyFrame();
```

## <a name="cbasekeyframegetanimationkeyframe"></a><a name="getanimationkeyframe"></a>CBaseKeyFrame::GetAnimationKeyframe

Temel anahtar kare değerini verir.

```
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir anahtar kare. Varsayılan değer UI_ANIMATION_KEYFRAME_STORYBOARD_START.

### <a name="remarks"></a>Açıklamalar

Bu, temel anahtar kare değerine bir erişimdir.

## <a name="cbasekeyframeisadded"></a><a name="isadded"></a>CbaseKeyFrame::Isadded

Film şeridine bir anahtar çerçevesi eklenip eklenmediğini söyler.

```
BOOL IsAdded() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir film şeridine bir anahtar çerçevesi eklenirse DOĞRU; otehrwise YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Temel sınıfta IsAdded her zaman TRUE döndürür, ancak türemiş sınıflarda geçersiz kılındı.

## <a name="cbasekeyframeiskeyframeatoffset"></a><a name="iskeyframeatoffset"></a>CBaseKeyFrame::IsKeyframeAtOffset

Anahtar çerçevesinin ofset'te veya geçişten sonra film şeridine eklenip eklenmeyeceğini belirtir.

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>Dönüş Değeri

Anahtar çerçevesi belirli bir ofset de film şeridine eklenecekse DOĞRU. Anahtar çerçevesi bir geçişten sonra film şeridine eklenecekse YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Anahtar çerçevesinin ofset olarak film şeridine eklenip eklenmeyeceğini belirtir. Ofset veya geçiş türemiş bir sınıfta belirtilmelidir.

## <a name="cbasekeyframem_badded"></a><a name="m_badded"></a>CBaseKeyFrame::m_bAdded

Bu anahtar çerçevenin bir film şeridine eklenip eklenmediğini belirtir.

```
BOOL m_bAdded;
```

## <a name="cbasekeyframem_biskeyframeatoffset"></a><a name="m_biskeyframeatoffset"></a>CBaseKeyFrame::m_bIsKeyframeAtOffset

Bu anahtar çerçevenin, varolan başka bir anahtar çerçeveden bir ofsette mi yoksa bazı geçişin sonunda mı bir ofset olarak film şeridine eklenmesi gerektiğini belirtir.

```
BOOL m_bIsKeyframeAtOffset;
```

## <a name="cbasekeyframem_keyframe"></a><a name="m_keyframe"></a>CBaseKeyFrame::m_keyframe

Windows Animasyon API anahtar çerçeveyi temsil eder. Bir anahtar çerçevesi baş harfe başlatıldığında, önceden tanımlanmış değer UI_ANIMATION_KEYFRAME_STORYBOARD_START olarak ayarlanır.

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
