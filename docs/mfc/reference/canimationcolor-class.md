---
description: 'Daha fazla bilgi edinin: CAnimationColor sınıfı'
title: CAnimationColor sınıfı
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
ms.openlocfilehash: 430f017bc9d60eed5e2d42b71f0303546deecaca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318643"
---
# <a name="canimationcolor-class"></a>CAnimationColor sınıfı

Kırmızı, yeşil ve mavi bileşenleri animasyonlu olabilecek bir rengin işlevselliğini uygular.

## <a name="syntax"></a>Syntax

```
class CAnimationColor : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationColor:: CAnimationColor](#canimationcolor)|Fazla Yüklendi. Bir animasyon rengi nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationColor:: AddTransition](#addtransition)|Kırmızı, yeşil ve mavi bileşenlere geçişler ekler.|
|[CAnimationColor:: GetB](#getb)|Mavi bileşeni temsil eden CAnimationVariable öğesine erişim sağlar.|
|[CAnimationColor:: GetDefaultValue](#getdefaultvalue)|Renk bileşenleri için varsayılan değerleri döndürür.|
|[CAnimationColor:: GetG](#getg)|Yeşil bileşeni temsil eden CAnimationVariable öğesine erişim sağlar.|
|[CAnimationColor:: GetR](#getr)|Red bileşenini temsil eden CAnimationVariable öğesine erişim sağlar.|
|[CAnimationColor:: GetValue](#getvalue)|Geçerli değeri döndürür.|
|[CAnimationColor:: SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationColor:: GetAnimationVariableList](#getanimationvariablelist)|Encapsulated animasyon değişkenlerini bir listeye koyar. ( [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)geçersiz kılınır.)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationColor:: operator COLORREF](#operator_colorref)||
|[CAnimationColor:: operator =](#operator_eq)|CAnimationColor 'e renk atar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationColor:: m_bValue](#m_bvalue)|Animasyon renginin mavi bileşenini temsil eden Encapsulated animasyon değişkeni.|
|[CAnimationColor:: m_gValue](#m_gvalue)|Animasyon renginin Yeşil bileşenini temsil eden Encapsulated animasyon değişkeni.|
|[CAnimationColor:: m_rValue](#m_rvalue)|Animasyon renginin kırmızı bileşenini temsil eden Encapsulated animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationColor sınıfı üç CAnimationVariable nesnesini kapsüller ve uygulamalarda bir renk temsil edebilir. Örneğin, ekrandaki herhangi bir nesnenin rengine animasyon uygulamak için bu sınıfı kullanabilirsiniz (metin rengi, arka plan rengi vb.). Bu sınıfı uygulamada kullanmak için, bu sınıfın bir nesnesinin örneğini oluşturun, CAnimationController:: AddAnimationObject öğesini kullanarak animasyon denetleyicisine ekleyin ve kırmızı, yeşil ve mavi bileşenlere uygulanacak her geçiş için AddTransition çağrısı yapın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationColor`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationcoloraddtransition"></a><a name="addtransition"></a> CAnimationColor:: AddTransition

Kırmızı, yeşil ve mavi bileşenlere geçişler ekler.

```cpp
void AddTransition(
    CBaseTransition* pRTransition,
    CBaseTransition* pGTransition,
    CBaseTransition* pBTransition);
```

### <a name="parameters"></a>Parametreler

*pRTransition*<br/>
Red bileşen geçişi.

*pGTransition*<br/>
Yeşil bileşen için geçiş.

*pBTransition*<br/>
Mavi bileşen için geçiş.

### <a name="remarks"></a>Açıklamalar

Renk bileşenlerini temsil eden animasyon değişkenlerine uygulanacak olan geçiş iç listesine belirtilen geçişleri eklemek için bu işlevi çağırın. Geçişler eklediğinizde, bunlar hemen uygulanmaz ve dahili bir listede depolanır. CAnimationController:: AnimateGroup ' i çağırdığınızda geçişler uygulanır (belirli bir değer için bir görsel taslağa eklenir). Renk bileşenlerinden birine geçiş uygulamanız gerekmiyorsa NULL geçirebilirsiniz.

## <a name="canimationcolorcanimationcolor"></a><a name="canimationcolor"></a> CAnimationColor:: CAnimationColor

Bir CAnimationColor nesnesi oluşturur.

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
Varsayılan rengi belirtir.

*Ngroupıd*<br/>
Grup KIMLIĞINI belirtir.

*Nobjectıd*<br/>
Nesne KIMLIĞINI belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı verileri belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne, 0 olarak ayarlanacak kırmızı, yeşil, mavi, nesne KIMLIĞI ve Grup KIMLIĞI için varsayılan değerlerle oluşturulur. Bu, daha sonra SetDefaultValue ve SetID kullanılarak çalışma zamanında değiştirilebilir.

## <a name="canimationcolorgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationColor:: GetAnimationVariableList

Encapsulated animasyon değişkenlerini bir listeye koyar.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*LST*<br/>
İşlev döndüğünde, kırmızı, yeşil ve mavi bileşenleri temsil eden üç CAnimationVariable nesnesine işaretçiler içerir.

## <a name="canimationcolorgetb"></a><a name="getb"></a> CAnimationColor:: GetB

Mavi bileşeni temsil eden CAnimationVariable öğesine erişim sağlar.

```
CAnimationVariable& GetB();
```

### <a name="return-value"></a>Dönüş Değeri

Mavi bileşeni temsil eden kapsüllenmiş CAnimationVariable başvurusu.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, mavi bileşeni temsil eden temeldeki CAnimationVariable öğesine doğrudan erişim almak için çağırabilirsiniz.

## <a name="canimationcolorgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationColor:: GetDefaultValue

Renk bileşenleri için varsayılan değerleri döndürür.

```
COLORREF GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

RGB bileşenleri için varsayılan değerleri içeren bir COLORREF değeri.

### <a name="remarks"></a>Açıklamalar

Daha önce constructor veya SetDefaultValue tarafından ayarlanan varsayılan değeri almak için bu işlevi çağırın.

## <a name="canimationcolorgetg"></a><a name="getg"></a> CAnimationColor:: GetG

Yeşil bileşeni temsil eden CAnimationVariable öğesine erişim sağlar.

```
CAnimationVariable& GetG();
```

### <a name="return-value"></a>Dönüş Değeri

Yeşil bileşeni temsil eden kapsüllenmiş CAnimationVariable başvurusu.

### <a name="remarks"></a>Açıklamalar

Yeşil bileşeni temsil eden temeldeki CAnimationVariable öğesine doğrudan erişim sağlamak için bu yöntemi çağırabilirsiniz.

## <a name="canimationcolorgetr"></a><a name="getr"></a> CAnimationColor:: GetR

Red bileşenini temsil eden CAnimationVariable öğesine erişim sağlar.

```
CAnimationVariable& GetR();
```

### <a name="return-value"></a>Dönüş Değeri

Kırmızı bileşeni temsil eden kapsüllenmiş CAnimationVariable başvurusu.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, Red bileşenini temsil eden temeldeki CAnimationVariable öğesine doğrudan erişim almak için çağırabilirsiniz.

## <a name="canimationcolorgetvalue"></a><a name="getvalue"></a> CAnimationColor:: GetValue

Geçerli değeri döndürür.

```
BOOL GetValue(COLORREF& color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
Çıktıların. Bu yöntemin döndürdüğü geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer başarıyla alınırsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Animasyon renginin geçerli değerini almak için bu işlevi çağırın. Bu yöntem başarısız olursa veya renk bileşenleri için temel alınan COM nesneleri başlatılmazsa, Color daha önce oluşturucuda veya SetDefaultValue tarafından ayarlanan varsayılan değeri içerir.

## <a name="canimationcolorm_bvalue"></a><a name="m_bvalue"></a> CAnimationColor:: m_bValue

Animasyon renginin mavi bileşenini temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_bValue;
```

## <a name="canimationcolorm_gvalue"></a><a name="m_gvalue"></a> CAnimationColor:: m_gValue

Animasyon renginin Yeşil bileşenini temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_gValue;
```

## <a name="canimationcolorm_rvalue"></a><a name="m_rvalue"></a> CAnimationColor:: m_rValue

Animasyon renginin kırmızı bileşenini temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_rValue;
```

## <a name="canimationcoloroperator-colorref"></a><a name="operator_colorref"></a> CAnimationColor:: operator COLORREF

```
operator COLORREF();
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="canimationcoloroperator"></a><a name="operator_eq"></a> CAnimationColor:: operator =

CAnimationColor 'e renk atar.

```cpp
void operator=(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
Yeni değer animasyon rengini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işleç, oluşturulduklarında renk bileşenleri için temel alınan COM nesnelerini yeniden oluşturan SetDefaultValue ' ı çağırdığı için, animasyon başlamadan önce bunu yapmanız önerilir. Bu animasyon nesnesini olaylara abone oldıysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="canimationcolorsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationColor:: SetDefaultValue

Varsayılan değeri ayarlar.

```cpp
void SetDefaultValue(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
Kırmızı, yeşil ve mavi bileşenler için yeni varsayılan değerleri belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine varsayılan bir değer ayarlamak için bu işlevi kullanın. Bu yöntemler, animasyon renginin renk bileşenlerine varsayılan değerler atar. Ayrıca, oluşturulan temel COM nesnelerini de yeniden oluşturur. Bu animasyon nesnesini olaylara abone oldıysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
