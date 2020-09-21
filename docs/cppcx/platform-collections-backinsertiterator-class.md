---
title: 'Platform:: Collections:: Backınsertıterator sınıfı'
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
helpviewer_keywords:
- BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
ms.openlocfilehash: f5c82a776a537d469d42a16bd4f425e7bb2c13aa
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742937"
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Platform:: Collections:: Backınsertıterator sınıfı

Öğelerin üzerine yazmak yerine, ardışık bir koleksiyonun arka ucuna kadar eklenen bir yineleyiciyi temsil eder.

## <a name="syntax"></a>Söz dizimi

```
template <typename T>
class BackInsertIterator :
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Geçerli Koleksiyondaki öğenin türü.

### <a name="remarks"></a>Açıklamalar

Backınsertıterator sınıfı, [Back_insert_iterator sınıfının](../standard-library/back-insert-iterator-class.md)gerektirdiği kuralları uygular.

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Backınsertıterator:: Backınsertıterator](#ctor)|Backınsertıterator sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Backınsertıterator:: operator * Işleci](#operator-dereference)|Geçerli Backınsertıterator öğesine bir başvuru alır.|
|[Backınsertıterator:: operator + + Işleci](#operator-increment)|Geçerli Backınsertıterator öğesine bir başvuru döndürür. Yineleyici değiştirilmemiş.|
|[Backınsertıterator:: operator = Işleci](#operator-assign)|Belirtilen nesneyi geçerli sıralı koleksiyonun sonuna ekler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BackInsertIterator`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="backinsertiteratorbackinsertiterator-constructor"></a><a name="ctor"></a> Backınsertıterator:: Backınsertıterator Oluşturucusu

`BackInsertIterator` sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Söz dizimi

```
explicit BackInsertIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

#### <a name="parameters"></a>Parametreler

*Yönetim*<br/>
Bir IVector \<T> nesnesi.

### <a name="remarks"></a>Açıklamalar

`BackInsertIterator`, Parametre tarafından belirtilen nesnenin son öğesinden sonra öğeler ekler `v` .

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-assign"></a> Backınsertıterator:: operator = Işleci

Belirtilen nesneyi geçerli sıralı koleksiyonun sonuna ekler.

### <a name="syntax"></a>Söz dizimi

```
BackInsertIterator& operator=( const T& t);
```

#### <a name="parameters"></a>Parametreler

*şı*<br/>
Geçerli koleksiyona eklenecek nesne.

### <a name="return-value"></a>Dönüş Değeri

Geçerli Backınsertıterator öğesine bir başvuru.

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-dereference"></a> Backınsertıterator:: operator * Işleci

Geçerli Backınsertıterator öğesine bir başvuru alır.

### <a name="syntax"></a>Syntax

```
BackInsertIterator& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Backınsertıterator öğesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işleç geçerli Backınsertıterator öğesine bir başvuru döndürür. geçerli koleksiyonda hiçbir öğe değil.

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-increment"></a> Backınsertıterator:: operator + + Işleci

Geçerli Backınsertıterator öğesine bir başvuru döndürür. Yineleyici değiştirilmemiş.

### <a name="syntax"></a>Syntax

```
BackInsertIterator& operator++();

BackInsertIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Backınsertıterator öğesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Tasarım yaparak, ilk sözdizimi örneği geçerli Backınsertıterator ' ı önceden artırır ve ikinci sözdizimi geçerli Backınsertıterator ' ı artırır. **`int`** İkinci sözdiziminde tür, gerçek bir tamsayı işleneni değil, artırma sonrası bir işlemi gösterir.

Ancak, bu işleç aslında Backınsertıterator öğesini değiştirmez. Bunun yerine, bu işleç değiştirilmemiş, geçerli Yineleyici için bir başvuru döndürür. Bu, [işleç *](#operator-dereference)ile aynı davranıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)
