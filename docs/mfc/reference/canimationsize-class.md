---
description: 'Daha fazla bilgi edinin: CAnimationSize sınıfı'
title: CAnimationSize sınıfı
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
ms.openlocfilehash: 894675c485077291c3fca35acfb9bfa9a3d10286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336768"
---
# <a name="canimationsize-class"></a>CAnimationSize sınıfı

Boyutları animasyon uygulanabilir olan bir boyut nesnesi işlevselliğini uygular.

## <a name="syntax"></a>Syntax

```
class CAnimationSize : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationSize:: CAnimationSize](#canimationsize)|Fazla Yüklendi. Bir animasyon boyutu nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationSize:: AddTransition](#addtransition)|Genişlik ve yükseklik için geçişler ekler.|
|[CAnimationSize:: GetCX](#getcx)|Genişliği temsil eden CAnimationVariable öğesine erişim sağlar.|
|[CAnimationSize:: GetCY](#getcy)|Yüksekliği temsil eden CAnimationVariable öğesine erişim sağlar.|
|[CAnimationSize:: GetDefaultValue](#getdefaultvalue)|Genişlik ve yükseklik için varsayılan değerleri döndürür.|
|[CAnimationSize:: GetValue](#getvalue)|Geçerli değeri döndürür.|
|[CAnimationSize:: SetDefaultValue](#setdefaultvalue)|Varsayılan değeri ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationSize:: GetAnimationVariableList](#getanimationvariablelist)|Encapsulated animasyon değişkenlerini bir listeye koyar. ( [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)geçersiz kılınır.)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationSize:: işleç CSize](#operator_csize)|CAnimationSize boyutunu CSize dönüştürür.|
|[CAnimationSize:: operator =](#operator_eq)|SzSrc 'yi CAnimationSize atar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationSize:: m_cxValue](#m_cxvalue)|Animasyon boyutunun genişliğini temsil eden Encapsulated animasyon değişkeni.|
|[CAnimationSize:: m_cyValue](#m_cyvalue)|Animasyon boyutunun yüksekliğini temsil eden Encapsulated animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationSize sınıfı iki CAnimationVariable nesnesini kapsüller ve uygulamalarda bir boyut temsil edebilir. Örneğin, bu sınıfı, ekranda herhangi bir iki boyutlu nesnenin boyutunu hareketlendirmek için kullanabilirsiniz (dikdörtgen, denetim vb.). Bu sınıfı uygulamada kullanmak için, bu sınıfın bir nesnesinin örneğini oluşturun, CAnimationController:: AddAnimationObject öğesini kullanarak animasyon denetleyicisine ekleyin ve her bir geçişin genişlik ve/veya yüksekliğe uygulanması için AddTransition çağrısı yapın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxanimationcontroller. h

## <a name="canimationsizeaddtransition"></a><a name="addtransition"></a> CAnimationSize:: AddTransition

Genişlik ve yükseklik için geçişler ekler.

```cpp
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>Parametreler

*pCXTransition*<br/>
Genişlik için geçiş işaretçisi.

*pCYTransition*<br/>
Yükseklik geçişi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Belirtilen geçişleri genişlik ve yükseklik için animasyon değişkenlerine uygulanacak iç geçiş listesine eklemek için bu işlevi çağırın. Geçişler eklediğinizde, bunlar hemen uygulanmaz ve dahili bir listede depolanır. CAnimationController:: AnimateGroup ' i çağırdığınızda geçişler uygulanır (belirli bir değer için bir görsel taslağa eklenir). Boyutlardan birine geçiş uygulamanız gerekmiyorsa NULL geçirebilirsiniz.

## <a name="canimationsizecanimationsize"></a><a name="canimationsize"></a> CAnimationSize:: CAnimationSize

Bir animasyon boyutu nesnesi oluşturur.

```
CAnimationSize();

CAnimationSize(
    const CSize& szDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametreler

*szDefault*<br/>
Varsayılan boyutu belirtir.

*Ngroupıd*<br/>
Grup KIMLIĞINI belirtir.

*Nobjectıd*<br/>
Nesne KIMLIĞINI belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı verileri belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne, 0 olarak ayarlanacak genişlik, yükseklik, nesne KIMLIĞI ve Grup KIMLIĞI için varsayılan değerlerle oluşturulur. Bu, daha sonra SetDefaultValue ve SetID kullanılarak çalışma zamanında değiştirilebilir.

## <a name="canimationsizegetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationSize:: GetAnimationVariableList

Encapsulated animasyon değişkenlerini bir listeye koyar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*LST*<br/>
İşlev döndüğünde, genişliği ve yüksekliği temsil eden iki CAnimationVariable nesnesine işaretçiler içerir.

## <a name="canimationsizegetcx"></a><a name="getcx"></a> CAnimationSize:: GetCX

Genişliği temsil eden CAnimationVariable öğesine erişim sağlar.

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>Dönüş Değeri

Genişliği temsil eden kapsüllenmiş CAnimationVariable başvurusu.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, genişliği temsil eden temeldeki CAnimationVariable öğesine doğrudan erişim sağlamak için çağırabilirsiniz.

## <a name="canimationsizegetcy"></a><a name="getcy"></a> CAnimationSize:: GetCY

Yüksekliği temsil eden CAnimationVariable öğesine erişim sağlar.

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>Dönüş Değeri

Yüksekliği temsil eden kapsüllenmiş CAnimationVariable başvurusu.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, yüksekliği temsil eden temeldeki CAnimationVariable öğesine doğrudan erişim almak için çağırabilirsiniz.

## <a name="canimationsizegetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationSize:: GetDefaultValue

Genişlik ve yükseklik için varsayılan değerleri döndürür.

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan değerleri içeren bir CSize nesnesi.

### <a name="remarks"></a>Açıklamalar

Daha önce constructor veya SetDefaultValue tarafından ayarlanan varsayılan değeri almak için bu işlevi çağırın.

## <a name="canimationsizegetvalue"></a><a name="getvalue"></a> CAnimationSize:: GetValue

Geçerli değeri döndürür.

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>Parametreler

*szValue*<br/>
Çıktıların. Bu yöntemin döndürdüğü geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer başarıyla alınırsa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Animasyon boyutunun geçerli değerini almak için bu işlevi çağırın. Bu yöntem başarısız olursa veya genişlik ve boyut için temel alınan COM nesneleri başlatılmazsa, szValue daha önce oluşturucuda veya SetDefaultValue tarafından ayarlanan varsayılan değeri içerir.

## <a name="canimationsizem_cxvalue"></a><a name="m_cxvalue"></a> CAnimationSize:: m_cxValue

Animasyon boyutunun genişliğini temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_cxValue;
```

## <a name="canimationsizem_cyvalue"></a><a name="m_cyvalue"></a> CAnimationSize:: m_cyValue

Animasyon boyutunun yüksekliğini temsil eden Encapsulated animasyon değişkeni.

```
CAnimationVariable m_cyValue;
```

## <a name="canimationsizeoperator-csize"></a><a name="operator_csize"></a> CAnimationSize:: işleç CSize

CAnimationSize boyutunu CSize dönüştürür.

```
operator CSize();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon boyutunun geçerli değeri CSize.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir dahili olarak GetValue çağırır. GetValue bir nedenden dolayı başarısız olursa, döndürülen boyut genişlik ve yükseklik için varsayılan değerleri içerir.

## <a name="canimationsizeoperator"></a><a name="operator_eq"></a> CAnimationSize:: operator =

SzSrc 'yi CAnimationSize atar.

```cpp
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>Parametreler

*szSrc*<br/>
CSize veya boyutuna başvurur.

### <a name="remarks"></a>Açıklamalar

SzSrc 'yi CAnimationSize atar. Bu işleç, oluşturulduklarında genişlik ve yükseklik için temeldeki COM nesnelerini yeniden oluşturan SetDefaultValue ' ı çağırdığı için, animasyon başlamadan önce bunu yapmanız önerilir. Bu animasyon nesnesini olaylara abone oldıysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="canimationsizesetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationSize:: SetDefaultValue

Varsayılan değeri ayarlar.

```cpp
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>Parametreler

*szDefault*<br/>
Yeni varsayılan boyutu belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine varsayılan bir değer ayarlamak için bu işlevi kullanın. Bu yöntemler varsayılan değerleri animasyon boyutunun genişliğine ve yüksekliğine atar. Ayrıca, oluşturulan temel COM nesnelerini de yeniden oluşturur. Bu animasyon nesnesini olaylara abone oldıysanız (ValueChanged veya IntegerValueChanged), bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
