---
title: 'Platform:: Collections:: Backınsertıterator sınıfı'
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
helpviewer_keywords:
- BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
ms.openlocfilehash: 79854d8ead089aeba88fbdc151fdc0788dd181c1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445786"
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Platform:: Collections:: Backınsertıterator sınıfı

Öğelerin üzerine yazmak yerine, ardışık bir koleksiyonun arka ucuna kadar eklenen bir yineleyiciyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class BackInsertIterator :
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;
```

#### <a name="parameters"></a>Parametreler

*Şı*<br/>
Geçerli Koleksiyondaki öğenin türü.

### <a name="remarks"></a>Açıklamalar

Backınsertıterator sınıfı, [Back_insert_iterator sınıfının](../standard-library/back-insert-iterator-class.md)gerektirdiği kuralları uygular.

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Backınsertıterator:: Backınsertıterator](#ctor)|Backınsertıterator sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[Backınsertıterator:: operator * Işleci](#operator-dereference)|Geçerli Backınsertıterator öğesine bir başvuru alır.|
|[Backınsertıterator:: operator + + Işleci](#operator-increment)|Geçerli Backınsertıterator öğesine bir başvuru döndürür. Yineleyici değiştirilmemiş.|
|[Backınsertıterator:: operator = Işleci](#operator-assign)|Belirtilen nesneyi geçerli sıralı koleksiyonun sonuna ekler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BackInsertIterator`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="ctor"></a>Backınsertıterator:: Backınsertıterator Oluşturucusu

`BackInsertIterator` sınıfının yeni bir örneğini başlatır.

## <a name="syntax"></a>Sözdizimi

```
explicit BackInsertIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

#### <a name="parameters"></a>Parametreler

*Yönetim*<br/>
IVector\<T > nesnesi.

### <a name="remarks"></a>Açıklamalar

`BackInsertIterator`, `v`parametresi tarafından belirtilen nesnenin son öğesinden sonra öğeleri ekler.

## <a name="operator-assign"></a>Backınsertıterator:: operator = Işleci

Belirtilen nesneyi geçerli sıralı koleksiyonun sonuna ekler.

## <a name="syntax"></a>Sözdizimi

```
BackInsertIterator& operator=( const T& t);
```

#### <a name="parameters"></a>Parametreler

*şı*<br/>
Geçerli koleksiyona eklenecek nesne.

### <a name="return-value"></a>Dönüş Değeri

Geçerli Backınsertıterator öğesine bir başvuru.

## <a name="operator-dereference"></a>Backınsertıterator:: operator * Işleci

Geçerli Backınsertıterator öğesine bir başvuru alır.

## <a name="syntax"></a>Sözdizimi

```
BackInsertIterator& operator*();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Backınsertıterator öğesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu işleç geçerli Backınsertıterator öğesine bir başvuru döndürür. geçerli koleksiyonda hiçbir öğe değil.

## <a name="operator-increment"></a>Backınsertıterator:: operator + + Işleci

Geçerli Backınsertıterator öğesine bir başvuru döndürür. Yineleyici değiştirilmemiş.

## <a name="syntax"></a>Sözdizimi

```
BackInsertIterator& operator++();

BackInsertIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli Backınsertıterator öğesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Tasarım yaparak, ilk sözdizimi örneği geçerli Backınsertıterator ' ı önceden artırır ve ikinci sözdizimi geçerli Backınsertıterator ' ı artırır. İkinci sözdiziminde `int` türü, gerçek bir tamsayı işleneni değil, bir artırma sonrası işlemi gösterir.

Ancak, bu işleç aslında Backınsertıterator öğesini değiştirmez. Bunun yerine, bu işleç değiştirilmemiş, geçerli Yineleyici için bir başvuru döndürür. Bu, [işleç *](#operator-dereference)ile aynı davranıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)
