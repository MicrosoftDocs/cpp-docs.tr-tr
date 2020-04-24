---
title: CAnimationSize Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
ms.openlocfilehash: 1f4a5b8b52d8bd37d1ed83618e7451dd85f84c32
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755122"
---
# <a name="canimationsize-class"></a>CAnimationSize Sınıfı

Boyutları canlandırılabilen bir boyut nesnesinin işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationSize : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CanimationSize::CanimationSize](#canimationsize)|Fazla Yüklendi. Animasyon boyutu nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CanimasyonBoyutu::Ekle Geçişi](#addtransition)|Genişlik ve Yükseklik için geçişler ekler.|
|[CAnimationSize::GetCX](#getcx)|Genişliği temsil eden CAnimationVariable'e erişim sağlar.|
|[CAnimationSize::GetCY](#getcy)|Yüksekliği temsil eden CAnimationVariable'e erişim sağlar.|
|[CanimasyonBoyutu::Varsayılan Değeri Al](#getdefaultvalue)|Genişlik ve Yükseklik için varsayılan değerleri döndürür.|
|[CAnimationSize::GetValue](#getvalue)|Geçerli değeri verir.|
|[CanimasyonBoyutu::SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenlerini bir listeye koyar. [(CAnimationBaseObject geçersiz kılar::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationSize::operatör CSize](#operator_csize)|CAnimationSize'ı CSize'a dönüştürür.|
|[CAnimationSize::operator=](#operator_eq)|CAnimationSize için szSrc atar.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAnimationSize::m_cxValue](#m_cxvalue)|Animasyon boyutunun genişliğini temsil eden kapsüllü animasyon değişkeni.|
|[CAnimationSize::m_cyValue](#m_cyvalue)|Animasyon boyutunun yüksekliğini temsil eden kapsüllü animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationSize sınıfı iki CAnimationVariable nesnesini kapsüller ve uygulamalarda bir boyutu temsil edebilir. Örneğin, ekrandaki herhangi iki boyutlu bir nesnenin boyutunu (dikdörtgen, denetim vb. gibi) canlandırmak için bu sınıfı kullanabilirsiniz. Uygulamada bu sınıfı kullanmak için, bu sınıfın bir nesnesini anlık olarak eklemeniz, CAnimationController'ı kullanarak animasyon denetleyicisine ekleyin::AddAnimationObject ve Genişlik ve/veya Yükseklik'e uygulanacak her geçiş için AddTransition'ı arayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller.h

## <a name="canimationsizeaddtransition"></a><a name="addtransition"></a>CanimasyonBoyutu::Ekle Geçişi

Genişlik ve Yükseklik için geçişler ekler.

```cpp
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>Parametreler

*pCXTransition*<br/>
Genişlik için geçiş için bir işaretçi.

*pCYTransition*<br/>
Yükseklik için geçiş için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Genişlik ve Yükseklik için animasyon değişkenlerine uygulanacak iç geçişler listesine belirtilen geçişleri eklemek için bu işlevi arayın. Geçişler eklediğinizde, bunlar hemen uygulanmaz ve dahili bir listede depolanır. Geçişler CAnimationController::AnimateGroup'u aradiğinizde uygulanır (belirli bir değer için bir film şeridine eklenir). Boyutlardan birine geçiş uygulamanız gerekmiyorsa, NULL'u geçebilirsiniz.

## <a name="canimationsizecanimationsize"></a><a name="canimationsize"></a>CanimationSize::CanimationSize

Animasyon boyutu nesnesi oluşturuyor.

```
CAnimationSize();

CAnimationSize(
    const CSize& szDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*szVarsayılan*<br/>
Varsayılan boyutu belirtir.

*nGroupID*<br/>
Grup Kimliğini belirtir.

*nObjectID*<br/>
Nesne Kimliğini belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı verileri belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne, 0 olarak ayarlanacak genişlik, yükseklik, Nesne Kimliği ve Grup Kimliği için varsayılan değerlerle oluşturulur. Bunlar daha sonra setdefaultvalue ve SetID kullanılarak çalışma zamanında değiştirilebilir.

## <a name="canimationsizegetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationSize::GetAnimationVariableList

Kapsüllenmiş animasyon değişkenlerini bir listeye koyar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*Lst*<br/>
İşlev döndüğünde, genişlik ve yüksekliği temsil eden iki CAnimationVariable nesnelerine işaretçiler içerir.

## <a name="canimationsizegetcx"></a><a name="getcx"></a>CAnimationSize::GetCX

Genişliği temsil eden CAnimationVariable'e erişim sağlar.

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>Dönüş Değeri

Genişliği temsil eden kapsüllü CAnimationVariable'e bir başvuru.

### <a name="remarks"></a>Açıklamalar

Genişlik temsil eden temel CAnimationVariable doğrudan erişim elde etmek için bu yöntemi arayabilirsiniz.

## <a name="canimationsizegetcy"></a><a name="getcy"></a>CAnimationSize::GetCY

Yüksekliği temsil eden CAnimationVariable'e erişim sağlar.

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>Dönüş Değeri

Yüksekliği temsil eden kapsüllü CAnimationVariable'e bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yükseklik'i temsil eden temel CAnimationVariable'e doğrudan erişim elde etmek için bu yöntemi arayabilirsiniz.

## <a name="canimationsizegetdefaultvalue"></a><a name="getdefaultvalue"></a>CanimasyonBoyutu::Varsayılan Değeri Al

Genişlik ve Yükseklik için varsayılan değerleri döndürür.

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan değerleri içeren bir CSize nesnesi.

### <a name="remarks"></a>Açıklamalar

Daha önce oluşturucu veya SetDefaultValue tarafından ayarlanmış varsayılan değeri almak için bu işlevi arayın.

## <a name="canimationsizegetvalue"></a><a name="getvalue"></a>CAnimationSize::GetValue

Geçerli değeri verir.

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>Parametreler

*szDeğer*<br/>
Çıkış. Bu yöntem döndüğünde geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU, geçerli değer başarıyla alındıysa; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Animasyon boyutunun geçerli değerini almak için bu işlevi arayın. Bu yöntem başarısız olursa veya Genişlik ve Boyut için COM nesneleri temele atılmıştır, szValue daha önce oluşturucu veya SetDefaultValue tarafından ayarlanmış varsayılan değer içerir.

## <a name="canimationsizem_cxvalue"></a><a name="m_cxvalue"></a>CAnimationSize::m_cxValue

Animasyon boyutunun genişliğini temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_cxValue;
```

## <a name="canimationsizem_cyvalue"></a><a name="m_cyvalue"></a>CAnimationSize::m_cyValue

Animasyon boyutunun yüksekliğini temsil eden kapsüllü animasyon değişkeni.

```
CAnimationVariable m_cyValue;
```

## <a name="canimationsizeoperator-csize"></a><a name="operator_csize"></a>CAnimationSize::operatör CSize

CAnimationSize'ı CSize'a dönüştürür.

```
operator CSize();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon boyutunun CSize olarak geçerli değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev dahili olarak GetValue çağırır. GetValue herhangi bir nedenle başarısız olursa, döndürülen boyut Genişlik ve Yükseklik için varsayılan değerleri içerir.

## <a name="canimationsizeoperator"></a><a name="operator_eq"></a>CAnimationSize::operator=

CAnimationSize için szSrc atar.

```cpp
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>Parametreler

*szSrc*<br/>
CSize veya SIZE anlamına gelir.

### <a name="remarks"></a>Açıklamalar

CAnimationSize için szSrc atar. Animasyon başlamadan önce bunu yapmanız önerilir, çünkü bu işleç, temel COM nesnelerini oluşturulduklarında Genişlik ve Yükseklik için yeniden oluşturan SetDefaultValue'ı çağırır. Bu animasyon nesnesini olaylara abone olduysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="canimationsizesetdefaultvalue"></a><a name="setdefaultvalue"></a>CanimasyonBoyutu::SetDefaultValue

Varsayılan değeri ayarlar.

```cpp
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>Parametreler

*szVarsayılan*<br/>
Yeni varsayılan boyutu belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine varsayılan değer ayarlamak için bu işlevi kullanın. Bu yöntem, varsayılan değerleri animasyon boyutunun Genişliği ve Yüksekliği'ne atar. Ayrıca, oluşturuldukları takdirde altta yatan COM nesnelerini yeniden oluşturur. Bu animasyon nesnesini olaylara abone olduysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
