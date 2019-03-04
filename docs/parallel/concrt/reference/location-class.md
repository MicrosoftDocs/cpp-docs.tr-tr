---
title: location Sınıfı
ms.date: 11/04/2016
f1_keywords:
- location
- CONCRT/concurrency::location
- CONCRT/concurrency::location::location
- CONCRT/concurrency::location::current
- CONCRT/concurrency::location::from_numa_node
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
ms.openlocfilehash: 5e90dd3b23b33f6699f2df4ce0df9178f95816b8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273263"
---
# <a name="location-class"></a>location Sınıfı

Fiziksel bir donanım konumunda bir soyutlamasıdır.

## <a name="syntax"></a>Sözdizimi

```
class location;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[konum](#ctor)|Fazla Yüklendi. Oluşturur bir `location` nesne.|
|[~ location yok Edicisi](#dtor)|Yok eder bir `location` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Geçerli](#current)|Döndürür bir `location` çağıran iş parçacığının yürütülmekte en belirgin yeri temsil eden nesne.|
|[from_numa_node](#from_numa_node)|Döndürür bir `location` belirli bir NUMA düğümünde temsil eden nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator!=](#operator_neq)|İki olup olmadığını belirleyen `location` nesneleri farklı bir konumu temsil eder.|
|[operator=](#operator_eq)|Farklı bir içeriğini atar `location` buna nesne.|
|[operator==](#operator_eq_eq)|İki olup olmadığını belirleyen `location` nesneleri aynı konumu temsil eder.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`location`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="dtor"></a> yaklaşık konum

Yok eder bir `location` nesne.

```
~location();
```

##  <a name="current"></a> Geçerli

Döndürür bir `location` çağıran iş parçacığının yürütülmekte en belirgin yeri temsil eden nesne.

```
static location __cdecl current();
```

### <a name="return-value"></a>Dönüş Değeri

En belirgin yeri temsil eden bir konum, çağıran iş parçacığını yürütüyor.

##  <a name="from_numa_node"></a> from_numa_node

Döndürür bir `location` belirli bir NUMA düğümünde temsil eden nesne.

```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```

### <a name="parameters"></a>Parametreler

*_NumaNodeNumber*<br/>
İçin bir konum oluşturmak için NUMA düğümü sayısı.

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen NUMA düğümü temsil eden bir konuma `_NumaNodeNumber` parametresi.

##  <a name="ctor"></a> Konum

Oluşturur bir `location` nesne.

```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>

*_LocationType*<br/>

*_Kimliği*<br/>

*_BindingId*<br/>

*_PBinding*<br/>
(İsteğe bağlı) Bağlama işaretçisi.

### <a name="remarks"></a>Açıklamalar

Oluşturulmuş varsayılan konumu, sistemin bir bütün olarak temsil eder.

##  <a name="operator_neq"></a> işleç! =

İki olup olmadığını belirleyen `location` nesneleri farklı bir konumu temsil eder.

```
bool operator!= (const location& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
İşlenen `location`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** iki konum farklıysa **false** Aksi takdirde.

##  <a name="operator_eq"></a> işleç =

Farklı bir içeriğini atar `location` buna nesne.

```
location& operator= (const location& _Rhs);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Kaynak `location` nesne.

### <a name="return-value"></a>Dönüş Değeri

##  <a name="operator_eq_eq"></a> işleç ==

İki olup olmadığını belirleyen `location` nesneleri aynı konumu temsil eder.

```
bool operator== (const location& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
İşlenen `location`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** iki konum aynıysa ve **false** Aksi takdirde.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
