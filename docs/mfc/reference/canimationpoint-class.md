---
description: 'Daha fazla bilgi edinin: CAnimationPoint sınıfı'
title: CAnimationPoint sınıfı
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
ms.openlocfilehash: ddefb93950f0ff1109478f3574413faf9f60a22a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336784"
---
# <a name="canimationpoint-class"></a>CAnimationPoint sınıfı

Koordinatları animasyonlu olabilecek bir noktanın işlevselliğini uygular.

## <a name="syntax"></a>Syntax

```
class CAnimationPoint : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationPoint:: CAnimationPoint](#canimationpoint)|Fazla Yüklendi. CAnimationPoint nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationPoint:: AddTransition](#addtransition)|X ve Y koordinatları için geçişler ekler.|
|[CAnimationPoint:: GetDefaultValue](#getdefaultvalue)|X ve Y koordinatları için varsayılan değerleri döndürür.|
|[CAnimationPoint:: GetValue](#getvalue)|Geçerli değeri döndürür.|
|[CAnimationPoint:: GetX](#getx)|X koordinatı için CAnimationVariable öğesine erişim sağlar.|
|[CAnimationPoint:: GetY](#gety)|Y koordinatı için CAnimationVariable erişimi sağlar.|
|[CAnimationPoint:: SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationPoint:: GetAnimationVariableList](#getanimationvariablelist)|Encapsulated animasyon değişkenlerini bir listeye koyar. ( [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)geçersiz kılınır.)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationPoint:: operator CPoint](#operator_cpoint)|CAnimationPoint 'i bir CPoint 'e dönüştürür.|
|[CAnimationPoint:: operator =](#operator_eq)|PtSrc 'yi CAnimationPoint 'e atar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationPoint:: m_xValue](#m_xvalue)|Animasyon noktasının X koordinatını temsil eden Encapsulated animasyon değişkeni.|
|[CAnimationPoint:: m_yValue](#m_yvalue)|Animasyon noktasının Y koordinatını temsil eden Encapsulated animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationPoint sınıfı iki CAnimationVariable nesnesini kapsüller ve uygulamalarda bir noktada temsil edebilir. Örneğin, ekrandaki herhangi bir nesnenin konumunu hareketlendirmek için (metin dizesi, daire, nokta vb. gibi) bu sınıfı kullanabilirsiniz. Bu sınıfı uygulamada kullanmak için, bu sınıfın bir nesnesinin örneğini oluşturun, CAnimationController:: AddAnimationObject öğesini kullanarak animasyon denetleyicisine ekleyin ve X ve/veya Y koordinatlarına uygulanacak her geçiş için AddTransition çağrısı yapın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationPoint`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationpointaddtransition"></a><a name="addtransition"></a> CAnimationPoint:: AddTransition

X ve Y koordinatları için geçişler ekler.

```cpp
void AddTransition(
    CBaseTransition* pXTransition,
    CBaseTransition* pYTransition);
```

### <a name="parameters"></a>Parametreler

*pXTransition*<br/>
X koordinatları için geçiş işaretçisi.

*pYTransition*<br/>
Y koordinatı için geçiş işaretçisi.

### <a name="remarks"></a>Açıklamalar

X ve Y koordinatları için animasyon değişkenlerine uygulanacak olan geçiş iç listesine belirtilen geçişleri eklemek için bu işlevi çağırın. Geçişler eklediğinizde, bunlar hemen uygulanmaz ve dahili bir listede depolanır. CAnimationController:: AnimateGroup ' i çağırdığınızda geçişler uygulanır (belirli bir değer için bir görsel taslağa eklenir). Koordinatlardan birine geçiş uygulamanız gerekmiyorsa NULL geçirebilirsiniz.

## <a name="canimationpointcanimationpoint"></a><a name="canimationpoint"></a> CAnimationPoint:: CAnimationPoint

CAnimationPoint nesnesi oluşturur.

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

*Ngroupıd*<br/>
Grup KIMLIĞINI belirtir.

*Nobjectıd*<br/>
Nesne KIMLIĞINI belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı verileri belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan özelliklerle CAnimationPoint nesnesi oluşturur: varsayılan nokta koordinatları, Grup KIMLIĞI ve nesne KIMLIĞI 0 olarak ayarlanır.

## <a name="canimationpointgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationPoint:: GetAnimationVariableList

Encapsulated animasyon değişkenlerini bir listeye koyar.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*LST*<br/>
İşlev döndüğünde, X ve Y koordinatlarını temsil eden iki CAnimationVariable nesnesine işaretçiler içerir.

## <a name="canimationpointgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationPoint:: GetDefaultValue

X ve Y koordinatları için varsayılan değerleri döndürür.

```
CPoint GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan değer içeren bir nokta.

### <a name="remarks"></a>Açıklamalar

Daha önce constructor veya SetDefaultValue tarafından ayarlanan varsayılan değeri almak için bu işlevi çağırın.

## <a name="canimationpointgetvalue"></a><a name="getvalue"></a> CAnimationPoint:: GetValue

Geçerli değeri döndürür.

```
BOOL GetValue(CPoint& ptValue);
```

### <a name="parameters"></a>Parametreler

*ptValue*<br/>
Çıktıların. Bu yöntemin döndürdüğü geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer başarıyla alınırsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Animasyon noktasının geçerli değerini almak için bu işlevi çağırın. Bu yöntem başarısız olursa veya X ve Y koordinatları için temel alınan COM nesneleri başlatılmazsa, ptValue daha önce oluşturucuda veya SetDefaultValue tarafından ayarlanan varsayılan değeri içerir.

## <a name="canimationpointgetx"></a><a name="getx"></a> CAnimationPoint:: GetX

X koordinatı için CAnimationVariable öğesine erişim sağlar.

```
CAnimationVariable& GetX();
```

### <a name="return-value"></a>Dönüş Değeri

X koordinatını temsil eden kapsüllenmiş CAnimationVariable başvurusu.

### <a name="remarks"></a>Açıklamalar

X koordinatını temsil eden temeldeki CAnimationVariable 'a doğrudan erişim sağlamak için bu yöntemi çağırabilirsiniz.

## <a name="canimationpointgety"></a><a name="gety"></a> CAnimationPoint:: GetY

Y koordinatı için CAnimationVariable erişimi sağlar.

```
CAnimationVariable& GetY();
```

### <a name="return-value"></a>Dönüş Değeri

Y koordinatını temsil eden kapsüllenmiş CAnimationVariable başvurusu.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, Y koordinatını temsil eden temeldeki CAnimationVariable öğesine doğrudan erişim sağlamak için çağırabilirsiniz.

## <a name="canimationpointm_xvalue"></a><a name="m_xvalue"></a> CAnimationPoint:: m_xValue

Animasyon noktasının X koordinatını temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_xValue;
```

## <a name="canimationpointm_yvalue"></a><a name="m_yvalue"></a> CAnimationPoint:: m_yValue

Animasyon noktasının Y koordinatını temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_yValue;
```

## <a name="canimationpointoperator-cpoint"></a><a name="operator_cpoint"></a> CAnimationPoint:: operator CPoint

CAnimationPoint 'i bir CPoint 'e dönüştürür.

```
operator CPoint();
```

### <a name="return-value"></a>Dönüş Değeri

CAnimationPoint 'in geçerli değeri CPoint olarak.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir dahili olarak GetValue çağırır. GetValue bir nedenden dolayı başarısız olursa, döndürülen nokta X ve Y koordinatları için varsayılan değerleri içerir.

## <a name="canimationpointoperator"></a><a name="operator_eq"></a> CAnimationPoint:: operator =

PtSrc 'yi CAnimationPoint 'e atar.

```cpp
void operator=(const CPoint& ptSrc);
```

### <a name="parameters"></a>Parametreler

*ptSrc*<br/>
CPoint veya POINT 'e başvurur.

### <a name="remarks"></a>Açıklamalar

PtSrc 'yi CAnimationPoint 'e atar. Bu işleç, oluşturulduklarında X ve Y koordinatları için temeldeki COM nesnelerini yeniden oluşturan SetDefaultValue ' ı çağırdığı için, animasyon başlamadan önce bunu yapmanız önerilir. Bu animasyon nesnesini olaylara abone oldıysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="canimationpointsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationPoint:: SetDefaultValue

Varsayılan değeri ayarlar.

```cpp
void SetDefaultValue(const POINT& ptDefault);
```

### <a name="parameters"></a>Parametreler

*ptDefault*<br/>
Varsayılan nokta değerini belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine varsayılan bir değer ayarlamak için bu işlevi kullanın. Bu yöntemler, animasyon noktasının X ve Y koordinatlarına varsayılan değerler atar. Ayrıca, oluşturulan temel COM nesnelerini de yeniden oluşturur. Bu animasyon nesnesini olaylara abone oldıysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
