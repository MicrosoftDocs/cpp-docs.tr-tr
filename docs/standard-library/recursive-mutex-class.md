---
title: recursive_mutex sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::recursive_mutex
- mutex/std::recursive_mutex::recursive_mutex
- mutex/std::recursive_mutex::lock
- mutex/std::recursive_mutex::try_lock
- mutex/std::recursive_mutex::unlock
dev_langs:
- C++
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::recursive_mutex [C++]
- std::recursive_mutex [C++], recursive_mutex
- std::recursive_mutex [C++], lock
- std::recursive_mutex [C++], try_lock
- std::recursive_mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: 89c39f006cee8c62c22f3caf7e2c10ee9a0c1d03
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="recursivemutex-class"></a>recursive_mutex Sınıfı

Temsil eden bir *mutex türü*. Tersine için [mutex](../standard-library/mutex-class-stl.md), zaten kilitli olan nesneler için kilitleme yöntemlerine çağrılarının iyi tanımlanmış bir davranıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
class recursive_mutex;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[recursive_mutex](#recursive_mutex)|Oluşturan bir `recursive_mutex` nesnesi.|
|[~recursive_mutex Destructor](#dtorrecursive_mutex_destructor)|Tarafından kullanılan tüm kaynakları serbest `recursive_mutex` nesnesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|İş parçacığı mutex sahipliğini alıncaya kadar çağıran iş parçacığı engeller.|
|[try_lock](#try_lock)|Engellenmeden mutex sahipliğini almaya çalışır.|
|[kilidini aç](#unlock)|Mutex sahipliğini serbest bırakır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="lock"></a>  kilitleme

İş parçacığı sahipliğini alıncaya kadar çağıran iş parçacığı engeller `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`yöntemi hemen döndürür ve önceki kilit yürürlükte kalır.

## <a name="recursive_mutex"></a>  recursive_mutex

Oluşturan bir `recursive_mutex` nesnesi kilitli değil.

```cpp
recursive_mutex();
```

## <a name="dtorrecursive_mutex_destructor"></a>  ~ recursive_mutex

Nesne tarafından kullanılan tüm kaynakları serbest bırakır.

```cpp
~recursive_mutex();
```

### <a name="remarks"></a>Açıklamalar

Yok Edicisi çalıştığında nesne kilitliyse tanımlanmamış bir davranıştır.

## <a name="try_lock"></a>  try_lock

Sahipliğini almayı denediğinde `mutex` engelleme olmadan.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

`true` Yöntem başarıyla sahipliğini elde ederse `mutex` veya çağıran iş parçacığı zaten sahipse `mutex`; Aksi halde, `false`.

### <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığı zaten sahipse `mutex`, işlevi hemen döndürür `true`, ve önceki kilit yürürlükte kalır.

## <a name="unlock"></a>  kilidini aç

Mutex sahipliğini serbest bırakır.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem sahipliğini serbest `mutex` yalnızca olarak gibi birçok kez çağrıldıktan sonra [kilit](#lock) ve [try_lock](#try_lock) üzerinde başarıyla çağrılmış `recursive_mutex` nesnesi.

Çağıran iş parçacığı kendi değil, `mutex`, tanımlanmamış bir davranıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<Mutex >](../standard-library/mutex.md)<br/>
