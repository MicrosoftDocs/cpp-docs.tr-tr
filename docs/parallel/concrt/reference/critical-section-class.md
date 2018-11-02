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
ms.openlocfilehash: a08cb5049d742a9740361595bd931a2f7a48bd16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498776"
---
# <a name="criticalsection-class"></a>critical_section Sınıfı

Eşzamanlılık çalışma zamanının açıkça farkında olan reentrant olmayan mutex.

## <a name="syntax"></a>Sözdizimi

```
class critical_section;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`native_handle_type`|Bir başvuru bir `critical_section` nesne.|

### <a name="public-classes"></a>Genel sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[critical_section::scoped_lock sınıfı](#critical_section__scoped_lock_class)|Bir özel durum güvenli için RAII sarmalayıcı bir `critical_section` nesne.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[critical_section](#ctor)|Yeni kritik bir bölüm oluşturur.|
|[~ critical_section yok Edicisi](#dtor)|Kritik Bölümü yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|Bu kritik bölüm devralır.|
|[native_handle](#native_handle)|Varsa bir platforma özel yerel tanıtıcı döndürür.|
|[try_lock](#try_lock)|Engellemeden kilit almaya çalışır.|
|[try_lock_for](#try_lock_for)|Belirli bir milisaniye sayısı için engellemeden kilit almaya çalışır.|
|[Kilit açma](#unlock)|Kritik bölüm kilidini açar.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [eşitleme veri yapıları](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`critical_section`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> critical_section

Yeni kritik bir bölüm oluşturur.

```
critical_section();
```

##  <a name="dtor"></a> ~ critical_section

Kritik Bölümü yok eder.

```
~critical_section();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştığında kilit artık tutulan beklenmektedir. Kilit ile yok etmek üzere kritik bölüm izin verme hala sonuçlarını tanımsız davranışlara tutulan.

##  <a name="lock"></a> Kilit

Bu kritik bölüm devralır.

```
void lock();
```

### <a name="remarks"></a>Açıklamalar

Yazılımınız genellikle güvenlidir [scoped_lock](#critical_section__scoped_lock_class) almak ve yayın yapısı bir `critical_section` bir özel durum nesnesi güvenli bir yoludur.

Arayan girintileme kilidi zaten tutarsa bir [improper_lock](improper-lock-class.md) özel durumu oluşturulur.

##  <a name="native_handle"></a> native_handle

Varsa bir platforma özel yerel tanıtıcı döndürür.

```
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

Kritik bölüm başvuru.

### <a name="remarks"></a>Açıklamalar

A `critical_section` nesne platforma özel yerel işleyici Windows işletim sistemi için ile ilişkili değil. Yöntemi yalnızca nesnesine bir başvuru döndürür.

##  <a name="critical_section__scoped_lock_class"></a>  critical_section::scoped_lock sınıfı

Bir özel durum güvenli için RAII sarmalayıcı bir `critical_section` nesne.

```
class scoped_lock;
```

##  <a name="critical_section__scoped_lock_ctor"></a> scoped_lock::scoped_lock

Oluşturur bir `scoped_lock` alır ve nesne `critical_section` geçirilen nesne `_Critical_section` parametresi. Bu çağrı, kritik bölüm başka bir iş parçacığı tarafından yapılmazsa engeller.

```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>Parametreler

*_Critical_section*<br/>
Kilitlemek için kritik bölüm.

##  <a name="critical_section__scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock

Yok eder bir `scoped_lock` nesne ve onun oluşturucuda sağlanan kritik bölüm serbest bırakır.

```
~scoped_lock();
```

##  <a name="try_lock"></a> try_lock

Engellemeden kilit almaya çalışır.

```
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit alındıysa değeri **true**; Aksi takdirde, değeri **false**.

##  <a name="try_lock_for"></a> try_lock_for

Belirli bir milisaniye sayısı için engellemeden kilit almaya çalışır.

```
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>Parametreler

*_Zaman aşımı*<br/>
Zaman aşımından önce beklenecek milisaniye sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kilit alındıysa değeri **true**; Aksi takdirde, değeri **false**.

##  <a name="unlock"></a> Kilit açma

Kritik bölüm kilidini açar.

```
void unlock();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[reader_writer_lock Sınıfı](reader-writer-lock-class.md)
