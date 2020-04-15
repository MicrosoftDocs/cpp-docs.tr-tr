---
title: CAnimationPoint Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
helpviewer_keywords:
- CAnimationPoint [MFC], CAnimationPoint
- CAnimationPoint [MFC], AddTransition
- CAnimationPoint [MFC], GetDefaultValue
- CAnimationPoint [MFC], GetValue
- CAnimationPoint [MFC], GetX
- CAnimationPoint [MFC], GetY
- CAnimationPoint [MFC], SetDefaultValue
- CAnimationPoint [MFC], GetAnimationVariableList
- CAnimationPoint [MFC], m_xValue
- CAnimationPoint [MFC], m_yValue
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
ms.openlocfilehash: 19f02010b6b73573a4800152e40c592fd1736ad5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369727"
---
# <a name="canimationpoint-class"></a>CAnimationPoint Sınıfı

Koordinatları animasyonlu olabilecek bir noktanın işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationPoint : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|Fazla Yüklendi. CAnimationPoint nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationPoint::AddTransition](#addtransition)|X ve Y koordinatları için geçişler ekler.|
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|X ve Y koordinatları için varsayılan değerleri döndürür.|
|[CAnimationPoint::GetValue](#getvalue)|Geçerli değeri verir.|
|[CAnimationPoint::GetX](#getx)|X koordinatı için CAnimationVariable'e erişim sağlar.|
|[CAnimationPoint::Gety](#gety)|Y koordinatı için CAnimationVariable'e erişim sağlar.|
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenlerini bir listeye koyar. [(CAnimationBaseObject geçersiz kılar::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationPoint::operatör CPoint](#operator_cpoint)|CAnimationPoint'i CPoint'e dönüştürür.|
|[CAnimationPoint::operator=](#operator_eq)|CAnimationPoint'e ptSrc atar.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationPoint::m_xValue](#m_xvalue)|Animasyon noktasının X koordinatını temsil eden kapsüllü animasyon değişkeni.|
|[CAnimationPoint::m_yValue](#m_yvalue)|Animasyon noktasının Y koordinatını temsil eden kapsüllü animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationPoint sınıfı iki CAnimationVariable nesnesini kapsüller ve uygulamalarda bir noktayı temsil edebilir. Örneğin, ekrandaki herhangi bir nesnenin konumunu (metin dizesi, daire, nokta vb. gibi) canlandırmak için bu sınıfı kullanabilirsiniz. Uygulamada bu sınıfı kullanmak için, bu sınıfın bir nesnesini anlık olarak eklemeniz, CAnimationController'ı kullanarak animasyon denetleyicisine ekleyin::AddAnimationObject ve X ve/veya Y koordinatlarına uygulanacak her geçiş için AddTransition'ı arayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationPoint`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationpointaddtransition"></a><a name="addtransition"></a>CAnimationPoint::AddTransition

X ve Y koordinatları için geçişler ekler.

```
void AddTransition(
    CBaseTransition* pXTransition,
    CBaseTransition* pYTransition);
```

### <a name="parameters"></a>Parametreler

*pXTransition*<br/>
X koordinatları için geçiş için bir işaretçi.

*pYTransition*<br/>
Y koordinatı için geçiş için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

X ve Y koordinatları için animasyon değişkenlerine uygulanacak iç geçişler listesine belirtilen geçişleri eklemek için bu işlevi arayın. Geçişler eklediğinizde, bunlar hemen uygulanmaz ve dahili bir listede depolanır. Geçişler CAnimationController::AnimateGroup'u aradiğinizde uygulanır (belirli bir değer için bir film şeridine eklenir). Koordinatlardan birine geçiş uygulamanız gerekmiyorsa, NULL'u geçebilirsiniz.

## <a name="canimationpointcanimationpoint"></a><a name="canimationpoint"></a>CAnimationPoint::CAnimationPoint

CAnimationPoint nesnesi oluşturuyor.

```
CAnimationPoint();

CAnimationPoint(
    const CPoint& ptDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*ptDefault*<br/>
Varsayılan nokta koordinatlarını belirtir.

*nGroupID*<br/>
Grup Kimliğini belirtir.

*nObjectID*<br/>
Nesne Kimliğini belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı verileri belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan özelliklere sahip CAnimationPoint nesnesi yapıları: varsayılan nokta koordinatları, Grup Kimliği ve Object ID 0 olarak ayarlanır.

## <a name="canimationpointgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationPoint::GetAnimationVariableList

Kapsüllenmiş animasyon değişkenlerini bir listeye koyar.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*Lst*<br/>
İşlev döndüğünde, X ve Y koordinatlarını temsil eden iki CAnimationVariable nesnesine işaretçiler içerir.

## <a name="canimationpointgetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationPoint::GetDefaultValue

X ve Y koordinatları için varsayılan değerleri döndürür.

```
CPoint GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan değer içeren bir nokta.

### <a name="remarks"></a>Açıklamalar

Daha önce oluşturucu veya SetDefaultValue tarafından ayarlanmış varsayılan değeri almak için bu işlevi arayın.

## <a name="canimationpointgetvalue"></a><a name="getvalue"></a>CAnimationPoint::GetValue

Geçerli değeri verir.

```
BOOL GetValue(CPoint& ptValue);
```

### <a name="parameters"></a>Parametreler

*ptValue*<br/>
Çıkış. Bu yöntem döndüğünde geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU, geçerli değer başarıyla alındıysa; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Animasyon noktasının geçerli değerini almak için bu işlevi çağırın. Bu yöntem başarısız olursa veya X ve Y koordinatları için com nesneleri temel e-baş harflerine sahip değilse, ptValue daha önce oluşturucu veya SetDefaultValue tarafından ayarlanmış varsayılan değer içerir.

## <a name="canimationpointgetx"></a><a name="getx"></a>CAnimationPoint::GetX

X koordinatı için CAnimationVariable'e erişim sağlar.

```
CAnimationVariable& GetX();
```

### <a name="return-value"></a>Dönüş Değeri

X koordinatı temsil eden kapsüllü CAnimationVariable için bir başvuru.

### <a name="remarks"></a>Açıklamalar

X koordinatLarını temsil eden temel CAnimationVariable'e doğrudan erişim elde etmek için bu yöntemi arayabilirsiniz.

## <a name="canimationpointgety"></a><a name="gety"></a>CAnimationPoint::Gety

Y koordinatı için CAnimationVariable'e erişim sağlar.

```
CAnimationVariable& GetY();
```

### <a name="return-value"></a>Dönüş Değeri

Y koordinatLarını temsil eden kapsüllü CAnimationVariable'e bir başvuru.

### <a name="remarks"></a>Açıklamalar

Y koordinatLarını temsil eden altta yatan CAnimationVariable'e doğrudan erişim elde etmek için bu yöntemi arayabilirsiniz.

## <a name="canimationpointm_xvalue"></a><a name="m_xvalue"></a>CAnimationPoint::m_xValue

Animasyon noktasının X koordinatını temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_xValue;
```

## <a name="canimationpointm_yvalue"></a><a name="m_yvalue"></a>CAnimationPoint::m_yValue

Animasyon noktasının Y koordinatını temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_yValue;
```

## <a name="canimationpointoperator-cpoint"></a><a name="operator_cpoint"></a>CAnimationPoint::operatör CPoint

CAnimationPoint'i CPoint'e dönüştürür.

```
operator CPoint();
```

### <a name="return-value"></a>Dönüş Değeri

CAnimationPoint'in CPoint olarak geçerli değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev dahili olarak GetValue çağırır. GetValue herhangi bir nedenle başarısız olursa, döndürülen nokta X ve Y koordinatları için varsayılan değerleri içerir.

## <a name="canimationpointoperator"></a><a name="operator_eq"></a>CAnimationPoint::operator=

CAnimationPoint'e ptSrc atar.

```
void operator=(const CPoint& ptSrc);
```

### <a name="parameters"></a>Parametreler

*ptSrc*<br/>
CPoint veya POINT'e başvurur.

### <a name="remarks"></a>Açıklamalar

CAnimationPoint'e ptSrc atar. Animasyon başlamadan önce bunu yapmanız önerilir, çünkü bu işleç, x ve y koordinatları için temel COM nesnelerini yeniden oluşturan SetDefaultValue'ı çağırır. Bu animasyon nesnesini olaylara abone olduysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="canimationpointsetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationPoint::SetDefaultValue

Varsayılan değeri ayarlar.

```
void SetDefaultValue(const POINT& ptDefault);
```

### <a name="parameters"></a>Parametreler

*ptDefault*<br/>
Varsayılan nokta değerini belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine varsayılan değer ayarlamak için bu işlevi kullanın. Bu yöntem, varsayılan değerleri animasyon noktasının X ve Y koordinatlarına atar. Ayrıca, oluşturuldukları takdirde altta yatan COM nesnelerini yeniden oluşturur. Bu animasyon nesnesini olaylara abone olduysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
