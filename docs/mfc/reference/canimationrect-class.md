---
title: CAnimationRect Sınıfı
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
ms.openlocfilehash: 273ea2b548d35722ebf937d2db2b589fef5e69fa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755129"
---
# <a name="canimationrect-class"></a>CAnimationRect Sınıfı

Kenarları animasyonlu olabilecek bir dikdörtgenin işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationRect : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationRect::CAnimationRect](#canimationrect)|Fazla Yüklendi. Animasyon dikdörtgen nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationRect::Ekle Geçiş](#addtransition)|Sol, üst, sağ ve alt koordinatlar için geçişler ekler.|
|[CAnimationRect::GetBottom](#getbottom)|Alt koordinatı temsil eden CAnimationVariable'e erişim sağlar.|
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|Dikdörtgenin sınırları için varsayılan değerleri döndürür.|
|[CAnimationRect::GetLeft](#getleft)|Sol koordinatı temsil eden CAnimationVariable'e erişim sağlar.|
|[CAnimationRect::GetRight](#getright)|Doğru koordinatı temsil eden CAnimationVariable'e erişim sağlar.|
|[CAnimationRect::GetTop](#gettop)|Üst koordinatı temsil eden CAnimationVariable'e erişim sağlar.|
|[CAnimationRect::GetValue](#getvalue)|Geçerli değeri verir.|
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenlerini bir listeye koyar. [(CAnimationBaseObject geçersiz kılar::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationRect::operatör RECT](#operator_rect)|CAnimationRect'i RECT'ye dönüştürür.|
|[CAnimationRect::operator=](#operator_eq)|CAnimationRect'e rect atar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|Dikdörtgenin sabit boyutu olup olmadığını belirtir.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|Animasyon dikdörtgeninalt ciltli temsil eden kapsüllü animasyon değişkeni.|
|[CAnimationRect::m_leftValue](#m_leftvalue)|Animasyon dikdörtgeninin Sol bağlı'sını temsil eden kapsüllü animasyon değişkeni.|
|[CAnimationRect::m_rightValue](#m_rightvalue)|Animasyon dikdörtgeninin Sağ kenarını temsil eden kapsüllü animasyon değişkeni.|
|[CAnimationRect::m_szInitial](#m_szinitial)|Animasyon dikdörtgeninin ilk boyutunu belirtir.|
|[CAnimationRect::m_topValue](#m_topvalue)|Animasyon dikdörtgeninin üst temasını temsil eden kapsüllü animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationRect sınıfı dört CAnimationVariable nesnesini kapsüller ve uygulamalarda bir dikdörtgeni temsil edebilir. Uygulamada bu sınıfı kullanmak için, bu sınıfın bir nesnesini anlık olarak eklemeniz, CAnimationController'ı kullanarak animasyon denetleyicisine ekleyin::AddAnimationObject ve sol, sağ üst ve alt koordinatlara uygulanacak her geçiş için AddTransition'ı arayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationrectaddtransition"></a><a name="addtransition"></a>CAnimationRect::Ekle Geçiş

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
Sol taraf için geçişi belirtir.

*pTopTransition*<br/>
Üst taraf için geçişi belirtir.

*pRightTransition*<br/>
Sağ taraf için geçişi belirtir.

*pBottomTransition*<br/>
Alt taraf için geçişi belirtir.

### <a name="remarks"></a>Açıklamalar

Her dikdörtgen taraf için animasyon değişkenlerine uygulanacak iç geçişler listesine belirtilen geçişleri eklemek için bu işlevi arayın. Geçişler eklediğinizde, bunlar hemen uygulanmaz ve dahili bir listede depolanır. Geçişler CAnimationController::AnimateGroup'u aradiğinizde uygulanır (belirli bir değer için bir film şeridine eklenir). Dikdörtgen kenarlarından birine geçiş uygulamanız gerekmiyorsa, NULL'u geçebilirsiniz.

## <a name="canimationrectcanimationrect"></a><a name="canimationrect"></a>CAnimationRect::CAnimationRect

CAnimationRect nesnesi oluşturuyor.

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

*nGroupID*<br/>
Grup Kimliğini belirtir.

*nObjectID*<br/>
Nesne Kimliğini belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı verileri belirtir.

*Pt*<br/>
Sol üst köşenin koordinatı.

*Sz*<br/>
Dikdörtgenin boyutu.

*nLeft*<br/>
Sol bağlının koordinatını belirtir.

*nTop*<br/>
Üst sınır koordinatını belirtir.

*nHakkı*<br/>
Doğru bağlı koordinatı belirtir.

*nBottom*<br/>
Alt sınır koordinatını belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne, sol, üst, sağ ve alt, Nesne Kimliği ve Grup Kimliği için varsayılan değerlerle oluşturulur ve bu değerler 0 olarak ayarlanır. Bunlar daha sonra setdefaultvalue ve SetID kullanılarak çalışma zamanında değiştirilebilir.

## <a name="canimationrectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationRect::GetAnimationVariableList

Kapsüllenmiş animasyon değişkenlerini bir listeye koyar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*Lst*<br/>
İşlev döndüğünde, dikdörtgenin koordinatlarını temsil eden dört CAnimationVariable nesnesine işaretçiler içerir.

## <a name="canimationrectgetbottom"></a><a name="getbottom"></a>CAnimationRect::GetBottom

Alt koordinatı temsil eden CAnimationVariable'e erişim sağlar.

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>Dönüş Değeri

Alt koordinatı temsil eden kapsüllü CAnimationVariable'e bir başvuru.

### <a name="remarks"></a>Açıklamalar

Alt koordinatı temsil eden altta yatan CAnimationVariable'e doğrudan erişim elde etmek için bu yöntemi arayabilirsiniz.

## <a name="canimationrectgetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationRect::GetDefaultValue

Dikdörtgenin sınırları için varsayılan değerleri döndürür.

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

Sol, sağ, üst ve alt için varsayılanları içeren bir CRect değeri.

### <a name="remarks"></a>Açıklamalar

Daha önce oluşturucu veya SetDefaultValue tarafından ayarlanmış varsayılan değeri almak için bu işlevi arayın.

## <a name="canimationrectgetleft"></a><a name="getleft"></a>CAnimationRect::GetLeft

Sol koordinatı temsil eden CAnimationVariable'e erişim sağlar.

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>Dönüş Değeri

Sol koordinatı temsil eden kapsüllü CAnimationVariable'e bir başvuru.

### <a name="remarks"></a>Açıklamalar

Sol koordinatı temsil eden altta yatan CAnimationVariable'e doğrudan erişim elde etmek için bu yöntemi arayabilirsiniz.

## <a name="canimationrectgetright"></a><a name="getright"></a>CAnimationRect::GetRight

Doğru koordinatı temsil eden CAnimationVariable'e erişim sağlar.

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>Dönüş Değeri

Sağ koordinatı temsil eden kapsüllü CAnimationVariable'e bir başvuru.

### <a name="remarks"></a>Açıklamalar

Doğru koordinatı temsil eden altta yatan CAnimationVariable'e doğrudan erişim elde etmek için bu yöntemi arayabilirsiniz.

## <a name="canimationrectgettop"></a><a name="gettop"></a>CAnimationRect::GetTop

Üst koordinatı temsil eden CAnimationVariable'e erişim sağlar.

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>Dönüş Değeri

Üst koordinatı temsil eden kapsüllü CAnimationVariable'e bir başvuru.

### <a name="remarks"></a>Açıklamalar

Üst koordinatı temsil eden altta yatan CAnimationVariable'e doğrudan erişim elde etmek için bu yöntemi arayabilirsiniz.

## <a name="canimationrectgetvalue"></a><a name="getvalue"></a>CAnimationRect::GetValue

Geçerli değeri verir.

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Çıkış. Bu yöntem döndüğünde geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU, geçerli değer başarıyla alındıysa; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Animasyon dikdörtgeninin geçerli değerini almak için bu işlevi arayın. Bu yöntem başarısız olursa veya sol, üst, sağ ve alt için COM nesneleri başharfe edilmemişse, rect daha önce oluşturucu veya SetDefaultValue tarafından ayarlanmış varsayılan değer içerir.

## <a name="canimationrectm_bfixedsize"></a><a name="m_bfixedsize"></a>CAnimationRect::m_bFixedSize

Dikdörtgenin sabit boyutu olup olmadığını belirtir.

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>Açıklamalar

Bu üye doğruysa, dikdörtgenin boyutu sabitlenir ve sağ ve alt değerler her sol üst köşe sabit boyuta göre hareket ettirildiğinde yeniden hesaplanır. Dikdörtgeni ekranın etrafında kolayca taşımak için bu değeri TRUE olarak ayarlayın. Bu durumda sağ ve alt koordinatlara uygulanan geçişler yoksayılır. Nesneyi ve/veya SetDefaultValue'ı yaptığınızda boyut dahili olarak depolanır. Varsayılan olarak bu üye FALSE olarak ayarlanır.

## <a name="canimationrectm_bottomvalue"></a><a name="m_bottomvalue"></a>CAnimationRect::m_bottomValue

Animasyon dikdörtgeninalt ciltli temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_bottomValue;
```

## <a name="canimationrectm_leftvalue"></a><a name="m_leftvalue"></a>CAnimationRect::m_leftValue

Animasyon dikdörtgeninin Sol bağlı'sını temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_leftValue;
```

## <a name="canimationrectm_rightvalue"></a><a name="m_rightvalue"></a>CAnimationRect::m_rightValue

Animasyon dikdörtgeninin Sağ kenarını temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_rightValue;
```

## <a name="canimationrectm_szinitial"></a><a name="m_szinitial"></a>CAnimationRect::m_szInitial

Animasyon dikdörtgeninin ilk boyutunu belirtir.

```
CSize m_szInitial;
```

## <a name="canimationrectm_topvalue"></a><a name="m_topvalue"></a>CAnimationRect::m_topValue

Animasyon dikdörtgeninin üst temasını temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_topValue;
```

## <a name="canimationrectoperator-rect"></a><a name="operator_rect"></a>CAnimationRect::operatör RECT

CAnimationRect'i RECT'ye dönüştürür.

```
operator RECT();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon dikdörtgeninin RECT olarak geçerli değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev dahili olarak GetValue çağırır. GetValue herhangi bir nedenle başarısız olursa, döndürülen RECT tüm dikdörtgen koordinatları için varsayılan değerleri içerir.

## <a name="canimationrectoperator"></a><a name="operator_eq"></a>CAnimationRect::operator=

CAnimationRect'e rect atar.

```cpp
void operator=(const RECT& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Animasyon dikdörtgeninin yeni değeri.

### <a name="remarks"></a>Açıklamalar

Animasyon başlamadan önce bunu yapmanız önerilir, çünkü bu işleç, oluşturulduklarında renk bileşenleri için temel COM nesnelerini yeniden oluşturan SetDefaultValue'ı çağırır. Bu animasyon nesnesini olaylara abone olduysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="canimationrectsetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationRect::SetDefaultValue

Varsayılan değeri ayarlar.

```cpp
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>Parametreler

*Rect*<br/>
Sol, üst, sağ ve alt için yeni varsayılan değerleri belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine varsayılan değer ayarlamak için bu işlevi kullanın. Bu yöntem, varsayılan değerleri dikdörtgenin sınırlarına atar. Ayrıca, oluşturuldukları takdirde altta yatan COM nesnelerini yeniden oluşturur. Bu animasyon nesnesini olaylara abone olduysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
