---
title: reader_writer_lock Sınıfı
ms.date: 11/04/2016
f1_keywords:
- reader_writer_lock
- CONCRT/concurrency::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock_read
- CONCRT/concurrency::reader_writer_lock::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::lock
- CONCRT/concurrency::reader_writer_lock::lock_read
- CONCRT/concurrency::reader_writer_lock::try_lock
- CONCRT/concurrency::reader_writer_lock::try_lock_read
- CONCRT/concurrency::reader_writer_lock::unlock
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
ms.openlocfilehash: 13b44387f3e9489090ec31345fe4347ff5f205ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376250"
---
# <a name="reader_writer_lock-class"></a>reader_writer_lock Sınıfı

Yerel sadece iplik ile bir yazar-tercih sıra tabanlı okuyucu-yazar kilidi. Kilit ilk olarak verir - ilk çıkış (FIFO) yazarlar a erişim ve yazarların sürekli bir yük altında okuyucuları açlıktan.

## <a name="syntax"></a>Sözdizimi

```cpp
class reader_writer_lock;
```

## <a name="members"></a>Üyeler

### <a name="public-classes"></a>Genel Sınıflar

|Adı|Açıklama|
|----------|-----------------|
|[reader_writer_lock::scoped_lock Sınıfı](#scoped_lock_class)|Bir yazar olarak kilit nesneleri elde `reader_writer_lock` etmek için kullanılabilecek bir özel durum güvenli RAII sarıcı.|
|[reader_writer_lock::scoped_lock_read Sınıfı](#scoped_lock_read_class)|Bir okuyucu olarak kilit nesneleri elde `reader_writer_lock` etmek için kullanılabilecek bir özel durum güvenli RAII sarıcı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[reader_writer_lock](#ctor)|Yeni `reader_writer_lock` bir nesne oluşturuyor.|
|[~reader_writer_lock Yıkıcı](#dtor)|Nesneyi `reader_writer_lock` yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Kilit](#lock)|Bir yazar olarak okuyucu-yazar kilidi kazanır.|
|[lock_read](#lock_read)|Okuyucu-yazar kilidini okuyucu olarak edinir. Yazarlar varsa, aktif okuyucular onlar bitene kadar beklemek zorunda. Okuyucu sadece kilit bir ilgi kaydeder ve yazarlar serbest bırakmak için bekler.|
|[try_lock](#try_lock)|Engellemeden bir yazar olarak okuyucu-yazar kilidi elde etmeye çalışır.|
|[try_lock_read](#try_lock_read)|Engellemeden okuyucu-yazar kilidi elde etmeye çalışır.|
|[Kilidini](#unlock)|Okuyucu-yazar kilidini kimin kilitlediğini, okuyucuyu veya yazarı açar.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [bkz.](../../../parallel/concrt/synchronization-data-structures.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`reader_writer_lock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt.h

**Ad alanı:** eşzamanlılık

## <a name="lock"></a><a name="lock"></a>Kilit

Bir yazar olarak okuyucu-yazar kilidi kazanır.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Genellikle bir özel durum [scoped_lock](#scoped_lock_class) güvenli bir şekilde bir `reader_writer_lock` yazar olarak bir nesne elde etmek ve serbest bırakmak için scoped_lock yapı kullanmak daha güvenlidir.

Bir yazar kilidi elde etmeye çalıştıktan sonra, gelecekteki okuyucular, yazarlar kilidi başarıyla elde edip serbest bırakana kadar bunu engeller. Bu kilit yazarlara karşı önyargılı ve yazarların sürekli bir yük altında okuyucuları açlıktan olabilir.

Yazarlar zincirlenir, böylece kilitten çıkan bir yazar sıradaki yazarı serbest bırakır.

Kilit zaten arama bağlamında tutuluyorsa, [improper_lock](improper-lock-class.md) bir özel durum atılır.

## <a name="lock_read"></a><a name="lock_read"></a>lock_read

Okuyucu-yazar kilidini okuyucu olarak edinir. Yazarlar varsa, aktif okuyucular onlar bitene kadar beklemek zorunda. Okuyucu sadece kilit bir ilgi kaydeder ve yazarlar serbest bırakmak için bekler.

```cpp
void lock_read();
```

### <a name="remarks"></a>Açıklamalar

Genellikle bir özel durum [scoped_lock_read](#scoped_lock_read_class) güvenli bir şekilde bir `reader_writer_lock` nesne elde etmek ve bir okuyucu olarak serbest bırakmak için scoped_lock_read yapı kullanmak daha güvenlidir.

Kilitte bekleyen yazarlar varsa, okuyucu satırdaki tüm yazarlar kilidi alıp serbest bırakana kadar bekler. Bu kilit yazarlara karşı önyargılı ve yazarların sürekli bir yük altında okuyucuları açlıktan olabilir.

## <a name="reader_writer_lock"></a><a name="ctor"></a>reader_writer_lock

Yeni `reader_writer_lock` bir nesne oluşturuyor.

```cpp
reader_writer_lock();
```

## <a name="reader_writer_lock"></a><a name="dtor"></a>~reader_writer_lock

Nesneyi `reader_writer_lock` yok eder.

```cpp
~reader_writer_lock();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalışırken kilidin artık tutulmadığı beklenmektedir. Okuyucu yazar kilidi kilidi kilit ile imha izin hala tanımlanmamış davranış sonuçları düzenledi.

## <a name="reader_writer_lockscoped_lock-class"></a><a name="scoped_lock_class"></a>reader_writer_lock::scoped_lock Sınıfı

Bir yazar olarak kilit nesneleri elde `reader_writer_lock` etmek için kullanılabilecek bir özel durum güvenli RAII sarıcı.

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="scoped_lock_ctor"></a>scoped_lock::scoped_lock

Bir `scoped_lock` nesne inşa eder `reader_writer_lock` ve parametrede geçen nesneyi yazar olarak edinir. `_Reader_writer_lock` Kilit başka bir iş parçacığı tarafından tutulursa, bu çağrı engellenir.

```cpp
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>Parametreler

*_Reader_writer_lock*<br/>
Bir `reader_writer_lock` yazar olarak elde etmek için nesne.

## <a name="scoped_lockscoped_lock"></a><a name="scoped_lock_dtor"></a>scoped_lock::~scoped_lock

Bir `reader_writer_lock` nesneyi yok eder ve oluşturucusu yla birlikte verilen kilidi serbest bırakır.

```cpp
~scoped_lock();
```

## <a name="reader_writer_lockscoped_lock_read-class"></a><a name="scoped_lock_read_class"></a>reader_writer_lock::scoped_lock_read Sınıfı

Bir okuyucu olarak kilit nesneleri elde `reader_writer_lock` etmek için kullanılabilecek bir özel durum güvenli RAII sarıcı.

```cpp
class scoped_lock_read;
```

## <a name="scoped_lock_readscoped_lock_read"></a><a name="scoped_lock_read_ctor"></a>scoped_lock_read:scoped_lock_read

Bir `scoped_lock_read` nesne inşa eder `reader_writer_lock` ve parametrede geçen nesneyi okuyucu olarak edinir. `_Reader_writer_lock` Kilit yazar olarak başka bir iş parçacığı tarafından tutulursa veya bekleyen yazarlar varsa, bu çağrı engellenir.

```cpp
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>Parametreler

*_Reader_writer_lock*<br/>
Okuyucu `reader_writer_lock` olarak elde etmek için nesne.

## <a name="a-namescoped_lock_read_dtor--reader_writer_lockscoped_lock_readscoped_lock_read-destructor"></a><a name="scoped_lock_read_dtor">reader_writer_lock::scoped_lock_read::~scoped_lock_read Yıkıcı

Bir `scoped_lock_read` nesneyi yok eder ve oluşturucusu yla birlikte verilen kilidi serbest bırakır.

```cpp
~scoped_lock_read();
```

## <a name="try_lock"></a><a name="try_lock"></a>try_lock

Engellemeden bir yazar olarak okuyucu-yazar kilidi elde etmeye çalışır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit elde edildiyse, değer **doğru;** aksi takdirde, değer **yanlış**.

## <a name="try_lock_read"></a><a name="try_lock_read"></a>try_lock_read

Engellemeden okuyucu-yazar kilidi elde etmeye çalışır.

```cpp
bool try_lock_read();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit elde edildiyse, değer **doğru;** aksi takdirde, değer **yanlış**.

## <a name="unlock"></a><a name="unlock"></a>Kilidini

Okuyucu-yazar kilidini kimin kilitlediğini, okuyucuyu veya yazarı açar.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Kilitte bekleyen yazarlar varsa, kilidin serbest bırakılması her zaman FIFO sırasına göre bir sonraki yazara gider. Bu kilit yazarlara karşı önyargılı ve yazarların sürekli bir yük altında okuyucuları açlıktan olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[critical_section Sınıfı](critical-section-class.md)
