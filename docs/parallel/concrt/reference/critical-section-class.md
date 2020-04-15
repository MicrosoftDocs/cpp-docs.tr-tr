---
title: critical_section Sınıfı
ms.date: 11/04/2016
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
ms.openlocfilehash: 24f96282a7728c6db6e0b05d36406f15383913f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372686"
---
# <a name="critical_section-class"></a>critical_section Sınıfı

Eşzamanlılık Çalışma Zamanı'nın açıkça farkında olan, yeniden işlemmeyen bir mutex.

## <a name="syntax"></a>Sözdizimi

```cpp
class critical_section;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|`native_handle_type`|Bir `critical_section` nesneye başvuru.|

### <a name="public-classes"></a>Genel Sınıflar

|Adı|Açıklama|
|----------|-----------------|
|[critical_section::scoped_lock Sınıfı](#critical_section__scoped_lock_class)|Bir `critical_section` nesne için özel bir özel durum güvenli RAII sarıcı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[critical_section](#ctor)|Yeni bir kritik bölüm oluşturuyor.|
|[~critical_section Yıkıcı](#dtor)|Kritik bir bölümü yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Kilit](#lock)|Bu kritik bölümü edinir.|
|[native_handle](#native_handle)|Varsa, platforma özgü bir yerel tanıtıcı döndürür.|
|[try_lock](#try_lock)|Engellenmeden kilidi elde etmeye çalışır.|
|[try_lock_for](#try_lock_for)|Belirli bir milisaniye sayısı için engellemeden kilidi elde etmeye çalışır.|
|[Kilidini](#unlock)|Kritik bölümün kilidini açar.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../../../parallel/concrt/synchronization-data-structures.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`critical_section`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt.h

**Ad alanı:** eşzamanlılık

## <a name="critical_section"></a><a name="ctor"></a>Crıtıcal_sectıon

Yeni bir kritik bölüm oluşturuyor.

```cpp
critical_section();
```

## <a name="critical_section"></a><a name="dtor"></a>~critical_section

Kritik bir bölümü yok eder.

```cpp
~critical_section();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalışırken kilidin artık tutulmadığı beklenmektedir. Kritik bölümün kilitle imha etmesine izin vermek hala tanımlanmamış davranışlara neden olabilir.

## <a name="lock"></a><a name="lock"></a>Kilit

Bu kritik bölümü edinir.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Genellikle bir özel durum [scoped_lock](#critical_section__scoped_lock_class) güvenli bir şekilde bir `critical_section` nesne elde etmek ve serbest bırakmak için scoped_lock yapı kullanmak daha güvenlidir.

Kilit zaten arama bağlamında tutuluyorsa, [improper_lock](improper-lock-class.md) bir özel durum atılır.

## <a name="native_handle"></a><a name="native_handle"></a>native_handle

Varsa, platforma özgü bir yerel tanıtıcı döndürür.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

Kritik bölüme bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bir `critical_section` nesne, Windows işletim sistemi için platforma özgü bir yerel tanıtıcıyla ilişkili değildir. Yöntem sadece nesnenin kendisine bir başvuru döndürür.

## <a name="critical_sectionscoped_lock-class"></a><a name="critical_section__scoped_lock_class"></a>critical_section::scoped_lock Sınıfı

Bir `critical_section` nesne için özel bir özel durum güvenli RAII sarıcı.

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_ctor"></a>scoped_lock::scoped_lock

Bir `scoped_lock` nesne inşa eder `critical_section` ve parametrede geçen nesneyi edinir. `_Critical_section` Kritik bölüm başka bir iş parçacığı tarafından tutulursa, bu çağrı engellenir.

```cpp
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>Parametreler

*_Critical_section*<br/>
Kilitlenmek için kritik bölüm.

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_dtor"></a>scoped_lock::~scoped_lock

Bir `scoped_lock` nesneyi yok eder ve oluşturucusu yla sağlanan kritik bölümü serbest bırakır.

```cpp
~scoped_lock();
```

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

Engellenmeden kilidi elde etmeye çalışır.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit elde edildiyse, değer **doğru;** aksi takdirde, değer **yanlış**.

## <a name="try_lock_for"></a><a name="try_lock_for"></a>try_lock_for

Belirli bir milisaniye sayısı için engellemeden kilidi elde etmeye çalışır.

```cpp
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>Parametreler

*_Timeout*<br/>
Zamanlaması önce beklemek milisaniye sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kilit elde edildiyse, değer **doğru;** aksi takdirde, değer **yanlış**.

## <a name="unlock"></a><a name="unlock"></a>Kilidini

Kritik bölümün kilidini açar.

```cpp
void unlock();
```

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[reader_writer_lock Sınıfı](reader-writer-lock-class.md)
