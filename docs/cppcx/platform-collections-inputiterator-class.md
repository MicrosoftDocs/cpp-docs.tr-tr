---
title: 'Platform:: Collections:: InputIterator sınıfı'
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
ms.openlocfilehash: 4aeef07a34c04bd1ab47acf808026024faada567
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218435"
---
# <a name="platformcollectionsinputiterator-class"></a>Platform:: Collections:: InputIterator sınıfı

Windows Çalışma Zamanı türetilen koleksiyonlar için standart bir şablon kitaplığı InputIterator sağlar.

## <a name="syntax"></a>Söz dizimi

```
template <typename X>
class InputIterator;
```

#### <a name="parameters"></a>Parametreler

*Sayı*<br/>
InputIterator şablon sınıfının TypeName 'i.

### <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`difference_type`|Bir işaretçi farkı (ptrdiff_t).|
|`iterator_category`|Bir giriş yineleyicisinin kategorisi (:: std:: input_iterator_tag).|
|`pointer`|Bir işaretçi`const X`|
|`reference`|Bir başvurusu`const X`|
|`value_type`|`X`TypeName.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[InputIterator:: InputIterator](#ctor)|InputIterator sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[InputIterator:: operator! = Işleci](#operator-inequality)|Geçerli InputIterator 'ın belirtilen bir InputIterator öğesine eşit olup olmadığını gösterir.|
|[InputIterator:: operator * Işleci](#operator-dereference)|Geçerli InputIterator tarafından belirtilen öğeye bir başvuru alır.|
|[InputIterator:: operator + + Işleci](#operator-increment)|Geçerli InputIterator değerini artırır.|
|[InputIterator:: operator = = Işleci](#operator-equality)|Geçerli InputIterator 'ın belirtilen bir InputIterator öğesine eşit olup olmadığını gösterir.|
|[InputIterator:: operator-> Işleci](#operator-arrow)|Geçerli InputIterator tarafından başvurulan öğenin adresini alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`InputIterator`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="inputiteratorinputiterator-constructor"></a><a name="ctor"></a>InputIterator:: InputIterator Oluşturucusu

InputIterator sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Söz dizimi

```
InputIterator();
explicit InputIterator(Windows::Foundation::Collections<X>^ iterator);
```

### <a name="parameters"></a>Parametreler

*iden*<br/>
Yineleyici nesne.

## <a name="inputiteratoroperator-gt-operator"></a><a name="operator-arrow"></a>InputIterator:: operator- &gt; işleci

Geçerli InputIterator tarafından belirtilen öğenin adresini alır.

### <a name="syntax"></a>Sözdizimi

```
pointer operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli InputIterator tarafından belirtilen öğenin adresi.

## <a name="inputiteratoroperator-operator"></a><a name="operator-dereference"></a>InputIterator:: operator \* işleci

Geçerli InputIterator tarafından belirtilen öğeye bir başvuru alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli InputIterator tarafından belirtilen öğe.

## <a name="inputiteratoroperator-operator"></a><a name="operator-equality"></a>InputIterator:: operator = = Işleci

Geçerli InputIterator 'ın belirtilen bir InputIterator öğesine eşit olup olmadığını gösterir.

### <a name="syntax"></a>Söz dizimi

```
bool operator== (const InputIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir InputIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli InputIterator, *diğer*değere eşitse; Aksi takdirde, **`false`** .

## <a name="inputiteratoroperator-operator"></a><a name="operator-increment"></a>InputIterator:: operator + + Işleci

Geçerli InputIterator değerini artırır.

### <a name="syntax"></a>Sözdizimi

```
InputIterator& operator++();
InputIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi artar ve sonra geçerli InputIterator ' i döndürür. İkinci sözdizimi, geçerli InputIterator öğesinin bir kopyasını döndürür ve ardından geçerli InputIterator ' ı artırır.

### <a name="remarks"></a>Açıklamalar

İlk InputIterator sözdizimi, geçerli InputIterator ' i önceden arttırır.

İkinci sözdizimi, güncel InputIterator ' i arttırır. **`int`** İkinci sözdiziminde tür, gerçek bir tamsayı işleneni değil, artırma sonrası bir işlemi gösterir.

## <a name="inputiteratoroperator-operator"></a><a name="operator-inequality"></a>InputIterator:: operator! = Işleci

Geçerli InputIterator 'ın belirtilen bir InputIterator öğesine eşit olup olmadığını gösterir.

### <a name="syntax"></a>Söz dizimi

```
bool operator!=(const InputIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir InputIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli InputIterator, *diğer*değere eşit değilse; Aksi takdirde, **`false`** .

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)
