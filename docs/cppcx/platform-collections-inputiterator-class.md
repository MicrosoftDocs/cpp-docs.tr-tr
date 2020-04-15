---
title: Platform::Collections::InputIterator Sınıfı
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
ms.openlocfilehash: 92f9b15f474a5aa3d063f0ccfb663f56baf8de31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354560"
---
# <a name="platformcollectionsinputiterator-class"></a>Platform::Collections::InputIterator Sınıfı

Windows Runtime'dan türetilen koleksiyonlar için Standart Şablon Kitaplığı Girişi Sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <typename X>
class InputIterator;
```

#### <a name="parameters"></a>Parametreler

*X*<br/>
Giriş Kaydedici şablon sınıfının dis adı.

### <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|`difference_type`|İşaretçi farkı (ptrdiff_t).|
|`iterator_category`|Giriş yineleme kategorisi (::std::input_iterator_tag).|
|`pointer`|Bir işaretçi`const X`|
|`reference`|Bir başvuru`const X`|
|`value_type`|Yazı `X` adı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Giriş::Giriş](#ctor)|InputIterator sınıfının yeni bir örneğini başolarak karşılar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[Giriş::operator!= Operatör](#operator-inequality)|Geçerli InputIterator'un belirtilen bir InputIterator'a eşit olup olmadığını gösterir.|
|[Giriş::operator* Operatör](#operator-dereference)|Geçerli InputIterator tarafından belirtilen öğeye bir başvuru alır.|
|[GirişIterator::operator++ Operatör](#operator-increment)|Geçerli InputIterator'u da artışlar.|
|[Giriş::operator== Operatör](#operator-equality)|Geçerli InputIterator'un belirtilen bir InputIterator'a eşit olup olmadığını gösterir.|
|[Giriş::operatör-> Operatörü](#operator-arrow)|Geçerli InputIterator tarafından başvurulan öğenin adresini alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InputIterator`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** collection.h

**Ad alanı:** Platform::Koleksiyonlar

## <a name="inputiteratorinputiterator-constructor"></a><a name="ctor"></a>Giriş::Giriş Oluşturucu

InputIterator sınıfının yeni bir örneğini başolarak karşılar.

### <a name="syntax"></a>Sözdizimi

```
InputIterator();
explicit InputIterator(Windows::Foundation::Collections<X>^ iterator);
```

### <a name="parameters"></a>Parametreler

*Yineleyici*<br/>
Bir yineleyici nesnesi.

## <a name="inputiteratoroperator-gt-operator"></a><a name="operator-arrow"></a>GirişIterator::operator-&gt; Operatör

Geçerli InputIterator tarafından belirtilen öğenin adresini alır.

### <a name="syntax"></a>Sözdizimi

```
pointer operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli InputIterator tarafından belirtilen öğenin adresi.

## <a name="inputiteratoroperator-operator"></a><a name="operator-dereference"></a>Giriş::operatör Operatörü\*

Geçerli InputIterator tarafından belirtilen öğeye bir başvuru alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli InputIterator tarafından belirtilen öğe.

## <a name="inputiteratoroperator-operator"></a><a name="operator-equality"></a>Giriş::operator== Operatör

Geçerli InputIterator'un belirtilen bir InputIterator'a eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator== (const InputIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir GirişIterator.

### <a name="return-value"></a>Dönüş Değeri

geçerli InputIterator *diğer*eşitise **doğru** ; aksi takdirde, **yanlış**.

## <a name="inputiteratoroperator-operator"></a><a name="operator-increment"></a>GirişIterator::operator++ Operatör

Geçerli InputIterator'u da artışlar.

### <a name="syntax"></a>Sözdizimi

```
InputIterator& operator++();
InputIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi artışlarını ve ardından geçerli InputIterator'u döndürür. İkinci sözdizimi, geçerli InputIterator'un bir kopyasını döndürür ve ardından geçerli InputIterator'u da arta erdirilir.

### <a name="remarks"></a>Açıklamalar

İlk InputIterator sözdizimi geçerli InputIterator ön-artışlar.

İkinci sözdizimi sonrası geçerli InputIterator'u atar. İkinci `int` sözdiziminde tür, gerçek bir tamsayı operand değil, artış sonrası işlemi gösterir.

## <a name="inputiteratoroperator-operator"></a><a name="operator-inequality"></a>Giriş::operator!= Operatör

Geçerli InputIterator'un belirtilen bir InputIterator'a eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator!=(const InputIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir GirişIterator.

### <a name="return-value"></a>Dönüş Değeri

geçerli InputIterator *diğer*eşit değilse **doğru** ; aksi takdirde, **yanlış**.

## <a name="see-also"></a>Ayrıca bkz.

[Platform İsim Alanı](platform-namespace-c-cx.md)
