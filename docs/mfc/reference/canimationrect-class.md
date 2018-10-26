---
title: CAnimationRect sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec22bfd2805f4af432821c4aaeb350a2cf635cfa
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083431"
---
# <a name="canimationrect-class"></a>CAnimationRect sınıfı

Kenarlarının animasyonu oluşturulabilen bir dikdörtgen işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationRect : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationRect::CAnimationRect](#canimationrect)|Fazla Yüklendi. Bir animasyon rect nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationRect::AddTransition](#addtransition)|Sol, üst, sağ ve alt koordinatları geçişlerini ekler.|
|[CAnimationRect::GetBottom](#getbottom)|Alt koordinatı temsil eden CAnimationVariable için erişim sağlar.|
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|Dikdörtgenin sınırları için varsayılan değerleri döndürür.|
|[CAnimationRect::GetLeft](#getleft)|Sol koordinatını temsil eden CAnimationVariable için erişim sağlar.|
|[CAnimationRect::GetRight](#getright)|Erişim için doğru koordinatı temsil eden CAnimationVariable sağlar.|
|[CAnimationRect::GetTop](#gettop)|Üst koordinatını temsil eden CAnimationVariable için erişim sağlar.|
|[CAnimationRect::GetValue](#getvalue)|Geçerli bir değer döndürür.|
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|Varsayılan değerini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenleri bir listesine koyar. (Geçersiz kılmaları [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[RECT CAnimationRect::operator](#operator_rect)|Bir CAnimationRect RECT. için dönüştürür.|
|[CAnimationRect::operator =](#operator_eq)|Rect CAnimationRect için atar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|Dikdörtgen boyutu sabit olup olmadığını belirtir.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|Alt temsil eden kapsüllenmiş animasyon değişkeni animasyon dikdörtgen bağlı.|
|[CAnimationRect::m_leftValue](#m_leftvalue)|Animasyon dikdörtgenin sol temsil eden kapsüllenmiş animasyon değişkeni bağlı.|
|[CAnimationRect::m_rightValue](#m_rightvalue)|Sağ temsil eden kapsüllenmiş animasyon değişkeni animasyon dikdörtgen bağlı.|
|[CAnimationRect::m_szInitial](#m_szinitial)|Animasyon dikdörtgen başlangıç boyutunu belirtir.|
|[CAnimationRect::m_topValue](#m_topvalue)|Animasyon dikdörtgenin üst temsil eden kapsüllenmiş animasyon değişkeni bağlı.|

## <a name="remarks"></a>Açıklamalar

CAnimationRect sınıfı dört CAnimationVariable nesneleri kapsüller ve uygulamalarda bir dikdörtgen temsil edebilir. Bu sınıf kullanmak için yalnızca bu sınıfın bir nesnesi, CAnimationController::AddAnimationObject kullanarak animasyon denetleyicisine eklemek ve sol, sağ üst ve alt koordinatlarına uygulanacak AddTransition her geçiş için çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationRect::AddTransition

Sol, üst, sağ ve alt koordinatları geçişlerini ekler.

```
void AddTransition(
    CBaseTransition* pLeftTransition,
    CBaseTransition* pTopTransition,
    CBaseTransition* pRightTransition,
    CBaseTransition* pBottomTransition);
```

### <a name="parameters"></a>Parametreler

*pLeftTransition*<br/>
Geçiş için sol tarafındaki belirtir.

*pTopTransition*<br/>
Geçiş için en iyi tarafı belirtir.

*pRightTransition*<br/>
Geçiş için sağ tarafındaki belirtir.

*pBottomTransition*<br/>
Geçiş için alt kenar belirtir.

### <a name="remarks"></a>Açıklamalar

Her bir dikdörtgen kenarı animasyon değişkenleri uygulanacak geçişleri iç listesinde belirtilen geçişleri eklemek için bu işlevi çağırın. Geçişleri eklediğinizde, bunlar değil hemen uygulanır ve bir iç listesinde depolanır. Geçiş (belirli bir değeri için bir görsel taslağı eklenebilir) uygulandığını CAnimationController::AnimateGroup çağırdığınızda. Dikdörtgene kenarları birine geçiş uygulanacak gerekmiyorsa NULL geçirebilirsiniz.

##  <a name="canimationrect"></a>  CAnimationRect::CAnimationRect

CAnimationRect bir nesne oluşturur.

```
CAnimationRect();

CAnimationRect(
    const CRect& rect,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    const CPoint& pt,
    const CSize& sz,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    int nLeft,
    int nTop,
    int nRight,
    int nBottom,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Varsayılan dikdörtgen belirtir.

*nGroupID*<br/>
Grup kimliğini belirtir.

*nObjectID*<br/>
Nesne kimliğini belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı veri belirtir.

*PT*<br/>
Sol üst köşedeki koordinatı.

*SZ*<br/>
Dikdörtgen boyutu.

*nLeft*<br/>
Sınır sol koordinatını belirtir.

*nTop*<br/>
Bağlı üst koordinatını belirtir.

*nRight*<br/>
Doğru bağlı koordinatını belirtir.

*nBottom*<br/>
Bağlı alt koordinatını belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne, nesne kimliği ve 0 olarak ayarlanacak grubu kimliği için sol, üst, sağ ve alt, varsayılan değerleri ile oluşturulur. Çalışma zamanında SetDefaultValue ve SetID kullanarak daha sonra değiştirilebilir.

##  <a name="getanimationvariablelist"></a>  CAnimationRect::GetAnimationVariableList

Kapsüllenmiş animasyon değişkenleri bir listesine koyar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*lst*<br/>
İşlevi döndüğünde, dikdörtgen koordinatlarını temsil eden dört CAnimationVariable nesnelerine işaretçiler içerir.

##  <a name="getbottom"></a>  CAnimationRect::GetBottom

Alt koordinatı temsil eden CAnimationVariable için erişim sağlar.

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş CAnimationVariable alt koordinatı temsil eden bir başvuru.

### <a name="remarks"></a>Açıklamalar

Temel alınan CAnimationVariable alt koordinatını temsil eden doğrudan erişim elde etmek için bu yöntem çağırabilirsiniz.

##  <a name="getdefaultvalue"></a>  CAnimationRect::GetDefaultValue

Dikdörtgenin sınırları için varsayılan değerleri döndürür.

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

Sol, sağ, üst ve alt için varsayılan değerleri içeren bir CRect değeri.

### <a name="remarks"></a>Açıklamalar

Oluşturucu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değerini almak için bu işlevi çağırın.

##  <a name="getleft"></a>  CAnimationRect::GetLeft

Sol koordinatını temsil eden CAnimationVariable için erişim sağlar.

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş CAnimationVariable sol koordinatını temsil eden bir başvuru.

### <a name="remarks"></a>Açıklamalar

Temel alınan CAnimationVariable sol koordinatını temsil eden doğrudan erişim elde etmek için bu yöntem çağırabilirsiniz.

##  <a name="getright"></a>  CAnimationRect::GetRight

Erişim için doğru koordinatı temsil eden CAnimationVariable sağlar.

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş CAnimationVariable doğru koordinatı temsil eden bir başvuru.

### <a name="remarks"></a>Açıklamalar

Temel alınan CAnimationVariable doğru koordinatını temsil eden doğrudan erişim elde etmek için bu yöntem çağırabilirsiniz.

##  <a name="gettop"></a>  CAnimationRect::GetTop

Üst koordinatını temsil eden CAnimationVariable için erişim sağlar.

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş CAnimationVariable üst koordinatını temsil eden bir başvuru.

### <a name="remarks"></a>Açıklamalar

Temel alınan CAnimationVariable üst koordinatını temsil eden doğrudan erişim elde etmek için bu yöntem çağırabilirsiniz.

##  <a name="getvalue"></a>  CAnimationRect::GetValue

Geçerli bir değer döndürür.

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Çıktı. Bu yöntem döndürüldüğünde, geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer başarıyla alındığında TRUE, Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Animasyon dikdörtgen geçerli değerini almak için bu işlevi çağırın. Sol için bu yöntem başarısız olursa veya temel alınan COM nesneleri, üst, sağ ve alt başlatılmamış, rect Oluşturucusu veya SetDefaultValue önceden ayarlanmış varsayılan değerini içeriyor.

##  <a name="m_bfixedsize"></a>  CAnimationRect::m_bFixedSize

Dikdörtgen boyutu sabit olup olmadığını belirtir.

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>Açıklamalar

Bu üye true ise, dikdörtgen boyutunun sabit ve sağ ve alt değerlere göre sabit boyutu üst sol löşede taşınır her zaman yeniden hesaplanır. Bu değeri kolayca dikdörtgeni ekranın etrafında taşımak için TRUE olarak ayarlayın. Bu durumda sağ ve alt koordinatlarına uygulanan geçişleri göz ardı edilir. Boyut, nesneyi oluşturmak ve/veya SetDefaultValue çağrı dahili olarak depolanır. Bu üye, varsayılan olarak FALSE olarak ayarlanır.

##  <a name="m_bottomvalue"></a>  CAnimationRect::m_bottomValue

Alt temsil eden kapsüllenmiş animasyon değişkeni animasyon dikdörtgen bağlı.

```
CAnimationVariable m_bottomValue;
```

##  <a name="m_leftvalue"></a>  CAnimationRect::m_leftValue

Animasyon dikdörtgenin sol temsil eden kapsüllenmiş animasyon değişkeni bağlı.

```
CAnimationVariable m_leftValue;
```

##  <a name="m_rightvalue"></a>  CAnimationRect::m_rightValue

Sağ temsil eden kapsüllenmiş animasyon değişkeni animasyon dikdörtgen bağlı.

```
CAnimationVariable m_rightValue;
```

##  <a name="m_szinitial"></a>  CAnimationRect::m_szInitial

Animasyon dikdörtgen başlangıç boyutunu belirtir.

```
CSize m_szInitial;
```

##  <a name="m_topvalue"></a>  CAnimationRect::m_topValue

Animasyon dikdörtgenin üst temsil eden kapsüllenmiş animasyon değişkeni bağlı.

```
CAnimationVariable m_topValue;
```

##  <a name="operator_rect"></a>  RECT CAnimationRect::operator

Bir CAnimationRect RECT. için dönüştürür.

```
operator RECT();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer olarak RECT. animasyon dikdörtgenin

### <a name="remarks"></a>Açıklamalar

Bu işlev, GetValue dahili olarak çağırır. GetValue herhangi bir nedenle başarısız olursa, döndürülen RECT tüm dikdörtgen koordinatları için varsayılan değerleri içerir.

##  <a name="operator_eq"></a>  CAnimationRect::operator =

Rect CAnimationRect için atar.

```
void operator=(const RECT& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Animasyon dikdörtgen yeni değeri.

### <a name="remarks"></a>Açıklamalar

Bu işleç oluşturulduktan gerekiyorsa, renk bileşenleri için temel alınan COM nesneleri yeniden oluşturur ve SetDefaultValue çağırdığı animasyon başlamadan önce bunu yapmak için önerilir. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesnesine abone, bu olayları yeniden etkinleştirmeniz gerekir.

##  <a name="setdefaultvalue"></a>  CAnimationRect::SetDefaultValue

Varsayılan değerini ayarlar.

```
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Sol, üst, sağ ve alt yeni varsayılan değerleri belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine bir varsayılan değer ayarlamak için bu işlevi kullanın. Bu yöntemleri dikdörtgenin sınırları için varsayılan değerleri atar. Ayrıca bunlar oluşturulmuşsa temel COM nesneleri yeniden oluşturur. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesnesine abone, bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
