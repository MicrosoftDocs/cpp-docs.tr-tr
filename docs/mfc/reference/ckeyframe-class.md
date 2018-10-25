---
title: CKeyFrame sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 70301284e306a2d207876eead82ad787684809ce
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055534"
---
# <a name="ckeyframe-class"></a>CKeyFrame sınıfı

Bir animasyon ana karesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CKeyFrame : public CBaseKeyFrame;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CKeyFrame::CKeyFrame](#ckeyframe)|Fazla Yüklendi. Diğer ana kare üzerinde bağlı bir anahtar kare oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Bir anahtar kare bir film şeridini ekler. (Geçersiz kılmaları [CBaseKeyFrame::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Geçişten sonra görsel taslak için bir anahtar kare ekler.|
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Bir anahtar kare uzaklığında görsel taslağa dönüştürme ekler.|
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Bu ana kare bağımlı bir ana kare bir işaretçi döndürür.|
|[CKeyFrame::GetOffset](#getoffset)|Diğer bir kareden bir uzaklık döndürür.|
|[CKeyFrame::GetTransition](#gettransition)|Bu ana kare bağımlı bir geçiş için bir işaretçi döndürür.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CKeyFrame::m_offset](#m_offset)|Bu ana kare m_pExistingKeyFrame içinde depolanan bir kareden uzaklığı belirtir.|
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Mevcut bir keframe bir işaretçi depolar. Bu ana kare m_offset mevcut ana kareye sahip görsel taslağa dönüştürme eklenir.|
|[CKeyFrame::m_pTransition](#m_ptransition)|Bu ana kare başlayan transtion bir işaretçi depolar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir animasyon ana karesini uygular. Bir anahtar kare biraz zaman içinde bir film şeridi temsil eder ve başlangıç ve bitiş zamanları geçişlerinin belirtmek için kullanılabilir. Bir ana kare üzerinde başka bir ana kare tabanlı uzaklık (saniye cinsinden), sahip veya bir geçiş üzerinde temel olabilir ve bu geçiş sona erdiğinde zaman içinde bir ana temsil eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)

[CKeyFrame](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="addtostoryboard"></a>  CKeyFrame::AddToStoryboard

Bir anahtar kare bir film şeridini ekler.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslak için bir işaretçi.

*bDeepAdd*<br/>
Anahtar Kare Ekle veya yinelemeli olarak geçiş belirtir.

### <a name="return-value"></a>Dönüş Değeri

TRUE, ana kare başarıyla eklendi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, film şeridi için bir anahtar kare ekler. Diğer ana kare veya geçiş bağlıdır ve bDeepAdd TRUE ise, bu yöntem, bunları yinelemeli olarak eklemeyi dener.

##  <a name="addtostoryboardaftertransition"></a>  CKeyFrame::AddToStoryboardAfterTransition

Geçişten sonra görsel taslak için bir anahtar kare ekler.

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslak için bir işaretçi.

*bDeepAdd*<br/>
Bir geçiş yinelemeli olarak eklenip eklenmeyeceğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

TRUE, ana kare başarıyla eklendi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, geçişten sonra görsel taslak için bir anahtar kare eklemek için framework tarafından çağırılır.

##  <a name="addtostoryboardatoffset"></a>  CKeyFrame::AddToStoryboardAtOffset

Bir anahtar kare uzaklığında görsel taslağa dönüştürme ekler.

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Parametreler

*pStoryboard*<br/>
Görsel taslak için bir işaretçi.

*bDeepAdd*<br/>
Bir ana kare eklemek için bu ana kare üzerinde yinelemeli olarak bağımlı olup olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

TRUE, ana kare başarıyla eklendi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir ana kare uzaklığında görsel taslağa dönüştürme eklemek için framework tarafından çağırılır.

##  <a name="ckeyframe"></a>  CKeyFrame::CKeyFrame

Bir geçiş üzerinde bağlı bir anahtar kare oluşturur.

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>Parametreler

*pTransition*<br/>
Geçiş için bir işaretçi.

*pKeyframe*<br/>
Ana kare işaretçi.

*uzaklık*<br/>
Saniye cinsinden bir kareden pKeyframe tarafından belirtilen uzaklık.

### <a name="remarks"></a>Açıklamalar

Belirtilen geçiş sona erdiğinde oluşturulmuş ana kare biraz zaman içinde bir film şeridi temsil eder.

##  <a name="getexistingkeyframe"></a>  CKeyFrame::GetExistingKeyframe

Bu ana kare bağımlı bir ana kare bir işaretçi döndürür.

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi ana kare ya da bu ana kare üzerinde başka bir ana kare bağlı değilse NULL.

### <a name="remarks"></a>Açıklamalar

Bu ana kare bağımlı bir ana kare için erişimci budur.

##  <a name="getoffset"></a>  CKeyFrame::GetOffset

Diğer bir kareden bir uzaklık döndürür.

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>Dönüş Değeri

Diğer ana kare saniyeler içinde bir uzaklık.

### <a name="remarks"></a>Açıklamalar

Diğer ana kare saniyeler içinde bir uzaklık belirlemek için bu yöntem çağrılmalıdır.

##  <a name="gettransition"></a>  CKeyFrame::GetTransition

Bu ana kare bağımlı bir geçiş için bir işaretçi döndürür.

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi için geçiş ya da bu ana kare geçişi bağlı değilse NULL.

### <a name="remarks"></a>Açıklamalar

Bu ana kare bağımlı geçiş erişimci budur.

##  <a name="m_offset"></a>  CKeyFrame::m_offset

Bu ana kare m_pExistingKeyFrame içinde depolanan bir kareden uzaklığı belirtir.

```
UI_ANIMATION_SECONDS m_offset;
```

##  <a name="m_pexistingkeyframe"></a>  CKeyFrame::m_pExistingKeyFrame

Mevcut bir keframe bir işaretçi depolar. Bu ana kare m_offset mevcut ana kareye sahip görsel taslağa dönüştürme eklenir.

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

##  <a name="m_ptransition"></a>  CKeyFrame::m_pTransition

Bu ana kare başlayan transtion bir işaretçi depolar.

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
