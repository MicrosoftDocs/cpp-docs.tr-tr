---
description: 'Daha fazla bilgi edinin: CAnimationValue sınıfı'
title: CAnimationValue sınıfı
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
ms.openlocfilehash: d704e83d286b4078af90d09edef35e8445d149d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336742"
---
# <a name="canimationvalue-class"></a>CAnimationValue sınıfı

Bir değere sahip animasyon nesnesinin işlevselliğini uygular.

## <a name="syntax"></a>Syntax

```
class CAnimationValue : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationValue:: CAnimationValue](#canimationvalue)|Fazla Yüklendi. Bir CAnimationValue nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationValue:: AddTransition](#addtransition)|Bir değere uygulanacak bir geçiş ekler.|
|[CAnimationValue:: GetValue](#getvalue)|Fazla Yüklendi. Geçerli değeri alır.|
|[CAnimationValue:: GetVariable](#getvariable)|Encapsulated animasyon değişkenine erişim sağlar.|
|[CAnimationValue:: SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationValue:: GetAnimationVariableList](#getanimationvariablelist)|Encapsulated animasyon değişkenini bir listeye koyar. ( [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)geçersiz kılınır.)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationValue:: operator DOUBLE](#operator_double)|CAnimationValue ve DOUBLE arasında dönüştürme sağlar.|
|[CAnimationValue:: operator ıNT32](#operator_int32)|CAnimationValue ve ıNT32 arasında dönüştürme sağlar.|
|[CAnimationValue:: operator =](#operator_eq)|Fazla Yüklendi. CAnimationValue için bir ıNT32 değeri atar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationValue:: m_value](#m_value)|Animasyon değerini temsil eden Encapsulated animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationValue sınıfı, tek bir CAnimationVariable nesnesini kapsüller ve uygulamalarda tek bir animasyon değeri temsil edebilir. Örneğin, bu sınıfı animasyonlu saydamlık (Silinme efekti), açı (nesneleri döndürmek için) veya tek bir animasyonlu değere bağlı olarak bir animasyon oluşturmanız gerektiğinde başka herhangi bir durum için kullanabilirsiniz. Bu sınıfı uygulamada kullanmak için, bu sınıfın bir nesnesinin örneğini oluşturun, CAnimationController:: AddAnimationObject öğesini kullanarak animasyon denetleyicisine ekleyin ve değere uygulanacak her geçiş için AddTransition çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationValue`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationvalueaddtransition"></a><a name="addtransition"></a> CAnimationValue:: AddTransition

Bir değere uygulanacak bir geçiş ekler.

```cpp
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Parametreler

*pTransition*<br/>
Geçiş nesnesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bir animasyon değişkenine uygulanacak geçişlerin iç listesine bir geçiş eklemek için bu işlevi çağırın. Geçişler eklediğinizde, bunlar hemen uygulanmaz ve dahili bir listede depolanır. CAnimationController:: AnimateGroup ' i çağırdığınızda geçişler uygulanır (belirli bir değer için bir görsel taslağa eklenir).

## <a name="canimationvaluecanimationvalue"></a><a name="canimationvalue"></a> CAnimationValue:: CAnimationValue

Bir CAnimationValue nesnesi oluşturur.

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

*Ngroupıd*<br/>
Grup KIMLIĞINI belirtir.

*Nobjectıd*<br/>
Nesne KIMLIĞINI belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı verileri belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan özelliklerle CAnimationValue nesnesi oluşturur: varsayılan değer, Grup KIMLIĞI ve nesne KIMLIĞI 0 olarak ayarlanır.

## <a name="canimationvaluegetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationValue:: GetAnimationVariableList

Encapsulated animasyon değişkenini bir listeye koyar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*LST*<br/>
İşlev döndürüldüğünde, hareketli değeri temsil eden CAnimationVariable için bir işaretçi içerir.

## <a name="canimationvaluegetvalue"></a><a name="getvalue"></a> CAnimationValue:: GetValue

Geçerli değeri alır.

```
BOOL GetValue(DOUBLE& dblValue);
BOOL GetValue(INT32& nValue);
```

### <a name="parameters"></a>Parametreler

*dblValue*<br/>
Çıktıların. İşlev döndürdüğü zaman animasyon değişkeninin geçerli bir değerini içerir.

*nDeğer*<br/>
Çıktıların. İşlev döndürdüğü zaman animasyon değişkeninin geçerli bir değerini içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer başarıyla alınırsa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Geçerli değeri almak için bu işlevi çağırın. Bu uygulama, kapsüllenmiş COM nesnesini çağırır ve çağrı başarısız olursa, bu yöntem daha önce oluşturucuda veya SetDefaultValue ile ayarlanan varsayılan değeri döndürür.

## <a name="canimationvaluegetvariable"></a><a name="getvariable"></a> CAnimationValue:: GetVariable

Encapsulated animasyon değişkenine erişim sağlar.

```
CAnimationVariable& GetVariable();
```

### <a name="return-value"></a>Dönüş Değeri

Encapsulated animasyon değişkenine başvuru.

### <a name="remarks"></a>Açıklamalar

Encapsulated animasyon değişkenine erişmek için bu yöntemi kullanın. CAnimationVariable, bir animasyon değişkeni oluşturulmadıysa işaretçi NULL olabilecek, temeldeki IUIAnimationVariable nesnesine erişim edinirsiniz.

## <a name="canimationvaluem_value"></a><a name="m_value"></a> CAnimationValue:: m_value

Animasyon değerini temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_value;
```

## <a name="canimationvalueoperator-double"></a><a name="operator_double"></a> CAnimationValue:: operator DOUBLE

CAnimationValue ve DOUBLE arasında dönüştürme sağlar.

```
operator DOUBLE();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon değerinin geçerli değeri.

### <a name="remarks"></a>Açıklamalar

CAnimationValue ve DOUBLE arasında dönüştürme sağlar. Bu yöntem, bir dahili olarak GetValue çağırır ve hata denetimi yapmaz. GetValue başarısız olursa, döndürülen değer, daha önce oluşturucuda veya SetDefaultValue ile ayarlanmış bir varsayılan değer içerecektir.

## <a name="canimationvalueoperator-int32"></a><a name="operator_int32"></a> CAnimationValue:: operator ıNT32

CAnimationValue ve ıNT32 arasında dönüştürme sağlar.

```
operator INT32();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon değerinin geçerli değeri tamsayı olarak.

### <a name="remarks"></a>Açıklamalar

CAnimationValue ve ıNT32 arasında dönüştürme sağlar. Bu yöntem, bir dahili olarak GetValue çağırır ve hata denetimi yapmaz. GetValue başarısız olursa, döndürülen değer, daha önce oluşturucuda veya SetDefaultValue ile ayarlanmış bir varsayılan değer içerecektir.

## <a name="canimationvalueoperator"></a><a name="operator_eq"></a> CAnimationValue:: operator =

CAnimationValue öğesine bir DOUBLE değeri atar.

```cpp
void operator=(DOUBLE dblVal);
void operator=(INT32 nVal);
```

### <a name="parameters"></a>Parametreler

*dblVal*<br/>
Animasyon değerine atanacak değeri belirtir.

*nVal*<br/>
Animasyon değerine atanacak değeri belirtir.

### <a name="remarks"></a>Açıklamalar

CAnimationValue öğesine bir DOUBLE değeri atar. Bu değer, kapsüllenmiş animasyon değişkeni için varsayılan değer olarak ayarlanır. Bu animasyon nesnesini olaylara abone oldıysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="canimationvaluesetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationValue:: SetDefaultValue

Varsayılan değeri ayarlar.

```cpp
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Parametreler

*dblDefaultValue*<br/>
Varsayılan değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan bir değer ayarlamak için bu yöntemi kullanın. Animasyon başlatılmamışsa ve/veya temel alınan COM nesnesi oluşturulmadıysa, uygulamaya varsayılan bir değer döndürülür. CAnimationVarible 'da Kapsüllenen temeldeki COM nesnesi zaten oluşturulmuşsa, bu yöntem onu yeniden oluşturur, bu nedenle EnableValueChanged/EnableIntegerValueChanged yöntemlerini tekrar çağırmanız gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
