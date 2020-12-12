---
description: 'Daha fazla bilgi edinin: CKeyFrame sınıfı'
title: CKeyFrame sınıfı
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
ms.openlocfilehash: ec6aa45484965afbf0c636a1eed26a3d4a63e426
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236886"
---
# <a name="ckeyframe-class"></a>CKeyFrame sınıfı

Bir animasyon ana karesini temsil eder.

## <a name="syntax"></a>Syntax

```
class CKeyFrame : public CBaseKeyFrame;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CKeyFrame:: CKeyFrame](#ckeyframe)|Fazla Yüklendi. Diğer ana kareye bağlı bir ana kare oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CKeyFrame:: AddToStoryboard](#addtostoryboard)|Görsel taslağa bir ana kare ekler. ( [CBaseKeyFrame:: AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard)geçersiz kılar.)|
|[CKeyFrame:: Addtoöyküboardadftertransition](#addtostoryboardaftertransition)|Geçişten sonra film şeridine bir ana kare ekler.|
|[CKeyFrame:: Addtoöyküboardadtoffset](#addtostoryboardatoffset)|Kaydırmadır film şeridine bir ana kare ekler.|
|[CKeyFrame:: GetExistingKeyframe](#getexistingkeyframe)|Bu ana karenin bağlı olduğu bir ana kareye yönelik bir işaretçi döndürür.|
|[CKeyFrame:: GetOffset](#getoffset)|Diğer ana kareden bir konum döndürür.|
|[CKeyFrame:: GetTransition](#gettransition)|Bu ana karenin bağlı olduğu geçişe yönelik bir işaretçi döndürür.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CKeyFrame:: m_offset](#m_offset)|Bu ana karenin m_pExistingKeyFrame depolanan bir ana kareden sapmasını belirtir.|
|[CKeyFrame:: m_pExistingKeyFrame](#m_pexistingkeyframe)|Varolan bir keframe için bir işaretçi depolar. Bu ana kare, mevcut ana kareye m_offset olan görsel taslağa eklenir.|
|[CKeyFrame:: m_pTransition](#m_ptransition)|Bu ana karede başlayan bir işaretçiye yönelik bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf bir animasyon ana karesini uygular. Bir ana kare, bir film şeridi içinde zaman içindeki bir süreyi temsil eder ve geçişlerin başlangıç ve bitiş zamanlarını belirtmek için kullanılabilir. Bir ana kare diğer ana kareyi temel alabilir ve bundan bir uzaklığa (saniye cinsinden) sahip olabilir veya bir geçişe bağlı olabilir ve bu geçişin sona erdiği sırada bir süre temsil edebilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)

[CKeyFrame](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="ckeyframeaddtostoryboard"></a><a name="addtostoryboard"></a> CKeyFrame:: AddToStoryboard

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
Anahtar kare veya geçişin yinelemeli olarak eklenip eklenmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Ana kare başarıyla eklendiyse TRUE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, görsel taslağa bir ana kare ekler. Diğer bir ana kareye veya geçişe bağımlıysa ve Bderin ekleme doğru ise, bu yöntem bunları yinelemeli olarak eklemeye çalışır.

## <a name="ckeyframeaddtostoryboardaftertransition"></a><a name="addtostoryboardaftertransition"></a> CKeyFrame:: Addtoöyküboardadftertransition

Geçişten sonra film şeridine bir ana kare ekler.

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslağa yönelik işaretçi.

*Boderin ekleme*<br/>
Yinelemeli olarak bir geçiş eklenip eklenmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Ana kare başarıyla eklendiyse TRUE.

### <a name="remarks"></a>Açıklamalar

Bu işlev, geçiş sonrasında görsel taslağa bir ana kare eklemek için çerçevesi tarafından çağırılır.

## <a name="ckeyframeaddtostoryboardatoffset"></a><a name="addtostoryboardatoffset"></a> CKeyFrame:: Addtoöyküboardadtoffset

Kaydırmadır film şeridine bir ana kare ekler.

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslağa yönelik işaretçi.

*Boderin ekleme*<br/>
Bu ana karenin yinelemeli olarak bağımlı olduğu bir anahtar kare eklenip eklenmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Ana kare başarıyla eklendiyse TRUE.

### <a name="remarks"></a>Açıklamalar

Bu işlev, çerçeve tarafından, kaydırılarak görsel taslağa bir ana kare eklemek için çağrılır.

## <a name="ckeyframeckeyframe"></a><a name="ckeyframe"></a> CKeyFrame:: CKeyFrame

Bir geçişe bağlı bir ana kare oluşturur.

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>Parametreler

*pTransition*<br/>
Bir geçişe yönelik işaretçi.

*Pana kare*<br/>
Ana kare işaretçisi.

*konumu*<br/>
PKeyframe tarafından belirtilen ana kareden saniye cinsinden fark.

### <a name="remarks"></a>Açıklamalar

Oluşturulan ana kare, belirtilen geçiş sona erdiğinde bir film şeridinde zaman içinde bir süre temsil eder.

## <a name="ckeyframegetexistingkeyframe"></a><a name="getexistingkeyframe"></a> CKeyFrame:: GetExistingKeyframe

Bu ana karenin bağlı olduğu bir ana kareye yönelik bir işaretçi döndürür.

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>Dönüş Değeri

Ana kareye yönelik geçerli bir işaretçi veya bu ana kare diğer ana kareye bağlı değilse NULL.

### <a name="remarks"></a>Açıklamalar

Bu anahtar karesine bağlı bir ana kareye yönelik bir erişimci budur.

## <a name="ckeyframegetoffset"></a><a name="getoffset"></a> CKeyFrame:: GetOffset

Diğer ana kareden bir konum döndürür.

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>Dönüş Değeri

Diğer ana kareden saniye cinsinden bir konum.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, diğer ana kareden saniye cinsinden bir konum belirlenmesi için çağrılmalıdır.

## <a name="ckeyframegettransition"></a><a name="gettransition"></a> CKeyFrame:: GetTransition

Bu ana karenin bağlı olduğu geçişe yönelik bir işaretçi döndürür.

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>Dönüş Değeri

Bu ana kare geçişe bağlı değilse, geçişe yönelik geçerli bir işaretçi veya NULL.

### <a name="remarks"></a>Açıklamalar

Bu, bu ana karenin bağımlı olduğu bir geçişe yönelik bir erişimdir.

## <a name="ckeyframem_offset"></a><a name="m_offset"></a> CKeyFrame:: m_offset

Bu ana karenin m_pExistingKeyFrame depolanan bir ana kareden sapmasını belirtir.

```
UI_ANIMATION_SECONDS m_offset;
```

## <a name="ckeyframem_pexistingkeyframe"></a><a name="m_pexistingkeyframe"></a> CKeyFrame:: m_pExistingKeyFrame

Varolan bir keframe için bir işaretçi depolar. Bu ana kare, mevcut ana kareye m_offset olan görsel taslağa eklenir.

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

## <a name="ckeyframem_ptransition"></a><a name="m_ptransition"></a> CKeyFrame:: m_pTransition

Bu ana karede başlayan bir işaretçiye yönelik bir işaretçi depolar.

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
