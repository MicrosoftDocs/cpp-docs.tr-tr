---
description: 'Daha fazla bilgi edinin: CAnimationRect sınıfı'
title: CAnimationRect sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 590b1382992a32e0eb3d49e0ea562d10193c1990
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207897"
---
# <a name="canimationrect-class"></a>CAnimationRect sınıfı

Kenarları animasyonlu olabilecek bir dikdörtgenin işlevlerini uygular.

## <a name="syntax"></a>Syntax

```
class CAnimationRect : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationRect:: CAnimationRect](#canimationrect)|Fazla Yüklendi. Bir animasyon Rect nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationRect:: AddTransition](#addtransition)|Sol, üst, sağ ve alt koordinatlar için geçişler ekler.|
|[CAnimationRect:: GetBottom](#getbottom)|Alt koordinatı temsil eden CAnimationVariable öğesine erişim sağlar.|
|[CAnimationRect:: GetDefaultValue](#getdefaultvalue)|Dikdörtgenin sınırları için varsayılan değerleri döndürür.|
|[CAnimationRect:: GetLeft](#getleft)|Sol koordinatı temsil eden CAnimationVariable öğesine erişim sağlar.|
|[CAnimationRect:: GetRight](#getright)|Doğru koordinatı temsil eden CAnimationVariable öğesine erişim sağlar.|
|[CAnimationRect:: GetTop](#gettop)|En üstteki koordinatı temsil eden CAnimationVariable öğesine erişim sağlar.|
|[CAnimationRect:: GetValue](#getvalue)|Geçerli değeri döndürür.|
|[CAnimationRect:: SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationRect:: GetAnimationVariableList](#getanimationvariablelist)|Encapsulated animasyon değişkenlerini bir listeye koyar. ( [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)geçersiz kılınır.)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationRect:: operator RECT](#operator_rect)|CAnimationRect 'i RECT 'e dönüştürür.|
|[CAnimationRect:: operator =](#operator_eq)|CAnimationRect 'e rect atar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationRect:: m_bFixedSize](#m_bfixedsize)|Dikdörtgenin sabit boyutta olup olmadığını belirtir.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationRect:: m_bottomValue](#m_bottomvalue)|Animasyon dikdörtgeninin alt sınırını temsil eden Encapsulated animasyon değişkeni.|
|[CAnimationRect:: m_leftValue](#m_leftvalue)|Animasyon dikdörtgeninin sol sınırını temsil eden Encapsulated animasyon değişkeni.|
|[CAnimationRect:: m_rightValue](#m_rightvalue)|Animasyon dikdörtgeninin sağ ilişkisini temsil eden Encapsulated animasyon değişkeni.|
|[CAnimationRect:: m_szInitial](#m_szinitial)|Animasyon dikdörtgeninin başlangıçtaki boyutunu belirtir.|
|[CAnimationRect:: m_topValue](#m_topvalue)|Animasyon dikdörtgeninin üst sınırını temsil eden Encapsulated animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationRect sınıfı dört CAnimationVariable nesnesini kapsüller ve uygulamalarda bir dikdörtgeni temsil edebilir. Bu sınıfı uygulamada kullanmak için, bu sınıfın bir nesnesinin örneğini oluşturun, CAnimationController:: AddAnimationObject öğesini kullanarak animasyon denetleyicisine ekleyin ve sol, sağ üst ve alt koordinatlara uygulanacak her geçiş için AddTransition çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationrectaddtransition"></a><a name="addtransition"></a> CAnimationRect:: AddTransition

Sol, üst, sağ ve alt koordinatlar için geçişler ekler.

```cpp
void AddTransition(
    CBaseTransition* pLeftTransition,
    CBaseTransition* pTopTransition,
    CBaseTransition* pRightTransition,
    CBaseTransition* pBottomTransition);
```

### <a name="parameters"></a>Parametreler

*pLeftTransition*<br/>
Sol kenar için geçişi belirtir.

*pTopTransition*<br/>
Üst kenar için geçişi belirtir.

*Prime geçişi*<br/>
Sağ kenar için geçişi belirtir.

*pBottomTransition*<br/>
Alt kenar için geçişi belirtir.

### <a name="remarks"></a>Açıklamalar

Her dikdörtgen kenarı için animasyon değişkenlerine uygulanacak olan geçiş iç listesine belirtilen geçişleri eklemek için bu işlevi çağırın. Geçişler eklediğinizde, bunlar hemen uygulanmaz ve dahili bir listede depolanır. CAnimationController:: AnimateGroup ' i çağırdığınızda geçişler uygulanır (belirli bir değer için bir görsel taslağa eklenir). Dikdörtgen kenarlarından birine geçiş uygulamanız gerekmiyorsa NULL geçirebilirsiniz.

## <a name="canimationrectcanimationrect"></a><a name="canimationrect"></a> CAnimationRect:: CAnimationRect

CAnimationRect nesnesi oluşturur.

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
Varsayılan dikdörtgeni belirtir.

*Ngroupıd*<br/>
Grup KIMLIĞINI belirtir.

*Nobjectıd*<br/>
Nesne KIMLIĞINI belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı verileri belirtir.

*yönergelerinin*<br/>
Sol üst köşenin koordinatı.

*SZ*<br/>
Dikdörtgenin boyutu.

*nLeft*<br/>
Sol sınırın koordinatını belirtir.

*nTop*<br/>
En üst sınırın koordinatını belirtir.

*Nsağ*<br/>
Sağ sınırın koordinatını belirtir.

*nBottom*<br/>
Alt sınırın koordinatını belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne, sol, üst, sağ ve alt, nesne KIMLIĞI ve Grup KIMLIĞI için varsayılan değerlerle oluşturulur ve bu değer 0 olarak ayarlanır. Bu, daha sonra SetDefaultValue ve SetID kullanılarak çalışma zamanında değiştirilebilir.

## <a name="canimationrectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationRect:: GetAnimationVariableList

Encapsulated animasyon değişkenlerini bir listeye koyar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*LST*<br/>
İşlev döndüğünde, dikdörtgenin koordinatlarını temsil eden dört CAnimationVariable nesnesine işaretçiler içerir.

## <a name="canimationrectgetbottom"></a><a name="getbottom"></a> CAnimationRect:: GetBottom

Alt koordinatı temsil eden CAnimationVariable öğesine erişim sağlar.

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>Dönüş Değeri

Alt koordinatı temsil eden kapsüllenmiş CAnimationVariable başvurusu.

### <a name="remarks"></a>Açıklamalar

Alt koordinatı temsil eden temeldeki CAnimationVariable öğesine doğrudan erişim sağlamak için bu yöntemi çağırabilirsiniz.

## <a name="canimationrectgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationRect:: GetDefaultValue

Dikdörtgenin sınırları için varsayılan değerleri döndürür.

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

Sol, sağ, üst ve alt değerlerini içeren bir CRect değeri.

### <a name="remarks"></a>Açıklamalar

Daha önce constructor veya SetDefaultValue tarafından ayarlanan varsayılan değeri almak için bu işlevi çağırın.

## <a name="canimationrectgetleft"></a><a name="getleft"></a> CAnimationRect:: GetLeft

Sol koordinatı temsil eden CAnimationVariable öğesine erişim sağlar.

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>Dönüş Değeri

Sol koordinatı temsil eden kapsüllenmiş CAnimationVariable başvurusu.

### <a name="remarks"></a>Açıklamalar

Sol koordinatı temsil eden temeldeki CAnimationVariable öğesine doğrudan erişim sağlamak için bu yöntemi çağırabilirsiniz.

## <a name="canimationrectgetright"></a><a name="getright"></a> CAnimationRect:: GetRight

Doğru koordinatı temsil eden CAnimationVariable öğesine erişim sağlar.

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>Dönüş Değeri

Doğru koordinatı temsil eden kapsüllenmiş CAnimationVariable başvurusu.

### <a name="remarks"></a>Açıklamalar

Doğru koordinatı temsil eden temeldeki CAnimationVariable 'a doğrudan erişim sağlamak için bu yöntemi çağırabilirsiniz.

## <a name="canimationrectgettop"></a><a name="gettop"></a> CAnimationRect:: GetTop

En üstteki koordinatı temsil eden CAnimationVariable öğesine erişim sağlar.

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>Dönüş Değeri

En üst koordinatları temsil eden kapsüllenmiş CAnimationVariable başvurusu.

### <a name="remarks"></a>Açıklamalar

En üstteki koordinatı temsil eden temeldeki CAnimationVariable 'a doğrudan erişim sağlamak için bu yöntemi çağırabilirsiniz.

## <a name="canimationrectgetvalue"></a><a name="getvalue"></a> CAnimationRect:: GetValue

Geçerli değeri döndürür.

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Çıktıların. Bu yöntemin döndürdüğü geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer başarıyla alınırsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Animasyon dikdörtgeninin geçerli değerini almak için bu işlevi çağırın. Bu yöntem başarısız olursa veya sol, üst, sağ ve alt için COM nesneleri başlatılmazsa, Rect, daha önce oluşturucuda veya SetDefaultValue tarafından ayarlanan varsayılan değeri içerir.

## <a name="canimationrectm_bfixedsize"></a><a name="m_bfixedsize"></a> CAnimationRect:: m_bFixedSize

Dikdörtgenin sabit boyutta olup olmadığını belirtir.

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>Açıklamalar

Bu üye doğru ise, sol üst köşedeki sabit boyuta göre her taşınışında dikdörtgenin boyutu sabittir ve sağ ve alt değerler yeniden hesaplanır. Dikdörtgeni ekranın etrafında kolayca taşımak için bu değeri TRUE olarak ayarlayın. Bu durumda, sağ ve alt koordinatlarına uygulanan geçişler yok sayılır. Nesne oluşturduğunuzda ve/veya SetDefaultValue ' i çağırdığınızda boyut dahili olarak depolanır. Varsayılan olarak, bu üye FALSE olarak ayarlanır.

## <a name="canimationrectm_bottomvalue"></a><a name="m_bottomvalue"></a> CAnimationRect:: m_bottomValue

Animasyon dikdörtgeninin alt sınırını temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_bottomValue;
```

## <a name="canimationrectm_leftvalue"></a><a name="m_leftvalue"></a> CAnimationRect:: m_leftValue

Animasyon dikdörtgeninin sol sınırını temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_leftValue;
```

## <a name="canimationrectm_rightvalue"></a><a name="m_rightvalue"></a> CAnimationRect:: m_rightValue

Animasyon dikdörtgeninin sağ ilişkisini temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_rightValue;
```

## <a name="canimationrectm_szinitial"></a><a name="m_szinitial"></a> CAnimationRect:: m_szInitial

Animasyon dikdörtgeninin başlangıçtaki boyutunu belirtir.

```
CSize m_szInitial;
```

## <a name="canimationrectm_topvalue"></a><a name="m_topvalue"></a> CAnimationRect:: m_topValue

Animasyon dikdörtgeninin üst sınırını temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_topValue;
```

## <a name="canimationrectoperator-rect"></a><a name="operator_rect"></a> CAnimationRect:: operator RECT

CAnimationRect 'i RECT 'e dönüştürür.

```
operator RECT();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon dikdörtgeninin geçerli değeri DIKDÖRTGEN olarak.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir dahili olarak GetValue çağırır. GetValue bir nedenden dolayı başarısız olursa, döndürülen RECT tüm dikdörtgen koordinatları için varsayılan değerleri içerir.

## <a name="canimationrectoperator"></a><a name="operator_eq"></a> CAnimationRect:: operator =

CAnimationRect 'e rect atar.

```cpp
void operator=(const RECT& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Animasyon dikdörtgeninin yeni değeri.

### <a name="remarks"></a>Açıklamalar

Bu işleç, oluşturulduklarında renk bileşenleri için temel alınan COM nesnelerini yeniden oluşturan SetDefaultValue ' ı çağırdığı için, animasyon başlamadan önce bunu yapmanız önerilir. Bu animasyon nesnesini olaylara abone oldıysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="canimationrectsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationRect:: SetDefaultValue

Varsayılan değeri ayarlar.

```cpp
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Sol, üst, sağ ve alt için yeni varsayılan değerleri belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine varsayılan bir değer ayarlamak için bu işlevi kullanın. Bu yöntemler, dikdörtgenin sınırlarına varsayılan değerler atar. Ayrıca, oluşturulan temel COM nesnelerini de yeniden oluşturur. Bu animasyon nesnesini olaylara abone oldıysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
