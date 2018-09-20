---
title: CAnimationSize sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 974bf49b4315095a2103c50bfb81cc5e164273d6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433183"
---
# <a name="canimationsize-class"></a>CAnimationSize sınıfı

Boyutlarının animasyonu oluşturulabilen bir nesne boyutlandırma işlevselliğini uygular.

## <a name="syntax"></a>Sözdizimi

```
class CAnimationSize : public CAnimationBaseObject;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationSize::CAnimationSize](#canimationsize)|Fazla Yüklendi. Bir animasyon boyutu nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationSize::AddTransition](#addtransition)|Genişlik ve yükseklik geçişleri ekler.|
|[CAnimationSize::GetCX](#getcx)|Genişliği temsil eden CAnimationVariable için erişim sağlar.|
|[CAnimationSize::GetCY](#getcy)|Yüksekliği temsil eden CAnimationVariable için erişim sağlar.|
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|Genişlik ve yükseklik için varsayılan değerleri döndürür.|
|[CAnimationSize::GetValue](#getvalue)|Geçerli bir değer döndürür.|
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|Varsayılan değerini ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|Kapsüllenmiş animasyon değişkenleri bir listesine koyar. (Geçersiz kılmaları [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationSize::operator CSize](#operator_csize)|Bir CAnimationSize için bir CSize dönüştürür.|
|[CAnimationSize::operator =](#operator_eq)|CAnimationSize için szSrc atar.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAnimationSize::m_cxValue](#m_cxvalue)|Animasyon boyutunun genişliğini temsil eden kapsüllenmiş animasyon değişkeni.|
|[CAnimationSize::m_cyValue](#m_cyvalue)|Animasyon boyutunun yüksekliğini temsil eden kapsüllenmiş animasyon değişkeni.|

## <a name="remarks"></a>Açıklamalar

CAnimationSize sınıfı iki CAnimationVariable nesneleri kapsüller ve uygulamalarda bir boyutu temsil edebilir. Örneğin, herhangi iki boyutuna animasyon ekleme için bu sınıf kullanabilirsiniz ekranında boyutlu nesne (dikdörtgen gibi denetim vb.). Bu sınıf kullanmak için yalnızca bu sınıfın bir nesnesi, CAnimationController::AddAnimationObject kullanarak animasyon denetleyicisine eklemek ve genişlik ve/veya yüksekliği uygulanacak AddTransition her geçiş için çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationSize::AddTransition

Genişlik ve yükseklik geçişleri ekler.

```
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>Parametreler

*pCXTransition*<br/>
Genişlik için geçiş için bir işaretçi.

*pCYTransition*<br/>
Yükseklik geçiş için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Belirtilen geçiş iç genişliği ve yüksekliği için animasyon değişkenlere uygulanacak geçişleri listesine eklemek için bu işlevi çağırın. Geçişleri eklediğinizde, bunlar değil hemen uygulanır ve bir iç listesinde depolanır. Geçiş (belirli bir değeri için bir görsel taslağı eklenebilir) uygulandığını CAnimationController::AnimateGroup çağırdığınızda. Bir geçiş boyutlardan birini uygulamak gerekmiyorsa NULL geçirebilirsiniz.

##  <a name="canimationsize"></a>  CAnimationSize::CAnimationSize

Bir animasyon boyutu nesne oluşturur.

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
Varsayılan boyutunu belirtir.

*nGroupID*<br/>
Grup kimliğini belirtir.

*nObjectID*<br/>
Nesne kimliğini belirtir.

*dwUserData*<br/>
Kullanıcı tanımlı veri belirtir.

### <a name="remarks"></a>Açıklamalar

Nesne kimliği ve 0 olarak ayarlanacak grubu kimliği nesnenin genişlik, yükseklik için varsayılan değerlerle oluşturulur. Çalışma zamanında SetDefaultValue ve SetID kullanarak daha sonra değiştirilebilir.

##  <a name="getanimationvariablelist"></a>  CAnimationSize::GetAnimationVariableList

Kapsüllenmiş animasyon değişkenleri bir listesine koyar.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametreler

*lst*<br/>
İşlevi döndüğünde, genişliğini ve yüksekliğini temsil eden iki CAnimationVariable nesnelerine işaretçiler içerir.

##  <a name="getcx"></a>  CAnimationSize::GetCX

Genişliği temsil eden CAnimationVariable için erişim sağlar.

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş CAnimationVariable genişliği temsil eden bir başvuru.

### <a name="remarks"></a>Açıklamalar

Temel alınan CAnimationVariable genişliği temsil eden doğrudan erişim elde etmek için bu yöntem çağırabilirsiniz.

##  <a name="getcy"></a>  CAnimationSize::GetCY

Yüksekliği temsil eden CAnimationVariable için erişim sağlar.

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>Dönüş Değeri

Kapsüllenmiş CAnimationVariable yüksekliği temsil eden bir başvuru.

### <a name="remarks"></a>Açıklamalar

Temel alınan CAnimationVariable yüksekliği temsil eden doğrudan erişim elde etmek için bu yöntem çağırabilirsiniz.

##  <a name="getdefaultvalue"></a>  CAnimationSize::GetDefaultValue

Genişlik ve yükseklik için varsayılan değerleri döndürür.

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan değerleri içeren bir CSize nesnesi.

### <a name="remarks"></a>Açıklamalar

Oluşturucu veya SetDefaultValue tarafından önceden ayarlanmış varsayılan değerini almak için bu işlevi çağırın.

##  <a name="getvalue"></a>  CAnimationSize::GetValue

Geçerli bir değer döndürür.

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>Parametreler

*szValue*<br/>
Çıktı. Bu yöntem döndürüldüğünde, geçerli değeri içerir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli değer başarıyla alındığında TRUE, Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Animasyon boyutu geçerli değerini almak için bu işlevi çağırın. Bu yöntem başarısız olursa veya genişlik ve boyutla için temel alınan COM nesnelerini başlatılmamış szValue Oluşturucusu veya SetDefaultValue önceden ayarlanmış varsayılan değeri içerir.

##  <a name="m_cxvalue"></a>  CAnimationSize::m_cxValue

Animasyon boyutunun genişliğini temsil eden kapsüllenmiş animasyon değişkeni.

```
CAnimationVariable m_cxValue;
```

##  <a name="m_cyvalue"></a>  CAnimationSize::m_cyValue

Animasyon boyutunun yüksekliğini temsil eden kapsüllenmiş animasyon değişkeni.

```
CAnimationVariable m_cyValue;
```

##  <a name="operator_csize"></a>  CAnimationSize::operator CSize

Bir CAnimationSize için bir CSize dönüştürür.

```
operator CSize();
```

### <a name="return-value"></a>Dönüş Değeri

Animasyon boyuttaki CSize olarak geçerli değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, GetValue dahili olarak çağırır. GetValue herhangi bir nedenle başarısız olursa, döndürülen boyutu genişlik ve yükseklik için varsayılan değerleri içerecektir.

##  <a name="operator_eq"></a>  CAnimationSize::operator =

CAnimationSize için szSrc atar.

```
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>Parametreler

*szSrc*<br/>
CSize ya da aynı boyuta başvurur.

### <a name="remarks"></a>Açıklamalar

CAnimationSize için szSrc atar. Bu işleç oluşturulmuş durumunda, temel alınan COM nesneleri, genişlik ve yükseklik yeniden oluşturur ve SetDefaultValue çağırdığı animasyon başlamadan önce bunu yapmak için önerilir. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesnesine abone, bu olayları yeniden etkinleştirmeniz gerekir.

##  <a name="setdefaultvalue"></a>  CAnimationSize::SetDefaultValue

Varsayılan değerini ayarlar.

```
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>Parametreler

*szDefault*<br/>
Yeni varsayılan boyutunu belirtir.

### <a name="remarks"></a>Açıklamalar

Animasyon nesnesine bir varsayılan değer ayarlamak için bu işlevi kullanın. Bu yöntem, genişlik ve yükseklik animasyon boyutu için varsayılan değerleri atar. Ayrıca bunlar oluşturulmuşsa temel COM nesneleri yeniden oluşturur. Bu olayları (ValueChanged veya IntegerValueChanged) animasyon nesnesine abone, bu olayları yeniden etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
