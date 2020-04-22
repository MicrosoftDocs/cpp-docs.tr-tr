---
title: CAnimationColor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
ms.openlocfilehash: 7c1c98d739aa1c17bb30df2d9d4ce8c41558c76d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750198"
---
# <a name="canimationcolor-class"></a>CAnimationColor Sınıfı

Kırmızı, yeşil ve mavi bileşenleri animasyonlu olabilecek bir rengin işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationColor : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationColor::CAnimationColor](#canimationcolor)|Fazla Yüklendi. Animasyon renk nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationColor::EkleGeçiş](#addtransition)|Kırmızı, Yeşil ve Mavi bileşenleri için geçişler ekler.|
|[CAnimationColor::GetB](#getb)|Mavi bileşeni temsil eden CAnimationVariable'e erişim sağlar.|
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|Renk bileşenleri için varsayılan değerleri döndürür.|
|[CAnimationColor::GetG](#getg)|Yeşil bileşeni temsil eden CAnimationVariable'e erişim sağlar.|
|[CAnimationColor::GetR](#getr)|Kırmızı bileşeni temsil eden CAnimationVariable'e erişim sağlar.|
|[CAnimationColor::GetValue](#getvalue)|Geçerli değeri verir.|
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenlerini bir listeye koyar. [(CAnimationBaseObject geçersiz kılar::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationColor::operatör COLORREF](#operator_colorref)||
|[CAnimationColor::operator=](#operator_eq)|CAnimationColor'a renk atar.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationColor::m_bValue](#m_bvalue)|Animasyon renginin Mavi bileşenini temsil eden kapsüllü animasyon değişkeni.|
|[CAnimationColor::m_gValue](#m_gvalue)|Animasyon renginin Yeşil bileşenini temsil eden kapsüllü animasyon değişkeni.|
|[CAnimationColor::m_rValue](#m_rvalue)|Animasyon renginin Kırmızı bileşenini temsil eden kapsüllü animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationColor sınıfı üç CAnimationVariable nesnesini kapsüller ve uygulamalarda bir rengi temsil edebilir. Örneğin, bu sınıfı ekrandaki herhangi bir nesnenin renklerini (metin rengi, arka plan rengi vb.) canlandırmak için kullanabilirsiniz. Uygulamada bu sınıfı kullanmak için, bu sınıfın bir nesnesini anlık olarak eklemeniz, CAnimationController kullanarak animasyon denetleyicisine ekleyin::AddAnimationObject ve Kırmızı, Yeşil ve Mavi bileşenlere uygulanacak her geçiş için AddTransition'ı arayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationColor`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationcoloraddtransition"></a><a name="addtransition"></a>CAnimationColor::EkleGeçiş

Kırmızı, Yeşil ve Mavi bileşenleri için geçişler ekler.

```cpp
void AddTransition(
    CBaseTransition* pRTransition,
    CBaseTransition* pGTransition,
    CBaseTransition* pBTransition);
```

### <a name="parameters"></a>Parametreler

*pRTransition*<br/>
Kırmızı bileşen için geçiş.

*pGTransition*<br/>
Yeşil bileşen için geçiş.

*pBGeçiş*<br/>
Mavi bileşen için geçiş.

### <a name="remarks"></a>Açıklamalar

Renk bileşenlerini temsil eden animasyon değişkenlerine uygulanacak iç geçişler listesine belirtilen geçişleri eklemek için bu işlevi arayın. Geçişler eklediğinizde, bunlar hemen uygulanmaz ve dahili bir listede depolanır. Geçişler CAnimationController::AnimateGroup'u aradiğinizde uygulanır (belirli bir değer için bir film şeridine eklenir). Renk bileşenlerinden birine geçiş uygulamanız gerekmiyorsa, NULL'u geçebilirsiniz.

## <a name="canimationcolorcanimationcolor"></a><a name="canimationcolor"></a>CAnimationColor::CAnimationColor

CAnimationColor nesnesi oluşturuyor.

```
CAnimationColor();

CAnimationColor(
    COLORREF color,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
Varsayılan rengi belirtir.

*nGroupID*<br/>
Grup Kimliğini belirtir.

*nObjectID*<br/>
Nesne Kimliğini belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı verileri belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne, 0 olarak ayarlanacak olan kırmızı, yeşil, mavi, Nesne Kimliği ve Grup Kimliği için varsayılan değerlerle oluşturulur. Bunlar daha sonra setdefaultvalue ve SetID kullanılarak çalışma zamanında değiştirilebilir.

## <a name="canimationcolorgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationColor::GetAnimationVariableList

Kapsüllenmiş animasyon değişkenlerini bir listeye koyar.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*Lst*<br/>
İşlev döndüğünde, kırmızı, yeşil ve mavi bileşenleri temsil eden üç CAnimationVariable nesnelerine işaretçiler içerir.

## <a name="canimationcolorgetb"></a><a name="getb"></a>CAnimationColor::GetB

Mavi bileşeni temsil eden CAnimationVariable'e erişim sağlar.

```
CAnimationVariable& GetB();
```

### <a name="return-value"></a>Dönüş Değeri

Mavi bileşeni temsil eden kapsüllü CAnimationVariable'e bir başvuru.

### <a name="remarks"></a>Açıklamalar

Mavi bileşeni temsil eden altta yatan CAnimationVariable'e doğrudan erişim elde etmek için bu yöntemi arayabilirsiniz.

## <a name="canimationcolorgetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationColor::GetDefaultValue

Renk bileşenleri için varsayılan değerleri döndürür.

```
COLORREF GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

RGB bileşenleri için varsayılanları içeren bir COLORREF değeri.

### <a name="remarks"></a>Açıklamalar

Daha önce oluşturucu veya SetDefaultValue tarafından ayarlanmış varsayılan değeri almak için bu işlevi arayın.

## <a name="canimationcolorgetg"></a><a name="getg"></a>CAnimationColor::GetG

Yeşil bileşeni temsil eden CAnimationVariable'e erişim sağlar.

```
CAnimationVariable& GetG();
```

### <a name="return-value"></a>Dönüş Değeri

Yeşil bileşeni temsil eden kapsüllü CAnimationVariable'e bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yeşil bileşeni temsil eden temel CAnimationVariable'e doğrudan erişim elde etmek için bu yöntemi arayabilirsiniz.

## <a name="canimationcolorgetr"></a><a name="getr"></a>CAnimationColor::GetR

Kırmızı bileşeni temsil eden CAnimationVariable'e erişim sağlar.

```
CAnimationVariable& GetR();
```

### <a name="return-value"></a>Dönüş Değeri

Kırmızı bileşeni temsil eden kapsüllü CAnimationVariable'e bir başvuru.

### <a name="remarks"></a>Açıklamalar

Kırmızı bileşeni temsil eden altta yatan CAnimationVariable'e doğrudan erişim elde etmek için bu yöntemi arayabilirsiniz.

## <a name="canimationcolorgetvalue"></a><a name="getvalue"></a>CAnimationColor::GetValue

Geçerli değeri verir.

```
BOOL GetValue(COLORREF& color);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
Çıkış. Bu yöntem döndüğünde geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU, geçerli değer başarıyla alındıysa; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Animasyon renginin geçerli değerini almak için bu işlevi arayın. Bu yöntem başarısız olursa veya renk bileşenleri için com nesneleri temele boyanır baş harflerine sahip değilse, renk daha önce oluşturucu veya SetDefaultValue tarafından ayarlanmış varsayılan değer içerir.

## <a name="canimationcolorm_bvalue"></a><a name="m_bvalue"></a>CAnimationColor::m_bValue

Animasyon renginin Mavi bileşenini temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_bValue;
```

## <a name="canimationcolorm_gvalue"></a><a name="m_gvalue"></a>CAnimationColor::m_gValue

Animasyon renginin Yeşil bileşenini temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_gValue;
```

## <a name="canimationcolorm_rvalue"></a><a name="m_rvalue"></a>CAnimationColor::m_rValue

Animasyon renginin Kırmızı bileşenini temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_rValue;
```

## <a name="canimationcoloroperator-colorref"></a><a name="operator_colorref"></a>CAnimationColor::operatör COLORREF

```
operator COLORREF();
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="canimationcoloroperator"></a><a name="operator_eq"></a>CAnimationColor::operator=

CAnimationColor'a renk atar.

```cpp
void operator=(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
Yeni değer Animasyon Rengi belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon başlamadan önce bunu yapmanız önerilir, çünkü bu işleç, oluşturulduklarında renk bileşenleri için temel COM nesnelerini yeniden oluşturan SetDefaultValue'ı çağırır. Bu animasyon nesnesini olaylara abone olduysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="canimationcolorsetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationColor::SetDefaultValue

Varsayılan değeri ayarlar.

```cpp
void SetDefaultValue(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
Kırmızı, yeşil ve mavi bileşenler için yeni varsayılan değerler belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine varsayılan değer ayarlamak için bu işlevi kullanın. Bu yöntem, varsayılan değerleri animasyon renginin renk bileşenlerine atar. Ayrıca, oluşturuldukları takdirde altta yatan COM nesnelerini yeniden oluşturur. Bu animasyon nesnesini olaylara abone olduysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
