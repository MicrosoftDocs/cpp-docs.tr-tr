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
ms.openlocfilehash: 05256516c0a693a282b8d0de56d6c9e7465f2740
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252977"
---
# <a name="combinable-class"></a>combinable Sınıfı

`combinable<T>` Nesne sırasında paralel algoritmalar kilidi serbest iş parçacığı-yerel alt hesaplamalar gerçekleştirmek için veri, iş parçacığı özel kopyalarını sağlamak için tasarlanmıştır. Paralel işlemin sonunda, iş parçacığı özel alt hesaplamalar sonra bir nihai sonucu birleştirilebilir. Bu sınıf, paylaşılan bir değişken yerine kullanılabilir ve aksi durumda olacaktır, paylaşılan bir değişken üzerinde Çekişme birçok performans geliştirmeyle neden olabilir.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>
class combinable;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Birleştirilmiş sonuç veri türü. Türü, bir kopya oluşturucu ve varsayılan bir oluşturucuya sahip olmalıdır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[birleştirilebilir](#ctor)|Fazla Yüklendi. Yeni bir oluşturur `combinable` nesne.|
|[~ combinable yok Edicisi](#dtor)|Yok eder bir `combinable` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Temizle](#clear)|Herhangi bir önceki kullanım hesaplama sonuçlardan Ara temizler.|
|[Birleştirme](#combine)|Sağlanan birleştirme işlev nesnesini çağırarak iş parçacığı-yerel alt hesaplamalar kümesinden son değer hesaplar.|
|[combine_each](#combine_each)|Her iş parçacığı-yerel alt hesaplama için bir kez sağlanan birleştirme işlev nesnesini çağırarak iş parçacığı-yerel alt hesaplamalar kümesinden son değer hesaplar. Nihai sonucu işlev nesnesi tarafından toplanır.|
|[local](#local)|Fazla Yüklendi. İş parçacığı özel alt hesaplama bir başvuru döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator=](#operator_eq)|Atayan bir `combinable` başka bir nesne `combinable` nesne.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`combinable`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppl.h

**Namespace:** eşzamanlılık

##  <a name="clear"></a> Temizle

Herhangi bir önceki kullanım hesaplama sonuçlardan Ara temizler.

```
void clear();
```

##  <a name="ctor"></a> birleştirilebilir

Yeni bir oluşturur `combinable` nesne.

```
combinable();

template <typename _Function>
explicit combinable(_Function _FnInitialize);

combinable(const combinable& _Copy);
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Başlatma functor nesnenin türü.

*_FnInitialize*<br/>
Her yeni iş parçacığı özel değer türü başlatmak için çağrılacak bir işlev `T`. İmzalı bir işlev çağrısı işleci desteklemelidir `T ()`.

*_Kopyala*<br/>
Mevcut bir `combinable` bunun kopyalanacak nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu türü için varsayılan oluşturucu yeni öğelerle başlatır `T`.

İkinci oluşturucu olarak sağlanan başlatma functor kullanarak yeni öğeler başlatır `_FnInitialize` parametresi.

Üçüncü Oluşturucu, kopya oluşturucudur.

##  <a name="dtor"></a> ~ combinable

Yok eder bir `combinable` nesne.

```
~combinable();
```

##  <a name="combine"></a> Birleştirme

Sağlanan birleştirme işlev nesnesini çağırarak iş parçacığı-yerel alt hesaplamalar kümesinden son değer hesaplar.

```
template<typename _Function>
T combine(_Function _FnCombine) const;
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
İki iş parçacığı-yerel alt hesaplamalar birleştirmek için çağrılacak işlev nesnesinin türü.

*_FnCombine*<br/>
Alt hesaplamalar birleştirmek için kullanılan functor. Kendi imzası `T (T, T)` veya `T (const T&, const T&)`, ve ilişkilendirilebilir ve yer değiştirebilirlik olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Tüm iş parçacığı özel alt hesaplamalar birleştirme nihai sonucu.

##  <a name="combine_each"></a> combine_each

Her iş parçacığı-yerel alt hesaplama için bir kez sağlanan birleştirme işlev nesnesini çağırarak iş parçacığı-yerel alt hesaplamalar kümesinden son değer hesaplar. Nihai sonucu işlev nesnesi tarafından toplanır.

```
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```

### <a name="parameters"></a>Parametreler

*_Function*<br/>
Tek bir iş parçacığı-yerel alt hesaplama birleştirmek için çağrılacak işlev nesnesinin türü.

*_FnCombine*<br/>
Bir alt hesaplama birleştirmek için kullanılan functor. Kendi imzası `void (T)` veya `void (const T&)`ve ilişkilendirilebilir ve yer değiştirebilirlik olması gerekir.

##  <a name="local"></a> Yerel

İş parçacığı özel alt hesaplama bir başvuru döndürür.

```
T& local();

T& local(bool& _Exists);
```

### <a name="parameters"></a>Parametreler

*_Exists*<br/>
Bir boolean değerine başvuru. Bu bağımsız değişkeni tarafından başvurulan bir Boole değeri ayarlanacak **true** alt hesaplama zaten bu iş parçacığı üzerinde varolan ve kümesine **false** bu ilk alt hesaplama bu iş parçacığı üzerinde ise.

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı özel alt hesaplama başvuru.

##  <a name="operator_eq"></a> işleç =

Atayan bir `combinable` başka bir nesne `combinable` nesne.

```
combinable& operator= (const combinable& _Copy);
```

### <a name="parameters"></a>Parametreler

*_Kopyala*<br/>
Mevcut bir `combinable` bunun kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `combinable` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
