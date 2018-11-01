---
title: 'Platform::Collections:: ınputıterator sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
ms.openlocfilehash: d01519870d52a51a18e25f73d5caa853d90a8792
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455243"
---
# <a name="platformcollectionsinputiterator-class"></a>Platform::Collections:: ınputıterator sınıfı

Windows çalışma zamanını şuradan türetilmiş koleksiyonlar için bir standart Şablon kitaplığı Inputıterator sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <typename X>
class InputIterator;
```

#### <a name="parameters"></a>Parametreler

*X*<br/>
Typename Inputıterator Şablon sınıfı.

### <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`difference_type`|İşaretçi farkı (ptrdiff_t).|
|`iterator_category`|Bir giriş yineleyici kategorisi (:: std::input_iterator_tag).|
|`pointer`|Bir işaretçi bir `const X`|
|`reference`|Bir başvuru bir `const X`|
|`value_type`|`X` Typename.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[InputIterator::InputIterator](#ctor)|Inputıterator sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[InputIterator::operator! = işleci](#operator-inequality)|Geçerli Inputıterator için belirtilen bir Inputıterator eşit olup olmadığını gösterir.|
|[InputIterator::operator * işleci](#operator-decrement)|Geçerli Inputıterator tarafından belirtilen öğeye bir başvuru alır.|
|[InputIterator::operator ++ işleci](#operator-increment)|Geçerli Inputıterator artırır.|
|[InputIterator::operator == işleci](#operator-equality)|Geçerli Inputıterator için belirtilen bir Inputıterator eşit olup olmadığını gösterir.|
|[InputIterator::operator -> işleci](#operator-arrow)|Geçerli Inputıterator tarafından başvurulan bir öğenin adresi alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InputIterator`

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Platform::Collections

## <a name="ctor"></a>  InputIterator::InputIterator Oluşturucusu

Inputıterator sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```
InputIterator();
explicit InputIterator(Windows::Foundation::Collections<X>^ iter);
```

### <a name="parameters"></a>Parametreler

*Iter*<br/>
Bir yineleyici nesnesi.

## <a name="operator-arrow"></a>  InputIterator::operator -&gt; işleci

Geçerli Inputıterator tarafından belirtilen bir öğenin adresi alır.

### <a name="syntax"></a>Sözdizimi

```
pointer operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Inputıterator tarafından belirtilen bir öğenin adresi.

## <a name="operator-dereference"></a>  InputIterator::operator\* işleci

Geçerli Inputıterator tarafından belirtilen öğeye bir başvuru alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Inputıterator tarafından belirtilen öğe.

## <a name="operator-equality"></a>  InputIterator::operator == işleci

Geçerli Inputıterator için belirtilen bir Inputıterator eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator== (const InputIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir Inputıterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** geçerli Inputıterator eşitse *diğer*; Aksi takdirde **false**.

## <a name="operator-increment"></a>  InputIterator::operator ++ işleci

Geçerli Inputıterator artırır.

### <a name="syntax"></a>Sözdizimi

```
InputIterator& operator++();
InputIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk söz dizimi artırır ve geçerli Inputıterator döndürür. İkinci sözdizimi geçerli Inputıterator bir kopyasını döndürür ve ardından geçerli Inputıterator artırır.

### <a name="remarks"></a>Açıklamalar

İlk Inputıterator söz dizimi geçerli Inputıterator önceden artırır.

İkinci sözdizimi geçerli Inputıterator sonrası artırır. `int` İkinci söz diziminde türü sonrası artırma işlemi, gerçek tamsayı işlenen gösterir.

## <a name="operator-inequality"></a>  InputIterator::operator! = işleci

Geçerli Inputıterator için belirtilen bir Inputıterator eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator!=(const InputIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir Inputıterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** geçerli Inputıterator eşit değilse *diğer*; Aksi takdirde **false**.

## <a name="see-also"></a>Ayrıca Bkz.

[Platform Namespace](platform-namespace-c-cx.md)