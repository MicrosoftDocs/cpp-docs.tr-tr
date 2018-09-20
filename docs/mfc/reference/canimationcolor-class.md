---
title: CAnimationColor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 565881fdbc085e7046574d3d468073f49b24f565
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421029"
---
# <a name="canimationcolor-class"></a>CAnimationColor sınıfı

Olan kırmızı, yeşil ve mavi bileşenlerinin animasyonunu oluşturulabilen bir rengin işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationColor : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationColor::CAnimationColor](#canimationcolor)|Fazla Yüklendi. Bir animasyon color nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationColor::AddTransition](#addtransition)|Kırmızı, yeşil ve mavi bileşenlerinin geçişleri ekler.|
|[CAnimationColor::GetB](#getb)|CAnimationVariable temsil eden mavi bileşeni için erişim sağlar.|
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|Renk bileşenleri için varsayılan değerleri döndürür.|
|[CAnimationColor::GetG](#getg)|Yeşil bileşeni temsil eden CAnimationVariable için erişim sağlar.|
|[CAnimationColor::GetR](#getr)|CAnimationVariable temsil eden kırmızı bileşeni için erişim sağlar.|
|[CAnimationColor::GetValue](#getvalue)|Geçerli bir değer döndürür.|
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|Varsayılan değerini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenleri bir listesine koyar. (Geçersiz kılmaları [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationColor::operator COLORREF](#operator_colorref)||
|[CAnimationColor::operator =](#operator_eq)|CAnimationColor için renk atar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationColor::m_bValue](#m_bvalue)|Animasyon renginin mavi bileşenini temsil eden kapsüllenmiş animasyon değişkeni.|
|[CAnimationColor::m_gValue](#m_gvalue)|Yeşil bileşeni animasyon rengi temsil eden kapsüllenmiş animasyon değişkeni.|
|[CAnimationColor::m_rValue](#m_rvalue)|Animasyon rengin kırmızı bileşenini temsil eden kapsüllenmiş animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationColor sınıfı üç CAnimationVariable nesneleri kapsüller ve uygulamalarda bir rengi temsil edebilir. Örneğin, renkleri ekrandaki herhangi bir nesnenin animasyon uygulamak için bu sınıf kullanabilirsiniz (metin rengi gibi arka plan rengi vb.). Bu sınıf kullanmak için yalnızca bu sınıfın bir nesnesi, CAnimationController::AddAnimationObject kullanarak animasyon denetleyicisine eklemek ve kırmızı, yeşil ve mavi bileşenleri için uygulanacak AddTransition her geçiş için çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationColor`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationColor::AddTransition

Kırmızı, yeşil ve mavi bileşenlerinin geçişleri ekler.

```
void AddTransition(
    CBaseTransition* pRTransition,
    CBaseTransition* pGTransition,
    CBaseTransition* pBTransition);
```

### <a name="parameters"></a>Parametreler

*pRTransition*<br/>
Kırmızı bileşeni için geçiş.

*pGTransition*<br/>
Yeşil bileşeni için geçiş.

*pBTransition*<br/>
Mavi bileşeni için geçiş.

### <a name="remarks"></a>Açıklamalar

Belirtilen geçişleri renk bileşenleri temsil eden animasyon değişkenlere uygulanması geçişleri iç listesine eklemek için bu işlevi çağırın. Geçişleri eklediğinizde, bunlar değil hemen uygulanır ve bir iç listesinde depolanır. Geçiş (belirli bir değeri için bir görsel taslağı eklenebilir) uygulandığını CAnimationController::AnimateGroup çağırdığınızda. Renk bileşenlerinden biri için bir geçiş uygulanacak gerekmiyorsa NULL geçirebilirsiniz.

##  <a name="canimationcolor"></a>  CAnimationColor::CAnimationColor

CAnimationColor bir nesne oluşturur.

```
CAnimationColor();

CAnimationColor(
    COLORREF color,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
Varsayılan rengini belirtir.

*nGroupID*<br/>
Grup kimliğini belirtir.

*nObjectID*<br/>
Nesne kimliğini belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı veri belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne, varsayılan değerleri kırmızı, yeşil, mavi, nesne kimliği ve 0 olarak ayarlanacak grubu kimliği ile oluşturulur. Çalışma zamanında SetDefaultValue ve SetID kullanarak daha sonra değiştirilebilir.

##  <a name="getanimationvariablelist"></a>  CAnimationColor::GetAnimationVariableList

Kapsüllenmiş animasyon değişkenleri bir listesine koyar.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*lst*<br/>
İşlevi döndüğünde, kırmızı, yeşil ve mavi bileşenleri temsil eden üç CAnimationVariable nesnelerine işaretçiler içerir.

##  <a name="getb"></a>  CAnimationColor::GetB

CAnimationVariable temsil eden mavi bileşeni için erişim sağlar.

```
CAnimationVariable& GetB();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş CAnimationVariable mavi bileşenini temsil eden bir başvuru.

### <a name="remarks"></a>Açıklamalar

Temel alınan CAnimationVariable temsil eden mavi bileşeni doğrudan erişim elde etmek için bu yöntem çağırabilirsiniz.

##  <a name="getdefaultvalue"></a>  CAnimationColor::GetDefaultValue

Renk bileşenleri için varsayılan değerleri döndürür.

```
COLORREF GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

RGB bileşenleri için varsayılan değerleri içeren bir COLORREF değeri.

### <a name="remarks"></a>Açıklamalar

Oluşturucu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değerini almak için bu işlevi çağırın.

##  <a name="getg"></a>  CAnimationColor::GetG

Yeşil bileşeni temsil eden CAnimationVariable için erişim sağlar.

```
CAnimationVariable& GetG();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş CAnimationVariable temsil eden yeşil bileşenine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Temel alınan CAnimationVariable temsil eden yeşil bileşeni doğrudan erişim elde etmek için bu yöntem çağırabilirsiniz.

##  <a name="getr"></a>  CAnimationColor::GetR

CAnimationVariable temsil eden kırmızı bileşeni için erişim sağlar.

```
CAnimationVariable& GetR();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş CAnimationVariable kırmızı bileşenini temsil eden bir başvuru.

### <a name="remarks"></a>Açıklamalar

Temel alınan CAnimationVariable temsil eden kırmızı bileşeni doğrudan erişim elde etmek için bu yöntem çağırabilirsiniz.

##  <a name="getvalue"></a>  CAnimationColor::GetValue

Geçerli bir değer döndürür.

```
BOOL GetValue(COLORREF& color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
Çıktı. Bu yöntem döndürüldüğünde, geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer başarıyla alındığında TRUE, Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Animasyon renk geçerli değerini almak için bu işlevi çağırın. Bu yöntem başarısız olursa veya renk bileşenleri için temel alınan COM nesnelerini başlatılmamış renk Oluşturucusu veya SetDefaultValue önceden ayarlanmış varsayılan değeri içerir.

##  <a name="m_bvalue"></a>  CAnimationColor::m_bValue

Animasyon renginin mavi bileşenini temsil eden kapsüllenmiş animasyon değişkeni.

```
CAnimationVariable m_bValue;
```

##  <a name="m_gvalue"></a>  CAnimationColor::m_gValue

Yeşil bileşeni animasyon rengi temsil eden kapsüllenmiş animasyon değişkeni.

```
CAnimationVariable m_gValue;
```

##  <a name="m_rvalue"></a>  CAnimationColor::m_rValue

Animasyon rengin kırmızı bileşenini temsil eden kapsüllenmiş animasyon değişkeni.

```
CAnimationVariable m_rValue;
```

##  <a name="operator_colorref"></a>  CAnimationColor::operator COLORREF

```
operator COLORREF();
```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="operator_eq"></a>  CAnimationColor::operator =

CAnimationColor için renk atar.

```
void operator=(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
Yeni değer animasyon rengini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işleç oluşturulduktan gerekiyorsa, renk bileşenleri için temel alınan COM nesneleri yeniden oluşturur ve SetDefaultValue çağırdığı animasyon başlamadan önce bunu yapmak için önerilir. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesnesine abone, bu olayları yeniden etkinleştirmeniz gerekir.

##  <a name="setdefaultvalue"></a>  CAnimationColor::SetDefaultValue

Varsayılan değerini ayarlar.

```
void SetDefaultValue(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
Kırmızı, yeşil ve mavi bileşenlerinin yeni varsayılan değerleri belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine bir varsayılan değer ayarlamak için bu işlevi kullanın. Bu yöntem, animasyon rengi renk bileşenleri için varsayılan değerleri atar. Ayrıca bunlar oluşturulmuşsa temel COM nesneleri yeniden oluşturur. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesnesine abone, bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
