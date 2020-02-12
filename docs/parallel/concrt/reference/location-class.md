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
ms.openlocfilehash: 7f45ff6d3092bd7c27e81adddca72c9411f752d1
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139819"
---
# <a name="location-class"></a>location Sınıfı

Donanımda fiziksel bir konumun soyutlaması.

## <a name="syntax"></a>Sözdizimi

```cpp
class location;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[konum](#ctor)|Fazla Yüklendi. `location` nesnesi oluşturur.|
|[~ Location yıkıcısı](#dtor)|`location` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[geçerli](#current)|Çağıran iş parçacığının yürütüldüğü en belirli yeri temsil eden bir `location` nesnesi döndürür.|
|[from_numa_node](#from_numa_node)|Belirli bir NUMA düğümünü temsil eden `location` nesnesini döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator!=](#operator_neq)|İki `location` nesnesinin farklı bir konumu temsil ettiğini belirler.|
|[işleç =](#operator_eq)|Farklı bir `location` nesnesinin içeriğini buna atar.|
|[işleç = =](#operator_eq_eq)|İki `location` nesnesinin aynı konumu temsil ettiğini belirtir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`location`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="dtor"></a>~ konum

`location` nesnesini yok eder.

```cpp
~location();
```

## <a name="current"></a>geçerli

Çağıran iş parçacığının yürütüldüğü en belirli yeri temsil eden bir `location` nesnesi döndürür.

```cpp
static location __cdecl current();
```

### <a name="return-value"></a>Dönüş Değeri

Çağıran iş parçacığının yürütüldüğü en belirli yeri temsil eden bir konum.

## <a name="from_numa_node"></a>from_numa_node

Belirli bir NUMA düğümünü temsil eden `location` nesnesini döndürür.

```cpp
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```

### <a name="parameters"></a>Parametreler

*_NumaNodeNumber*<br/>
İçin bir konum oluşturmak üzere NUMA düğüm numarası.

### <a name="return-value"></a>Dönüş Değeri

`_NumaNodeNumber` parametresi tarafından belirtilen NUMA düğümünü temsil eden bir konum.

## <a name="ctor"></a>konumuna

`location` nesnesi oluşturur.

```cpp
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

*_Id*<br/>

*_BindingId*<br/>

*_PBinding*<br/>
Seçim Bağlama işaretçisi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak oluşturulmuş bir konum sistemi bir bütün olarak temsil eder.

## <a name="operator_neq"></a>işleç! =

İki `location` nesnesinin farklı bir konumu temsil ettiğini belirler.

```cpp
bool operator!= (const location& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
İşlenen `location`.

### <a name="return-value"></a>Dönüş Değeri

iki konum farklıysa **true** , aksi takdirde **false** .

## <a name="operator_eq"></a>işleç =

Farklı bir `location` nesnesinin içeriğini buna atar.

```cpp
location& operator= (const location& _Rhs);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Kaynak `location` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator_eq_eq"></a>işleç = =

İki `location` nesnesinin aynı konumu temsil ettiğini belirtir.

```cpp
bool operator== (const location& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
İşlenen `location`.

### <a name="return-value"></a>Dönüş Değeri

iki konum özdeş ise **true** , aksi takdirde **false** .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
