---
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
ms.openlocfilehash: 86a2caa8946bcafeabf85687a24b2430ecefe790
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283546"
---
# <a name="canimationvalue-class"></a>CAnimationValue sınıfı

Bir değeri olan animasyon nesnesinin işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationValue : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationValue::CAnimationValue](#canimationvalue)|Fazla Yüklendi. CAnimationValue bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationValue::AddTransition](#addtransition)|Bir değere uygulanacak bir geçiş ekler.|
|[CAnimationValue::GetValue](#getvalue)|Fazla Yüklendi. Geçerli bir değer alır.|
|[CAnimationValue::GetVariable](#getvariable)|Kapsüllenmiş animasyon değişkenin erişim sağlar.|
|[CAnimationValue::SetDefaultValue](#setdefaultvalue)|Varsayılan değerini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkeninin bir listesine koyar. (Geçersiz kılmaları [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationValue::operator çift](#operator_double)|CAnimationValue ve DOUBLE arasında dönüştürme sağlar.|
|[CAnimationValue::operator Int32](#operator_int32)|CAnimationValue ve Int32 arasında dönüştürme sağlar.|
|[CAnimationValue::operator=](#operator_eq)|Fazla Yüklendi. Bir Int32 değeri için CAnimationValue atar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationValue::m_value](#m_value)|Animasyon değeri temsil eden kapsüllenmiş animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationValue sınıfı, tek bir CAnimationVariable nesne kapsüller ve uygulamalarında tek bir animasyonlu değeri temsil edebilir. Animasyonlu saydamlık (fade etkisi) açı (nesneleri döndürmek için), örneğin, bu sınıf kullanabilirsiniz veya tek bir animasyonlu değerine bağlı olarak bir animasyon oluşturmak ihtiyacınız olduğunda herhangi diğer çalışması için. Bu sınıf kullanmak için yalnızca bu sınıfın bir nesnesi, CAnimationController::AddAnimationObject kullanarak animasyon denetleyicisine eklemek ve değere uygulanacak AddTransition her geçiş için çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationValue`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationValue::AddTransition

Bir değere uygulanacak bir geçiş ekler.

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Parametreler

*pTransition*<br/>
Geçiş nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçiş için bir animasyon değişkenini uygulanacak geçişleri iç listesine eklemek için bu işlevi çağırın. Geçişleri eklediğinizde, bunlar değil hemen uygulanır ve bir iç listesinde depolanır. Geçiş (belirli bir değeri için bir görsel taslağı eklenebilir) uygulandığını CAnimationController::AnimateGroup çağırdığınızda.

##  <a name="canimationvalue"></a>  CAnimationValue::CAnimationValue

CAnimationValue bir nesne oluşturur.

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
Varsayılan bir değer belirtir.

*nGroupID*<br/>
Grup kimliğini belirtir.

*nObjectID*<br/>
Nesne kimliğini belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı veri belirtir.

### <a name="remarks"></a>Açıklamalar

CAnimationValue varsayılan özelliklere sahip bir nesne oluşturur: Grup Kimliği ve nesne kimliği varsayılan değer 0 olarak ayarlanır.

##  <a name="getanimationvariablelist"></a>  CAnimationValue::GetAnimationVariableList

Kapsüllenmiş animasyon değişkeninin bir listesine koyar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*lst*<br/>
İşlevi döndüğünde CAnimationVariable animasyonlu değeri temsil eden bir işaretçi içerir.

##  <a name="getvalue"></a>  CAnimationValue::GetValue

Geçerli bir değer alır.

```
BOOL GetValue(DOUBLE& dblValue);
BOOL GetValue(INT32& nValue);
```

### <a name="parameters"></a>Parametreler

*dblValue*<br/>
Çıktı. İşlevi döndüğünde animasyon değişkenin geçerli değeri içerir.

*nDeğer*<br/>
Çıktı. İşlevi döndüğünde animasyon değişkenin geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer başarıyla alındığında TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Geçerli değerini almak için bu işlevi çağırın. Bu uygulama kapsüllenmiş COM nesnesi çağırır ve çağrı başarısız olursa, bu yöntem Oluşturucusu veya SetDefaultValue önceden ayarlanmış varsayılan değeri döndürür.

##  <a name="getvariable"></a>  CAnimationValue::GetVariable

Kapsüllenmiş animasyon değişkenin erişim sağlar.

```
CAnimationVariable& GetVariable();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş animasyon değişkeninin bir başvuru.

### <a name="remarks"></a>Açıklamalar

Kapsüllenmiş animasyon değişkenini erişmek için bu yöntemi kullanın. CAnimationVariable animasyon değişkenini oluşturulmadı, işaretçi NULL olabilir, temel alınan IUIAnimationVariable nesne erişim elde edersiniz.

##  <a name="m_value"></a>  CAnimationValue::m_value

Animasyon değeri temsil eden kapsüllenmiş animasyon değişkeni.

```
CAnimationVariable m_value;
```

##  <a name="operator_double"></a>  CAnimationValue::operator çift

CAnimationValue ve DOUBLE arasında dönüştürme sağlar.

```
operator DOUBLE();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon değeri geçerli değeri.

### <a name="remarks"></a>Açıklamalar

CAnimationValue ve DOUBLE arasında dönüştürme sağlar. Bu yöntem, dahili olarak GetValue çağırır ve hatalar için denetlemez. GetValue başarısız olursa, döndürülen değer oluşturucu veya SetDefaultValue önceden ayarlanmış bir varsayılan değeri içerir.

##  <a name="operator_int32"></a>  CAnimationValue::operator Int32

CAnimationValue ve Int32 arasında dönüştürme sağlar.

```
operator INT32();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon değeri tamsayı olarak geçerli değeri.

### <a name="remarks"></a>Açıklamalar

CAnimationValue ve Int32 arasında dönüştürme sağlar. Bu yöntem, dahili olarak GetValue çağırır ve hatalar için denetlemez. GetValue başarısız olursa, döndürülen değer oluşturucu veya SetDefaultValue önceden ayarlanmış bir varsayılan değeri içerir.

##  <a name="operator_eq"></a>  CAnimationValue::operator =

CAnimationValue için bir DOUBLE değeri atar.

```
void operator=(DOUBLE dblVal);
void operator=(INT32 nVal);
```

### <a name="parameters"></a>Parametreler

*dblVal*<br/>
Animasyon değeri atanacak değeri belirtir.

*nVal*<br/>
Animasyon değeri atanacak değeri belirtir.

### <a name="remarks"></a>Açıklamalar

CAnimationValue için bir DOUBLE değeri atar. Bu değer, kapsüllenmiş animasyon değişkenin varsayılan değeri olarak ayarlanır. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesnesine abone, bu olayları yeniden etkinleştirmeniz gerekir.

##  <a name="setdefaultvalue"></a>  CAnimationValue::SetDefaultValue

Varsayılan değerini ayarlar.

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Parametreler

*dblDefaultValue*<br/>
Varsayılan değer belirtir.

### <a name="remarks"></a>Açıklamalar

Varsayılan değer ayarlamak için bu yöntemi kullanın. Varsayılan değer, animasyon başlatılmadı ve/veya COM nesnesini oluşturulmadı, uygulamaya döndürülür. İçinde CAnimationVarible kapsüllenmiş COM nesnesini zaten oluşturulmuş olsa bile, bu yöntem yeniden oluşturur, bu nedenle EnableValueChanged/EnableIntegerValueChanged yöntemleri tekrar başvurmanız gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
