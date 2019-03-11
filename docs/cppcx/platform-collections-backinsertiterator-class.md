---
title: 'Platform::Collections:: backınsertıterator sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
helpviewer_keywords:
- BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
ms.openlocfilehash: 7478555b19bbe5c984fcbe531d2d8be1a0b865a9
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739531"
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Platform::Collections:: backınsertıterator sınıfı

Geçersiz kılar, sıralı bir koleksiyonu, arka uçtaki elementini yerine ekler bir yineleyici temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class BackInsertIterator :
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Geçerli koleksiyon öğesinin türü.

### <a name="remarks"></a>Açıklamalar

Gerekli kurallar BackInsertIterator sınıfın uyguladığı [back_insert_iterator sınıfı](../standard-library/back-insert-iterator-class.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[BackInsertIterator::BackInsertIterator](#ctor)|BackInsertIterator sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[BackInsertIterator::operator * işleci](#operator-dereference)|Geçerli BackInsertIterator bir başvuru alır.|
|[BackInsertIterator::operator++ Operator](#operator-increment)|Geçerli BackInsertIterator bir başvuru döndürür. Yineleyici değiştirilmez.|
|[BackInsertIterator::operator= Operator](#operator-assign)|Belirtilen nesnenin geçerli sıralı koleksiyonun sonuna ekler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BackInsertIterator`

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Platform::Collections

---
## <a name="ctor"></a>  BackInsertIterator::BackInsertIterator Oluşturucusu

Yeni bir örneğini başlatır `BackInsertIterator` sınıfı.

## <a name="syntax"></a>Sözdizimi

```

explicit BackInsertIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

#### <a name="parameters"></a>Parametreler

*v*<br/>
Bir Ivector\<T > nesne.

### <a name="remarks"></a>Açıklamalar

A `BackInsertIterator` parametresi tarafından belirtilen nesnenin son öğeden sonra öğe ekler; `v`.

## <a name="operator-assign"></a>  BackInsertIterator::operator = işleci

Belirtilen nesnenin geçerli sıralı koleksiyonun sonuna ekler.

## <a name="syntax"></a>Sözdizimi

```
BackInsertIterator& operator=( const T& t);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Geçerli koleksiyona eklenecek nesne.

### <a name="return-value"></a>Dönüş Değeri

Geçerli BackInsertIterator başvuru.

## <a name="operator-dereference"></a>  BackInsertIterator::operator * işleci

Geçerli BackInsertIterator bir başvuru alır.

## <a name="syntax"></a>Sözdizimi

```
BackInsertIterator& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli BackInsertIterator başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işleç geçerli BackInsertIterator bir başvuru döndürür; değil herhangi bir öğenin için geçerli koleksiyonu.

## <a name="operator-increment"></a>  BackInsertIterator::operator ++ işleci

Geçerli BackInsertIterator bir başvuru döndürür. Yineleyici değiştirilmez.

## <a name="syntax"></a>Sözdizimi

```

BackInsertIterator& operator++();

BackInsertIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli BackInsertIterator başvuru.

### <a name="remarks"></a>Açıklamalar

Tasarıma göre ilk sözdizimini örnek geçerli BackInsertIterator önceden artırır ve ikinci sözdizimi geçerli BackInsertIterator sonrası artırır. `int` İkinci söz diziminde türü sonrası artırma işlemi, gerçek tamsayı işlenen gösterir.

Ancak, bu işleci BackInsertIterator gerçekten değiştirmez. Bunun yerine, bu işleci bir başvuru değiştirilmemiş, geçerli bir yineleyici döndürür. Aynı davranışı budur [işleci *](#dereference-operator).

## <a name="see-also"></a>Ayrıca bkz.

[Platform Namespace](platform-namespace-c-cx.md)
