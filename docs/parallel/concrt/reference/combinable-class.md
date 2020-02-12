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
ms.openlocfilehash: a1954cd3a69233deed053da5b5fdef0dbc183b80
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141440"
---
# <a name="combinable-class"></a>combinable Sınıfı

`combinable<T>` nesnesi, paralel algoritmalar sırasında kilit içermeyen iş parçacığı yerel alt hesaplamalar gerçekleştirmek için verilerin iş parçacığı özel kopyalarını sağlamaya yöneliktir. Paralel işlemin sonunda, iş parçacığı özel alt hesaplamaları daha sonra nihai bir sonuçla birleştirilebilir. Bu sınıf, paylaşılan bir değişken yerine kullanılabilir ve bu paylaşılan değişkende çok fazla çekişme olmaması durumunda performans iyileştirmesine neden olabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
class combinable;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Son birleştirilmiş sonucun veri türü. Türün bir kopya Oluşturucusu ve varsayılan bir oluşturucusu olmalıdır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[combinable](#ctor)|Fazla Yüklendi. Yeni bir `combinable` nesnesi oluşturur.|
|[~ combinable yıkıcısı](#dtor)|`combinable` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lediğiniz](#clear)|Önceki kullanımlardan tüm ara hesaplama sonuçlarını temizler.|
|[bile](#combine)|Sağlanan birleştirme functor 'u çağırarak iş parçacığı yerel alt hesaplamaları kümesinden son bir değer hesaplar.|
|[combine_each](#combine_each)|İş parçacığı yerel alt hesaplamaları kümesinden bir son değeri, iş parçacığı yerel alt hesaplama başına sağlanan birleştirme functor 'u çağırarak hesaplar. Nihai sonuç, Function nesnesi tarafından biriktirilir.|
|[local](#local)|Fazla Yüklendi. Thread-Private alt hesaplama için bir başvuru döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Başka bir `combinable` nesnesinden bir `combinable` nesnesine atar.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`combinable`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="clear"></a>lediğiniz

Önceki kullanımlardan tüm ara hesaplama sonuçlarını temizler.

```cpp
void clear();
```

## <a name="ctor"></a>combinable

Yeni bir `combinable` nesnesi oluşturur.

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
`T`türünün her yeni iş parçacığı özel değerini başlatmak için çağrılacak bir işlev. İmza `T ()`bir işlev çağrısı işlecini desteklemelidir.

*_Copy*<br/>
Bu nesneye kopyalanacak var olan bir `combinable` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, `T`türü için varsayılan Oluşturucu ile yeni öğeleri başlatır.

İkinci Oluşturucu, `_FnInitialize` parametresi olarak sağlanan başlatma functor kullanarak yeni öğeleri başlatır.

Üçüncü Oluşturucu kopya oluşturucudur.

## <a name="dtor"></a>~ combinable

`combinable` nesnesini yok eder.

```cpp
~combinable();
```

## <a name="combine"></a>bile

Sağlanan birleştirme functor 'u çağırarak iş parçacığı yerel alt hesaplamaları kümesinden son bir değer hesaplar.

```cpp
template<typename _Function>
T combine(_Function _FnCombine) const;
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
İki iş parçacığı yerel alt hesaplama birleştirmek için çağrılacak işlev nesnesinin türü.

*_FnCombine*<br/>
Alt hesaplamaları birleştirmek için kullanılan functor. İmzası `T (T, T)` veya `T (const T&, const T&)`ve ilişkilendirilebilir ve iletişim olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Tüm iş parçacığı-özel alt hesaplamaları birleştirmenin nihai sonucu.

## <a name="combine_each"></a>combine_each

İş parçacığı yerel alt hesaplamaları kümesinden bir son değeri, iş parçacığı yerel alt hesaplama başına sağlanan birleştirme functor 'u çağırarak hesaplar. Nihai sonuç, Function nesnesi tarafından biriktirilir.

```cpp
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Tek iş parçacığı yerel alt hesaplamayı birleştirmek için çağrılacak işlev nesnesinin türü.

*_FnCombine*<br/>
Bir alt hesaplamayı birleştirmek için kullanılan functor. İmzası `void (T)` veya `void (const T&)`ve ilişkilendirilebilir ve iletişim olmalıdır.

## <a name="local"></a>Yerel

Thread-Private alt hesaplama için bir başvuru döndürür.

```cpp
T& local();

T& local(bool& _Exists);
```

### <a name="parameters"></a>Parametreler

*_Exists*<br/>
Boole başvurusu. Alt hesaplama bu iş parçacığında zaten mevcutsa, bu bağımsız değişken tarafından başvurulan Boolean değeri **true** olarak ayarlanır ve bu iş parçacığında ilk alt hesaplauyorsa **false** olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı özel alt hesaplama başvurusu.

## <a name="operator_eq"></a>işleç =

Başka bir `combinable` nesnesinden bir `combinable` nesnesine atar.

```cpp
combinable& operator= (const combinable& _Copy);
```

### <a name="parameters"></a>Parametreler

*_Copy*<br/>
Bu nesneye kopyalanacak var olan bir `combinable` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu `combinable` nesnesine bir başvuru.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
