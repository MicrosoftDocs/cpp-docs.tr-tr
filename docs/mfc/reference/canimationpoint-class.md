---
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
ms.openlocfilehash: 15f18a43fcda76bb5531434de84d97a349cb7f39
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497209"
---
# <a name="canimationpoint-class"></a>CAnimationPoint sınıfı

Koordinatlarının animasyonu oluşturulabilen bir nokta işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationPoint : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|Fazla Yüklendi. CAnimationPoint bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationPoint::AddTransition](#addtransition)|X geçişlerini ekler ve Y koordinatları.|
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|Varsayılan değerleri döndürür X ve Y koordinatları.|
|[CAnimationPoint::GetValue](#getvalue)|Geçerli bir değer döndürür.|
|[CAnimationPoint::GetX](#getx)|X koordinatı CAnimationVariable için erişim sağlar.|
|[CAnimationPoint::GetY](#gety)|Erişim için CAnimationVariable Y koordinatı sağlar.|
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|Varsayılan değerini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenleri bir listesine koyar. (Geçersiz kılmaları [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationPoint::operator CPoint](#operator_cpoint)|Bir CAnimationPoint için bir CPoint dönüştürür.|
|[CAnimationPoint::operator =](#operator_eq)|CAnimationPoint için ptSrc atar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationPoint::m_xValue](#m_xvalue)|X temsil eden kapsüllenmiş animasyon değişkeni animasyon noktasının koordinat.|
|[CAnimationPoint::m_yValue](#m_yvalue)|Animasyon noktası Y koordinatını temsil eden kapsüllenmiş animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationPoint sınıfı iki CAnimationVariable nesneleri kapsüller ve uygulamalarda bir noktayı temsil edebilir. Örneğin, bu sınıf, bir ekranın (örneğin, metin dizesi, daire, noktası vb.) herhangi bir nesnenin konumuna animasyon uygulamak için kullanabilirsiniz. Bu sınıf kullanmak için yalnızca bu sınıfın bir nesnesi, animasyon denetleyicisini CAnimationController::AddAnimationObject kullanarak ekleyin ve uygulanacak AddTransition her geçiş için çağrı X ve/veya Y koordinatları.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationPoint`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationPoint::AddTransition

X geçişlerini ekler ve Y koordinatları.

```
void AddTransition(
    CBaseTransition* pXTransition,
    CBaseTransition* pYTransition);
```

### <a name="parameters"></a>Parametreler

*pXTransition*<br/>
Koordinatları X geçiş için bir işaretçi.

*pYTransition*<br/>
Bir işaretçi geçiş y koordinatı.

### <a name="remarks"></a>Açıklamalar

Belirtilen geçiş için X animasyon değişkenlere uygulanacak geçişleri iç listesini eklemek için bu işlevi çağırın ve Y koordinatları. Geçişleri eklediğinizde, bunlar değil hemen uygulanır ve bir iç listesinde depolanır. Geçiş (belirli bir değeri için bir görsel taslağı eklenebilir) uygulandığını CAnimationController::AnimateGroup çağırdığınızda. Bir geçişi bir koordinat uygulamak gerekmiyorsa NULL geçirebilirsiniz.

##  <a name="canimationpoint"></a>  CAnimationPoint::CAnimationPoint

CAnimationPoint bir nesne oluşturur.

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
Varsayılan noktası koordinatları belirtir.

*nGroupID*<br/>
Grup kimliğini belirtir.

*nObjectID*<br/>
Nesne kimliğini belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı veri belirtir.

### <a name="remarks"></a>Açıklamalar

CAnimationPoint varsayılan özelliklere sahip bir nesne oluşturur: nokta koordinatları varsayılan, grup kimliği ve nesne kimliği 0 olarak ayarlanır.

##  <a name="getanimationvariablelist"></a>  CAnimationPoint::GetAnimationVariableList

Kapsüllenmiş animasyon değişkenleri bir listesine koyar.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*lst*<br/>
İşlevi döndüğünde, X ve Y koordinatları temsil eden iki CAnimationVariable nesnelerine işaretçiler içerir.

##  <a name="getdefaultvalue"></a>  CAnimationPoint::GetDefaultValue

Varsayılan değerleri döndürür X ve Y koordinatları.

```
CPoint GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

Bir nokta içeren varsayılan değeri.

### <a name="remarks"></a>Açıklamalar

Oluşturucu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değerini almak için bu işlevi çağırın.

##  <a name="getvalue"></a>  CAnimationPoint::GetValue

Geçerli bir değer döndürür.

```
BOOL GetValue(CPoint& ptValue);
```

### <a name="parameters"></a>Parametreler

*ptValue*<br/>
Çıktı. Bu yöntem döndürüldüğünde, geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer başarıyla alındığında TRUE, Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Animasyon noktası geçerli değerini almak için bu işlevi çağırın. X için bu yöntem başarısız olursa veya temel alınan COM nesnelerini ve Y koordinatları başlatılmamış ptValue Oluşturucusu veya SetDefaultValue önceden ayarlanmış varsayılan değeri içerir.

##  <a name="getx"></a>  CAnimationPoint::GetX

X koordinatı CAnimationVariable için erişim sağlar.

```
CAnimationVariable& GetX();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş CAnimationVariable X temsil eden bir başvuru koordine edin.

### <a name="remarks"></a>Açıklamalar

Temel alınan CAnimationVariable X temsil eden doğrudan erişim elde etmek için bu yöntem çağırabilirsiniz koordine edin.

##  <a name="gety"></a>  CAnimationPoint::GetY

Erişim için CAnimationVariable Y koordinatı sağlar.

```
CAnimationVariable& GetY();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş CAnimationVariable Y koordinatını temsil eden bir başvuru.

### <a name="remarks"></a>Açıklamalar

Temel alınan CAnimationVariable Y koordinatını temsil eden doğrudan erişim elde etmek için bu yöntem çağırabilirsiniz.

##  <a name="m_xvalue"></a>  CAnimationPoint::m_xValue

X temsil eden kapsüllenmiş animasyon değişkeni animasyon noktasının koordinat.

```
CAnimationVariable m_xValue;
```

##  <a name="m_yvalue"></a>  CAnimationPoint::m_yValue

Animasyon noktası Y koordinatını temsil eden kapsüllenmiş animasyon değişkeni.

```
CAnimationVariable m_yValue;
```

##  <a name="operator_cpoint"></a>  CAnimationPoint::operator CPoint

Bir CAnimationPoint için bir CPoint dönüştürür.

```
operator CPoint();
```

### <a name="return-value"></a>Dönüş Değeri

CAnimationPoint CPoint olarak geçerli değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, GetValue dahili olarak çağırır. GetValue herhangi bir nedenle başarısız olursa, döndürülen noktası X için varsayılan değerleri içeren ve Y koordinatları.

##  <a name="operator_eq"></a>  CAnimationPoint::operator =

CAnimationPoint için ptSrc atar.

```
void operator=(const CPoint& ptSrc);
```

### <a name="parameters"></a>Parametreler

*ptSrc*<br/>
CPoint veya NOKTASINA ifade eder.

### <a name="remarks"></a>Açıklamalar

CAnimationPoint için ptSrc atar. Bu işleç, SetDefaultValue çağırdığı oluşturulduktan, X ve Y koordinatları için animasyon başlamadan önce temel alınan COM yeniden oluşturur nesneleri, yapmanız önerilir. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesnesine abone, bu olayları yeniden etkinleştirmeniz gerekir.

##  <a name="setdefaultvalue"></a>  CAnimationPoint::SetDefaultValue

Varsayılan değerini ayarlar.

```
void SetDefaultValue(const POINT& ptDefault);
```

### <a name="parameters"></a>Parametreler

*ptDefault*<br/>
Varsayılan noktası değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine bir varsayılan değer ayarlamak için bu işlevi kullanın. Bu yöntemleri atar varsayılan değerler animasyon noktasının X ve Y koordinatları. Ayrıca bunlar oluşturulmuşsa temel COM nesneleri yeniden oluşturur. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesnesine abone, bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
