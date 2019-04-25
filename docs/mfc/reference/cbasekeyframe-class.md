---
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
ms.openlocfilehash: d36c924d30bd728fcd54b6cdf6805ade25e20b5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218413"
---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame sınıfı

Bir ana karenin temel işlevlerini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CBaseKeyFrame : public CObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|Bir ana kare nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|Görsel taslak için bir anahtar kare ekler.|
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|Temel alınan ana kare değeri döndürür.|
|[CBaseKeyFrame::IsAdded](#isadded)|Bir anahtar kare görsel taslağa dönüştürme eklenip eklenmediğini belirtir.|
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|Ana kare uzaklığında veya geçişten sonra görsel taslağa dönüştürme eklenip eklenmeyeceğini belirtir.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CBaseKeyFrame::m_bAdded](#m_badded)|Bu ana kare bir film şeridini eklenip eklenmediğini belirtir.|
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Bu ana kare var olan başka bir ana kare bir uzaklığı veya bazı geçiş sonunda görsel taslağa dönüştürme eklenip eklenmeyeceğini belirtir.|
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Bir Windows animasyon API'sı ana karesini temsil eder. Bir anahtar kare başlatılmadan UI_ANIMATION_KEYFRAME_STORYBOARD_START önceden tanımlanmış değerine ayarlanır.|

## <a name="remarks"></a>Açıklamalar

UI_ANIMATION_KEYFRAME değişkeni kapsüller. Herhangi bir ana kare uygulaması için temel sınıf olarak görev yapar. Bir anahtar kare biraz zaman içinde bir film şeridi temsil eder ve başlangıç ve bitiş zamanları geçişlerinin belirtmek için kullanılabilir. Ana kareleri - ana kareleri belirtilen uzaklık (zaman içinde) film şeridi eklenen ya da belirtilen geçişten sonra eklenen ana kareleri iki tür vardır. Bazı geçiş süreleri animasyon başlatılmadan önce bilinen olamaz çünkü bazı ana kareleri gerçek değerleri yalnızca çalışma zamanında belirlenir. Ana kareleri, üzerinde ana kareleri bağlı olan ve dolayısıyla geçişleri üzerinde bağlı olabileceği için ana kare zincirleri derlenirken sonsuz özyinelemeler önlemek önemlidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CBaseKeyFrame`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="addtostoryboard"></a>  CBaseKeyFrame::AddToStoryboard

Görsel taslak için bir anahtar kare ekler.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslak için bir işaretçi.

*bDeepAdd*<br/>
Bu parametre TRUE ise ve diğer bazı ana kare veya geçiş eklenen ana kare bağlıdır, bu ana kare veya geçiş önce film şeridi eklemek bu yöntem çalışır.

### <a name="return-value"></a>Dönüş Değeri

Ana kare başarıyla film şeridi eklenmişse TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Görsel taslak için bir anahtar kare eklemek için bu yöntem çağrılır.

##  <a name="cbasekeyframe"></a>  CBaseKeyFrame::CBaseKeyFrame

Bir ana kare nesne oluşturur.

```
CBaseKeyFrame();
```

##  <a name="getanimationkeyframe"></a>  CBaseKeyFrame::GetAnimationKeyframe

Temel alınan ana kare değeri döndürür.

```
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir ana kare. UI_ANIMATION_KEYFRAME_STORYBOARD_START varsayılan değerdir.

### <a name="remarks"></a>Açıklamalar

Temel alınan ana kare değere bir erişimci budur.

##  <a name="isadded"></a>  CBaseKeyFrame::IsAdded

Bir anahtar kare görsel taslağa dönüştürme eklenip eklenmediğini belirtir.

```
BOOL IsAdded() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görsel taslak için bir anahtar kare eklenirse TRUE; otehrwise FALSE.

### <a name="remarks"></a>Açıklamalar

Temel sınıfta IsAdded her zaman TRUE değerini döndürür, ancak türetilmiş sınıflarda geçersiz kılındı.

##  <a name="iskeyframeatoffset"></a>  CBaseKeyFrame::IsKeyframeAtOffset

Ana kare uzaklığında veya geçişten sonra görsel taslağa dönüştürme eklenip eklenmeyeceğini belirtir.

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ana kare bazı belirtilen uzaklıkta görsel taslağa dönüştürme eklenecekse TRUE. Ana kare bazı geçişten sonra görsel taslağa dönüştürme eklenecekse FALSE.

### <a name="remarks"></a>Açıklamalar

Ana kare uzaklığında görsel taslağa dönüştürme eklenip eklenmeyeceğini belirtir. Türetilen bir sınıfta, offset veya geçiş belirtilmelidir.

##  <a name="m_badded"></a>  CBaseKeyFrame::m_bAdded

Bu ana kare bir film şeridini eklenip eklenmediğini belirtir.

```
BOOL m_bAdded;
```

##  <a name="m_biskeyframeatoffset"></a>  CBaseKeyFrame::m_bIsKeyframeAtOffset

Bu ana kare var olan başka bir ana kare bir uzaklığı veya bazı geçiş sonunda görsel taslağa dönüştürme eklenip eklenmeyeceğini belirtir.

```
BOOL m_bIsKeyframeAtOffset;
```

##  <a name="m_keyframe"></a>  CBaseKeyFrame::m_keyframe

Bir Windows animasyon API'sı ana karesini temsil eder. Bir anahtar kare başlatılmadan UI_ANIMATION_KEYFRAME_STORYBOARD_START önceden tanımlanmış değerine ayarlanır.

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
