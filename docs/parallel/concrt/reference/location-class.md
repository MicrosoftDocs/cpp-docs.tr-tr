---
description: 'Daha fazla bilgi edinin: location Sınıfı'
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
ms.openlocfilehash: ae6ce0ac58d504f1fb99f5c38db04bb402dc31c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335794"
---
# <a name="location-class"></a>location Sınıfı

Donanımda fiziksel bir konumun soyutlaması.

## <a name="syntax"></a>Syntax

```cpp
class location;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[konumuna](#ctor)|Fazla Yüklendi. Bir `location` nesnesi oluşturur.|
|[~ Location yıkıcısı](#dtor)|Bir nesneyi yok eder `location` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[geçerli](#current)|`location`Çağıran iş parçacığının yürütüldüğü en belirli yeri temsil eden bir nesne döndürür.|
|[from_numa_node](#from_numa_node)|`location`Belirli BIR NUMA düğümünü temsil eden bir nesne döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç! =](#operator_neq)|İki `location` nesnenin farklı bir konumu temsil ettiğini belirler.|
|[işleç =](#operator_eq)|Başka bir nesnenin içeriğini buna atar `location` .|
|[işleç = =](#operator_eq_eq)|İki `location` nesnenin aynı konumu temsil ettiğini belirtir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`location`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="location"></a><a name="dtor"></a> ~ konum

Bir nesneyi yok eder `location` .

```cpp
~location();
```

## <a name="current"></a><a name="current"></a> geçerli

`location`Çağıran iş parçacığının yürütüldüğü en belirli yeri temsil eden bir nesne döndürür.

```cpp
static location __cdecl current();
```

### <a name="return-value"></a>Dönüş Değeri

Çağıran iş parçacığının yürütüldüğü en belirli yeri temsil eden bir konum.

## <a name="from_numa_node"></a><a name="from_numa_node"></a> from_numa_node

`location`Belirli BIR NUMA düğümünü temsil eden bir nesne döndürür.

```cpp
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```

### <a name="parameters"></a>Parametreler

*_NumaNodeNumber*<br/>
İçin bir konum oluşturmak üzere NUMA düğüm numarası.

### <a name="return-value"></a>Dönüş Değeri

Parametresi tarafından belirtilen NUMA düğümünü temsil eden bir konum `_NumaNodeNumber` .

## <a name="location"></a><a name="ctor"></a> konumuna

Bir `location` nesnesi oluşturur.

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

## <a name="operator"></a><a name="operator_neq"></a> işleç! =

İki `location` nesnenin farklı bir konumu temsil ettiğini belirler.

```cpp
bool operator!= (const location& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
İşleneni `location` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** iki konum farklıysa, **`false`** tersi durumda.

## <a name="operator"></a><a name="operator_eq"></a> işleç =

Başka bir nesnenin içeriğini buna atar `location` .

```cpp
location& operator= (const location& _Rhs);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Kaynak `location` nesne.

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator"></a><a name="operator_eq_eq"></a> işleç = =

İki `location` nesnenin aynı konumu temsil ettiğini belirtir.

```cpp
bool operator== (const location& _Rhs) const;
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
İşleneni `location` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** iki konum özdeş ise ve **`false`** Aksi durumda.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
