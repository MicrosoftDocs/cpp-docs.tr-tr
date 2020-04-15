---
title: CAnimationValue Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
ms.openlocfilehash: 0437f0fc66f64ccb99157330154bf5aa4b5666b3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321974"
---
# <a name="canimationvalue-class"></a>CAnimationValue Sınıfı

Tek bir değere sahip animasyon nesnesinin işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationValue : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationValue::CAnimationValue](#canimationvalue)|Fazla Yüklendi. CAnimationValue nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationValue::AddTransition](#addtransition)|Bir değere uygulanacak bir geçiş ekler.|
|[CAnimationValue::GetValue](#getvalue)|Fazla Yüklendi. Geçerli değeri alır.|
|[CAnimationValue::GetVariable](#getvariable)|Kapsüllü animasyon değişkenine erişim sağlar.|
|[CAnimationValue::SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenini bir listeye koyar. [(CAnimationBaseObject geçersiz kılar::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationValue::operatör ÇİFT](#operator_double)|CAnimationValue ve DOUBLE arasında dönüştürme sağlar.|
|[CAnimationValue::operatör INT32](#operator_int32)|CAnimationValue ve INT32 arasında dönüştürme sağlar.|
|[CAnimationValue::operator=](#operator_eq)|Fazla Yüklendi. CAnimationValue'a bir INT32 değeri atar.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationValue::m_value](#m_value)|Animasyon değerini temsil eden kapsüllü animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationValue sınıfı tek bir CAnimationVariable nesnesini kapsüller ve uygulamalarda tek bir animasyonlu değeri temsil edebilir. Örneğin, bu sınıfı animasyonlu saydamlık (soluk efekti), açı (nesneleri döndürmek için) veya tek bir animasyon değerine bağlı olarak animasyon oluşturmanız gerektiğinde başka bir durum için kullanabilirsiniz. Uygulamada bu sınıfı kullanmak için, bu sınıfın bir nesnesini anlık olarak eklemeniz, CAnimationController kullanarak animasyon denetleyicisine eklemeniz::AddAnimationObject ve değere uygulanacak her geçiş için AddTransition'ı arayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationValue`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationvalueaddtransition"></a><a name="addtransition"></a>CAnimationValue::AddTransition

Bir değere uygulanacak bir geçiş ekler.

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Parametreler

*pGeçiş*<br/>
Nesneyi geçiş için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Animasyon değişkenine uygulanacak iç geçişler listesine geçiş eklemek için bu işlevi çağırın. Geçişler eklediğinizde, bunlar hemen uygulanmaz ve dahili bir listede depolanır. Geçişler CAnimationController::AnimateGroup'u aradiğinizde uygulanır (belirli bir değer için bir film şeridine eklenir).

## <a name="canimationvaluecanimationvalue"></a><a name="canimationvalue"></a>CAnimationValue::CAnimationValue

CAnimationValue nesnesi oluşturuyor.

```
CAnimationValue();

CAnimationValue(
    DOUBLE dblDefaultValue,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*dblDefaultValue*<br/>
Varsayılan değeri belirtir.

*nGroupID*<br/>
Grup Kimliğini belirtir.

*nObjectID*<br/>
Nesne Kimliğini belirtir.

*dwUserData*<br/>
kullanıcı tanımlı verileri belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan özelliklere sahip CAnimationValue nesnesi yapıları: varsayılan değer, Grup Kimliği ve Object ID 0 olarak ayarlanır.

## <a name="canimationvaluegetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationValue::GetAnimationVariableList

Kapsüllenmiş animasyon değişkenini bir listeye koyar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*Lst*<br/>
İşlev döndüğünde, animasyonlu değeri temsil eden CAnimationVariable için bir işaretçi içerir.

## <a name="canimationvaluegetvalue"></a><a name="getvalue"></a>CAnimationValue::GetValue

Geçerli değeri alır.

```
BOOL GetValue(DOUBLE& dblValue);
BOOL GetValue(INT32& nValue);
```

### <a name="parameters"></a>Parametreler

*dblValue*<br/>
Çıkış. İşlev döndüğünde animasyon değişkeninin geçerli bir değerini içerir.

*nDeğer*<br/>
Çıkış. İşlev döndüğünde animasyon değişkeninin geçerli bir değerini içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer başarıyla alındıysa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Geçerli değeri almak için bu işlevi arayın. Bu uygulama kapsüllenmiş COM nesnesini çağırır ve arama başarısız olursa, bu yöntem daha önce oluşturucu veya SetDefaultValue ile ayarlanmış varsayılan değeri döndürür.

## <a name="canimationvaluegetvariable"></a><a name="getvariable"></a>CAnimationValue::GetVariable

Kapsüllü animasyon değişkenine erişim sağlar.

```
CAnimationVariable& GetVariable();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllü animasyon değişkenine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Kapsüllü animasyon değişkenine erişmek için bu yöntemi kullanın. CAnimationVariable'ten, animasyon değişkeni oluşturulmazsa işaretçisi NULL olabilecek alttaki IUIAnimationVariable nesnesine erişebilirsiniz.

## <a name="canimationvaluem_value"></a><a name="m_value"></a>CAnimationValue::m_value

Animasyon değerini temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_value;
```

## <a name="canimationvalueoperator-double"></a><a name="operator_double"></a>CAnimationValue::operatör ÇİFT

CAnimationValue ve DOUBLE arasında dönüştürme sağlar.

```
operator DOUBLE();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon Değerinin geçerli değeri.

### <a name="remarks"></a>Açıklamalar

CAnimationValue ve DOUBLE arasında dönüştürme sağlar. Bu yöntem dahili olarak GetValue çağırır ve hataları denetlemez. GetValue başarısız olursa, döndürülen değer daha önce oluşturucu veya SetDefaultValue ile ayarlanmış varsayılan bir değer içerir.

## <a name="canimationvalueoperator-int32"></a><a name="operator_int32"></a>CAnimationValue::operatör INT32

CAnimationValue ve INT32 arasında dönüştürme sağlar.

```
operator INT32();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon Değerinin birandı olarak geçerli değeri.

### <a name="remarks"></a>Açıklamalar

CAnimationValue ve INT32 arasında dönüştürme sağlar. Bu yöntem dahili olarak GetValue çağırır ve hataları denetlemez. GetValue başarısız olursa, döndürülen değer daha önce oluşturucu veya SetDefaultValue ile ayarlanmış varsayılan bir değer içerir.

## <a name="canimationvalueoperator"></a><a name="operator_eq"></a>CAnimationValue::operator=

CAnimationValue'a ÇİFT değer atar.

```
void operator=(DOUBLE dblVal);
void operator=(INT32 nVal);
```

### <a name="parameters"></a>Parametreler

*dblVal*<br/>
Animasyon Değeri'ne atanacak değeri belirtir.

*nVal*<br/>
Animasyon Değeri'ne atanacak değeri belirtir.

### <a name="remarks"></a>Açıklamalar

CAnimationValue'a ÇİFT değer atar. Bu değer kapsüllenmiş animasyon değişkeni için varsayılan değer olarak ayarlanır. Bu animasyon nesnesini olaylara abone olduysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="canimationvaluesetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationValue::SetDefaultValue

Varsayılan değeri ayarlar.

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Parametreler

*dblDefaultValue*<br/>
Varsayılan değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan değer ayarlamak için bu yöntemi kullanın. Animasyon başlatılınca ve/veya temel COM nesnesi oluşturulmadısa varsayılan değer uygulamaya döndürülür. CAnimationVarible'da kapsüllenen temel COM nesnesi zaten oluşturulduysa, bu yöntem onu yeniden oluşturur, bu nedenle EnableValueChanged/EnableIntegerValueChanged yöntemlerini yeniden aramanız gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
