---
title: CKeyFrame Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
helpviewer_keywords:
- CKeyFrame [MFC], CKeyFrame
- CKeyFrame [MFC], AddToStoryboard
- CKeyFrame [MFC], AddToStoryboardAfterTransition
- CKeyFrame [MFC], AddToStoryboardAtOffset
- CKeyFrame [MFC], GetExistingKeyframe
- CKeyFrame [MFC], GetOffset
- CKeyFrame [MFC], GetTransition
- CKeyFrame [MFC], m_offset
- CKeyFrame [MFC], m_pExistingKeyFrame
- CKeyFrame [MFC], m_pTransition
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
ms.openlocfilehash: f535503338a82c7cc70455ae6a08cdab0f13c624
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372286"
---
# <a name="ckeyframe-class"></a>CKeyFrame Sınıfı

Animasyon anahtar çerçeveyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CKeyFrame : public CBaseKeyFrame;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CKeyFrame::CKeyFrame](#ckeyframe)|Fazla Yüklendi. Diğer anahtar çerçeveye bağlı bir anahtar çerçevesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Film şeridine anahtar kare ekler. [(CBaseKeyFrame geçersiz kılar::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Geçişten sonra film şeridine bir anahtar kare ekler.|
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Ofset'te film şeridine bir anahtar çerçevesi ekler.|
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Bu anahtar çerçevesibağlı bir anahtar çerçevesi için bir işaretçi döndürür.|
|[CKeyFrame::GetOffset](#getoffset)|Diğer anahtar dilimden bir ofset döndürür.|
|[CKeyFrame::GetTransition](#gettransition)|Bu anahtar çerçevesibağlı bir geçiş için bir işaretçi döndürür.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CKeyFrame::m_offset](#m_offset)|Bu anahtar çerçevesinin m_pExistingKeyFrame depolanan bir anahtar çerçevesinden mahsup olduğunu belirtir.|
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Bir işaretçiyi varolan bir keframe'e doğru depolar. Bu anahtar çerçevesi, varolan anahtar çerçevesine m_offset ile film şeridine eklenir.|
|[CKeyFrame::m_pTransition](#m_ptransition)|Bu anahtar çerçevede başlayan bir transtion işaretçisi depolar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf bir animasyon anahtar çerçevesi uygular. Anahtar çerçevesi, bir film şeridi içindeki bir anı temsil eder ve geçişlerin başlangıç ve bitiş saatlerini belirtmek için kullanılabilir. Anahtar çerçeve, diğer anahtar çerçeveyi temel alabilir ve ondan bir ofset (saniye cinsinden) olabilir veya bir geçişe dayalı olabilir ve bu geçişin sona erdiğinde bir anı temsil edebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)

[CKeyFrame](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="ckeyframeaddtostoryboard"></a><a name="addtostoryboard"></a>CKeyFrame::AddToStoryboard

Film şeridine anahtar kare ekler.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Bir film şeridi için bir işaretçi.

*bDeepAdd*<br/>
Anahtar çerçevesi veya geçiş özyinelemeli olarak eklenip eklenmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU, anahtar çerçevesi başarıyla eklendiyse.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, film şeridine bir anahtar kare ekler. Diğer anahtar çerçevesi veya geçiş bağlıdır ve bDeepAdd TRUE ise, bu yöntem bunları özyinelemeli eklemeye çalışır.

## <a name="ckeyframeaddtostoryboardaftertransition"></a><a name="addtostoryboardaftertransition"></a>CKeyFrame::AddToStoryboardAfterTransition

Geçişten sonra film şeridine bir anahtar kare ekler.

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Bir film şeridi için bir işaretçi.

*bDeepAdd*<br/>
Bir geçiş özyinelemeli olarak eklenip eklenmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU, anahtar çerçevesi başarıyla eklendiyse.

### <a name="remarks"></a>Açıklamalar

Bu işlev, geçişten sonra film şeridine bir anahtar çerçevesi eklemek için çerçeve tarafından çağrılır.

## <a name="ckeyframeaddtostoryboardatoffset"></a><a name="addtostoryboardatoffset"></a>CKeyFrame::AddToStoryboardAtOffset

Ofset'te film şeridine bir anahtar çerçevesi ekler.

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Bir film şeridi için bir işaretçi.

*bDeepAdd*<br/>
Bu anahtar çerçevesinin özyinelemeli olarak bağlı olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU, anahtar çerçevesi başarıyla eklendiyse.

### <a name="remarks"></a>Açıklamalar

Bu işlev, ofset de film şeridine bir anahtar çerçevesi eklemek için çerçeve tarafından çağrılır.

## <a name="ckeyframeckeyframe"></a><a name="ckeyframe"></a>CKeyFrame::CKeyFrame

Geçişe bağlı bir anahtar çerçeve oluşturuyor.

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>Parametreler

*pGeçiş*<br/>
Geçiş için bir işaretçi.

*pKeyframe*<br/>
Anahtar kare için bir işaretçi.

*Uzaklık*<br/>
PKeyframe tarafından belirtilen anahtar çerçevesinden saniyeler içinde ofset.

### <a name="remarks"></a>Açıklamalar

Yapılandırılan anahtar çerçeve, belirtilen geçiş sona erdiğinde bir film şeridi içinde zaman içinde bir anı temsil edecektir.

## <a name="ckeyframegetexistingkeyframe"></a><a name="getexistingkeyframe"></a>CKeyFrame::GetExistingKeyframe

Bu anahtar çerçevesibağlı bir anahtar çerçevesi için bir işaretçi döndürür.

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>Dönüş Değeri

Anahtar çerçevesi için geçerli bir işaretçi veya bu anahtar çerçevesi diğer anahtar çerçevesine bağlı değilse NULL.

### <a name="remarks"></a>Açıklamalar

Bu, bu anahtar çerçevesinin bağlı olduğu bir anahtar çerçevesinin erişimidir.

## <a name="ckeyframegetoffset"></a><a name="getoffset"></a>CKeyFrame::GetOffset

Diğer anahtar dilimden bir ofset döndürür.

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>Dönüş Değeri

Diğer anahtar dilimden saniyeler içinde bir ofset.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, diğer anahtar çerçeveden saniyeler içinde bir ofset belirlemek için çağrılmalıdır.

## <a name="ckeyframegettransition"></a><a name="gettransition"></a>CKeyFrame::GetTransition

Bu anahtar çerçevesibağlı bir geçiş için bir işaretçi döndürür.

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>Dönüş Değeri

Geçiş için geçerli bir işaretçi veya bu anahtar çerçevesi geçişe bağlı değilse NULL.

### <a name="remarks"></a>Açıklamalar

Bu, anahtar çerçevesinin bağlı olduğu bir geçişin erişimidir.

## <a name="ckeyframem_offset"></a><a name="m_offset"></a>CKeyFrame::m_offset

Bu anahtar çerçevesinin m_pExistingKeyFrame depolanan bir anahtar çerçevesinden mahsup olduğunu belirtir.

```
UI_ANIMATION_SECONDS m_offset;
```

## <a name="ckeyframem_pexistingkeyframe"></a><a name="m_pexistingkeyframe"></a>CKeyFrame::m_pExistingKeyFrame

Bir işaretçiyi varolan bir keframe'e doğru depolar. Bu anahtar çerçevesi, varolan anahtar çerçevesine m_offset ile film şeridine eklenir.

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

## <a name="ckeyframem_ptransition"></a><a name="m_ptransition"></a>CKeyFrame::m_pTransition

Bu anahtar çerçevede başlayan bir transtion işaretçisi depolar.

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
