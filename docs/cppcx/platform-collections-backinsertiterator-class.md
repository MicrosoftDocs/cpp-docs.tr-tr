---
title: Platform::Koleksiyonlar::BackInsertIterator Sınıfı
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
helpviewer_keywords:
- BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
ms.openlocfilehash: fcb680c8f43a50801d081762bb5b546cb110c52d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354764"
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Platform::Koleksiyonlar::BackInsertIterator Sınıfı

Sıralı bir koleksiyonun arka ucuna öğeleri yazmak yerine ekleyen bir yineleyiciyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class BackInsertIterator :
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Geçerli koleksiyondaki öğe türü.

### <a name="remarks"></a>Açıklamalar

BackInsertIterator sınıfı [back_insert_iterator Sınıfı'nın](../standard-library/back-insert-iterator-class.md)gerektirdiği kuralları uygular.

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[BackInsertIterator::BackInsertIterator](#ctor)|BackInsertIterator sınıfının yeni bir örneğini başolarak karşılar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[BackInsertIterator::operator* Operatör](#operator-dereference)|Geçerli BackInsertIterator bir başvuru alır.|
|[BackInsertIterator::operator++ Operatör](#operator-increment)|Geçerli BackInsertIterator bir başvuru döndürür. Yineleyici değiştirilmemiş.|
|[BackInsertIterator::operator= Operatör](#operator-assign)|Belirtilen nesneyi geçerli sıralı koleksiyonun sonuna ekler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BackInsertIterator`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** collection.h

**Ad alanı:** Platform::Koleksiyonlar

## <a name="backinsertiteratorbackinsertiterator-constructor"></a><a name="ctor"></a>BackInsertIterator::BackInsertIterator Constructor

`BackInsertIterator` sınıfının yeni bir örneğini başlatır.

## <a name="syntax"></a>Sözdizimi

```
explicit BackInsertIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

#### <a name="parameters"></a>Parametreler

*v*<br/>
Bir IVector\<T> nesnesi.

### <a name="remarks"></a>Açıklamalar

Bir `BackInsertIterator` parametre `v`ile belirtilen nesnenin son öğesi sonra öğeleri ekler.

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-assign"></a>BackInsertIterator::operator= Operatör

Belirtilen nesneyi geçerli sıralı koleksiyonun sonuna ekler.

## <a name="syntax"></a>Sözdizimi

```
BackInsertIterator& operator=( const T& t);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Geçerli koleksiyona eklenen nesne.

### <a name="return-value"></a>Dönüş Değeri

Geçerli BackInsertIterator bir başvuru.

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-dereference"></a>BackInsertIterator::operator* Operatör

Geçerli BackInsertIterator bir başvuru alır.

## <a name="syntax"></a>Sözdizimi

```
BackInsertIterator& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli BackInsertIterator bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işleç geçerli BackInsertIterator bir referans döndürür; geçerli koleksiyondaki herhangi bir öğeye değil.

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-increment"></a>BackInsertIterator::operator++ Operatör

Geçerli BackInsertIterator bir başvuru döndürür. Yineleyici değiştirilmemiş.

## <a name="syntax"></a>Sözdizimi

```
BackInsertIterator& operator++();

BackInsertIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli BackInsertIterator bir başvuru.

### <a name="remarks"></a>Açıklamalar

Tasarım olarak, ilk sözdizimi örneği geçerli BackInsertIterator'u, ikinci sözdizimi sonrası ise geçerli BackInsertIterator'u öne doğru atar. İkinci `int` sözdiziminde tür, gerçek bir tamsayı operand değil, artış sonrası işlemi gösterir.

Ancak, bu işleç aslında BackInsertIterator değiştirmez. Bunun yerine, bu işleç değiştirilmemiş, geçerli yineleyicibir başvuru döndürür. Bu işleç le aynı [davranıştır*](#operator-dereference).

## <a name="see-also"></a>Ayrıca bkz.

[Platform İsim Alanı](platform-namespace-c-cx.md)
