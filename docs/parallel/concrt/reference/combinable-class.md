---
title: combinable Sınıfı
ms.date: 11/04/2016
f1_keywords:
- combinable
- PPL/concurrency::combinable
- PPL/concurrency::combinable::combinable
- PPL/concurrency::combinable::clear
- PPL/concurrency::combinable::combine
- PPL/concurrency::combinable::combine_each
- PPL/concurrency::combinable::local
helpviewer_keywords:
- combinable class
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
ms.openlocfilehash: d445b8ac1d2a8487e9e1ec4f21f63cf5ef071e91
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224974"
---
# <a name="combinable-class"></a>combinable Sınıfı

`combinable<T>`Nesne, paralel algoritmalar sırasında kilit içermeyen iş parçacığı yerel alt hesaplamaları gerçekleştirmek için, verilerin iş parçacığına özel kopyalarını sağlamak üzere tasarlanmıştır. Paralel işlemin sonunda, iş parçacığı özel alt hesaplamaları daha sonra nihai bir sonuçla birleştirilebilir. Bu sınıf, paylaşılan bir değişken yerine kullanılabilir ve bu paylaşılan değişkende çok fazla çekişme olmaması durumunda performans iyileştirmesine neden olabilir.

## <a name="syntax"></a>Söz dizimi

```cpp
template<typename T>
class combinable;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Son birleştirilmiş sonucun veri türü. Türün bir kopya Oluşturucusu ve varsayılan bir oluşturucusu olmalıdır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[combinable](#ctor)|Fazla Yüklendi. Yeni bir `combinable` nesne oluşturur.|
|[~ combinable yıkıcısı](#dtor)|Bir nesneyi yok eder `combinable` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lediğiniz](#clear)|Önceki kullanımlardan tüm ara hesaplama sonuçlarını temizler.|
|[combine](#combine)|Sağlanan birleştirme functor 'u çağırarak iş parçacığı yerel alt hesaplamaları kümesinden son bir değer hesaplar.|
|[combine_each](#combine_each)|İş parçacığı yerel alt hesaplamaları kümesinden bir son değeri, iş parçacığı yerel alt hesaplama başına sağlanan birleştirme functor 'u çağırarak hesaplar. Nihai sonuç, Function nesnesi tarafından biriktirilir.|
|[Yerel](#local)|Fazla Yüklendi. Thread-Private alt hesaplama için bir başvuru döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|`combinable`Başka bir nesneden bir nesneye atar `combinable` .|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`combinable`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="clear"></a><a name="clear"></a>lediğiniz

Önceki kullanımlardan tüm ara hesaplama sonuçlarını temizler.

```cpp
void clear();
```

## <a name="combinable"></a><a name="ctor"></a>combinable

Yeni bir `combinable` nesne oluşturur.

```cpp
combinable();

template <typename _Function>
explicit combinable(_Function _FnInitialize);

combinable(const combinable& _Copy);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Başlatma functor nesnesinin türü.

*_FnInitialize*<br/>
Her yeni iş parçacığı özel değerini başlatmak için çağrılacak bir işlev `T` . İmzaya sahip bir işlev çağrısı işlecini desteklemesi gerekir `T ()` .

*_Copy*<br/>
Var olan bir `combinable` nesne buna kopyalanacak.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, varsayılan Oluşturucu olan yeni öğeleri tür için başlatır `T` .

İkinci Oluşturucu, parametresi olarak sağlanan başlatma functor kullanarak yeni öğeleri başlatır `_FnInitialize` .

Üçüncü Oluşturucu kopya oluşturucudur.

## <a name="combinable"></a><a name="dtor"></a>~ combinable

Bir nesneyi yok eder `combinable` .

```cpp
~combinable();
```

## <a name="combine"></a><a name="combine"></a>bile

Sağlanan birleştirme functor 'u çağırarak iş parçacığı yerel alt hesaplamaları kümesinden son bir değer hesaplar.

```cpp
template<typename _Function>
T combine(_Function _FnCombine) const;
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
İki iş parçacığı yerel alt hesaplama birleştirmek için çağrılacak işlev nesnesinin türü.

*_FnCombine*<br/>
Alt hesaplamaları birleştirmek için kullanılan functor. İmzası veya olur `T (T, T)` `T (const T&, const T&)` ve ilişkilendirilebilir ve iletişim olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Tüm iş parçacığı-özel alt hesaplamaları birleştirmenin nihai sonucu.

## <a name="combine_each"></a><a name="combine_each"></a>combine_each

İş parçacığı yerel alt hesaplamaları kümesinden bir son değeri, iş parçacığı yerel alt hesaplama başına sağlanan birleştirme functor 'u çağırarak hesaplar. Nihai sonuç, Function nesnesi tarafından biriktirilir.

```cpp
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Tek iş parçacığı yerel alt hesaplamayı birleştirmek için çağrılacak işlev nesnesinin türü.

*_FnCombine*<br/>
Bir alt hesaplamayı birleştirmek için kullanılan functor. İmzası veya olur `void (T)` `void (const T&)` ve ilişkilendirilebilir ve iletişim olmalıdır.

## <a name="local"></a><a name="local"></a>Yerel

Thread-Private alt hesaplama için bir başvuru döndürür.

```cpp
T& local();

T& local(bool& _Exists);
```

### <a name="parameters"></a>Parametreler

*_Exists*<br/>
Boole başvurusu. Bu bağımsız değişken tarafından başvurulan Boolean değeri, **`true`** alt hesaplama bu iş parçacığında zaten mevcutsa olarak ayarlanır ve bu **`false`** iş parçacığında ilk alt hesaplauyorsa olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı özel alt hesaplama başvurusu.

## <a name="operator"></a><a name="operator_eq"></a>işleç =

`combinable`Başka bir nesneden bir nesneye atar `combinable` .

```cpp
combinable& operator= (const combinable& _Copy);
```

### <a name="parameters"></a>Parametreler

*_Copy*<br/>
Var olan bir `combinable` nesne buna kopyalanacak.

### <a name="return-value"></a>Dönüş Değeri

Bu nesneye bir başvuru `combinable` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
