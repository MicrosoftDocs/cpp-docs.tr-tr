---
description: 'Hakkında daha fazla bilgi edinin: critical_section sınıfı'
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
ms.openlocfilehash: d781ce467123197521bf92dd4d932a665e55c6a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188943"
---
# <a name="critical_section-class"></a>critical_section Sınıfı

Eşzamanlılık Çalışma Zamanı açıkça farkında olan, yer olmayan bir mutex.

## <a name="syntax"></a>Syntax

```cpp
class critical_section;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`native_handle_type`|Bir `critical_section` nesneye başvuru.|

### <a name="public-classes"></a>Ortak sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[critical_section:: scoped_lock sınıfı](#critical_section__scoped_lock_class)|Bir nesne için özel durum güvenli Çıı sarmalayıcısı `critical_section` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[critical_section](#ctor)|Yeni bir kritik bölüm oluşturur.|
|[~ critical_section yok edici](#dtor)|Kritik bir bölümü yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ine](#lock)|Bu kritik bölümü elde edin.|
|[native_handle](#native_handle)|Varsa, platforma özgü yerel bir tanıtıcı döndürür.|
|[try_lock](#try_lock)|Kilidi engellenmeden almaya çalışır.|
|[try_lock_for](#try_lock_for)|Kilidi, belirli bir süre boyunca engellenmeksizin almaya çalışır.|
|[kaldırın](#unlock)|Kritik bölümün kilidini açar.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [eşitleme veri yapıları](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`critical_section`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="critical_section"></a><a name="ctor"></a> critical_section

Yeni bir kritik bölüm oluşturur.

```cpp
critical_section();
```

## <a name="critical_section"></a><a name="dtor"></a> ~ critical_section

Kritik bir bölümü yok eder.

```cpp
~critical_section();
```

### <a name="remarks"></a>Açıklamalar

Yok edicinin çalıştırıldığı zaman kilidin artık tutulmuyor olması beklenmektedir. Kritik bölümün kilit ile sınıfların 'a izin verilmesi, yine de tanımsız davranışa neden olur.

## <a name="lock"></a><a name="lock"></a> ine

Bu kritik bölümü elde edin.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Bir [](#critical_section__scoped_lock_class) `critical_section` nesneyi özel durum güvenli bir şekilde almak ve serbest bırakmak için scoped_lock yapısını kullanmak genellikle daha güvenlidir.

Kilit çağıran bağlam tarafından zaten tutuluyorsa, bir [improper_lock](improper-lock-class.md) özel durumu oluşturulur.

## <a name="native_handle"></a><a name="native_handle"></a> native_handle

Varsa, platforma özgü yerel bir tanıtıcı döndürür.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

Kritik bölüme bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bir `critical_section` nesne, Windows işletim sistemi için platforma özgü yerel tanıtıcı ile ilişkili değildir. Yöntemi yalnızca nesnenin kendisi için bir başvuru döndürür.

## <a name="critical_sectionscoped_lock-class"></a><a name="critical_section__scoped_lock_class"></a> critical_section:: scoped_lock sınıfı

Bir nesne için özel durum güvenli Çıı sarmalayıcısı `critical_section` .

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_ctor"></a> scoped_lock:: scoped_lock

Bir `scoped_lock` nesnesi oluşturur ve `critical_section` parametre içinde geçirilen nesneyi alır `_Critical_section` . Kritik bölüm başka bir iş parçacığı tarafından tutuluyorsa bu çağrı engellenir.

```cpp
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>Parametreler

*_Critical_section*<br/>
Kilitlenecek kritik bölüm.

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock

Bir nesneyi yok eder `scoped_lock` ve oluşturucusunda sağlanan kritik bölümü yayınlar.

```cpp
~scoped_lock();
```

## <a name="try_lock"></a><a name="try_lock"></a> try_lock

Kilidi engellenmeden almaya çalışır.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit alınırsa değer **`true`** ; Aksi takdirde değer **`false`** .

## <a name="try_lock_for"></a><a name="try_lock_for"></a> try_lock_for

Kilidi, belirli bir süre boyunca engellenmeksizin almaya çalışır.

```cpp
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>Parametreler

*_Timeout*<br/>
Zaman aşımından önce beklenecek milisaniye sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kilit alınırsa değer **`true`** ; Aksi takdirde değer **`false`** .

## <a name="unlock"></a><a name="unlock"></a> kaldırın

Kritik bölümün kilidini açar.

```cpp
void unlock();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[reader_writer_lock sınıfı](reader-writer-lock-class.md)
