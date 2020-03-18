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
ms.openlocfilehash: 1a7386e527b5327d928bfdcb3281c88666f1b106
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417126"
---
# <a name="reader_writer_lock-class"></a>reader_writer_lock Sınıfı

Yalnızca yerel olarak dönen bir yazıcı tercihi kuyruğu tabanlı okuyucu-yazıcı kilidi. Kilit, sürekli bir yazıcı yüklemesi altında yazıcılara ve başlangıç okuyucularına ilk çıkar (FıFO) erişimi verir.

## <a name="syntax"></a>Sözdizimi

```cpp
class reader_writer_lock;
```

## <a name="members"></a>Üyeler

### <a name="public-classes"></a>Ortak sınıflar

|Name|Açıklama|
|----------|-----------------|
|[reader_writer_lock:: scoped_lock sınıfı](#scoped_lock_class)|Bir yazıcı olarak `reader_writer_lock` kilitleme nesneleri elde etmek için kullanılabilen özel durum güvenli bir KAıı sarmalayıcısı.|
|[reader_writer_lock:: scoped_lock_read sınıfı](#scoped_lock_read_class)|Bir okuyucu olarak `reader_writer_lock` kilitleme nesneleri elde etmek için kullanılabilen özel durum güvenli bir KAıı sarmalayıcısı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[reader_writer_lock](#ctor)|Yeni bir `reader_writer_lock` nesnesi oluşturur.|
|[~ reader_writer_lock yok edici](#dtor)|`reader_writer_lock` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[lock](#lock)|Okuyucu-yazıcı kilidini bir yazıcı olarak alır.|
|[lock_read](#lock_read)|Reader-yazıcı kilidini okuyucu olarak alır. Yazıcılar varsa, etkin okuyucular tamamlanana kadar beklemelidir. Okuyucu yalnızca kilit için bir ilgi kaydeder ve yazarların bunu serbest bırakmasını bekler.|
|[try_lock](#try_lock)|Okuyucu-yazıcı kilidini engelleme olmadan bir yazıcı olarak almayı dener.|
|[try_lock_read](#try_lock_read)|Reader-yazıcı kilidini engellemeye gerek kalmadan okuyucu olarak almayı dener.|
|[kaldırın](#unlock)|It, Reader veya Writer 'ın kimin kilitlemesine göre okuyucu yazıcı kilidi 'nin kilidini açar.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [eşitleme veri yapıları](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`reader_writer_lock`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="lock"></a>ine

Okuyucu-yazıcı kilidini bir yazıcı olarak alır.

```cpp
void lock();
```

### <a name="remarks"></a>Açıklamalar

Özel durum güvenli bir şekilde bir `reader_writer_lock` nesnesini bir yazıcı olarak almak ve serbest bırakmak için [scoped_lock](#scoped_lock_class) yapısını kullanmak genellikle daha güvenlidir.

Bir yazıcı kilidi edinmeye çalıştıktan sonra, yazarları başarılı bir şekilde alıp serbest bırakılana kadar gelecek okuyucular bu işlemleri engeller. Bu kilit, yazıcılara sahiptir ve sürekli bir yazıcı yüklemesi altında okuyucuları açabilir.

Yazıcılar zincirdir, böylece kilidi çıkış sonrasında bir yazıcı, satırdaki sonraki yazıcıya serbest bırakır.

Kilit çağıran bağlam tarafından zaten tutuluyorsa, bir [improper_lock](improper-lock-class.md) özel durumu oluşturulur.

## <a name="lock_read"></a>lock_read

Reader-yazıcı kilidini okuyucu olarak alır. Yazıcılar varsa, etkin okuyucular tamamlanana kadar beklemelidir. Okuyucu yalnızca kilit için bir ilgi kaydeder ve yazarların bunu serbest bırakmasını bekler.

```cpp
void lock_read();
```

### <a name="remarks"></a>Açıklamalar

Özel durum güvenli bir şekilde bir `reader_writer_lock` nesnesini okuyucu olarak almak ve serbest bırakmak için [scoped_lock_read](#scoped_lock_read_class) yapısını kullanmak genellikle daha güvenlidir.

Kilit üzerinde bekleyen yazıcılar varsa, bu, satırdaki tüm yazarlar elde edilene ve kilidi serbest bırakılana kadar bekler. Bu kilit, yazıcılara sahiptir ve sürekli bir yazıcı yüklemesi altında okuyucuları açabilir.

## <a name="ctor"></a>reader_writer_lock

Yeni bir `reader_writer_lock` nesnesi oluşturur.

```cpp
reader_writer_lock();
```

## <a name="dtor"></a>~ reader_writer_lock

`reader_writer_lock` nesnesini yok eder.

```cpp
~reader_writer_lock();
```

### <a name="remarks"></a>Açıklamalar

Yok edicinin çalıştırıldığı zaman kilidin artık tutulmuyor olması beklenmektedir. Okuyucu Yazıcı kilidinin kilit ile sınıfların 'a geçmesine izin, tanımsız davranışa neden olur.

## <a name="scoped_lock_class"></a>reader_writer_lock:: scoped_lock sınıfı

Bir yazıcı olarak `reader_writer_lock` kilitleme nesneleri elde etmek için kullanılabilen özel durum güvenli bir KAıı sarmalayıcısı.

```cpp
class scoped_lock;
```

## <a name="scoped_lock_ctor"></a>scoped_lock:: scoped_lock

`scoped_lock` nesnesi oluşturur ve `_Reader_writer_lock` parametresinde geçirilen `reader_writer_lock` nesnesini bir yazıcı olarak alır. Kilit başka bir iş parçacığı tarafından tutuluyorsa bu çağrı engellenir.

```cpp
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>Parametreler

*_Reader_writer_lock*<br/>
Bir yazıcı olarak elde edilecek `reader_writer_lock` nesnesi.

## <a name="scoped_lock_dtor"></a>scoped_lock:: ~ scoped_lock

`reader_writer_lock` nesnesini yok eder ve yapıcısında sağlanan kilidi serbest bırakır.

```cpp
~scoped_lock();
```

## <a name="scoped_lock_read_class"></a>reader_writer_lock:: scoped_lock_read sınıfı

Bir okuyucu olarak `reader_writer_lock` kilitleme nesneleri elde etmek için kullanılabilen özel durum güvenli bir KAıı sarmalayıcısı.

```cpp
class scoped_lock_read;
```

## <a name="scoped_lock_read_ctor"></a>scoped_lock_read:: scoped_lock_read

Bir `scoped_lock_read` nesnesi oluşturur ve `_Reader_writer_lock` parametresinde geçirilen `reader_writer_lock` nesnesini okuyucu olarak alır. Kilit başka bir iş parçacığı tarafından bir yazıcı olarak tutuluyorsa veya bekleyen yazıcılar varsa, bu çağrı engellenir.

```cpp
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>Parametreler

*_Reader_writer_lock*<br/>
Okuyucu olarak elde edilecek `reader_writer_lock` nesnesi.

## <a name="a-namescoped_lock_read_dtor--reader_writer_lockscoped_lock_readscoped_lock_read-destructor"></a><a name="scoped_lock_read_dtor"> reader_writer_lock:: scoped_lock_read:: ~ scoped_lock_read yok edici

`scoped_lock_read` nesnesini yok eder ve yapıcısında sağlanan kilidi serbest bırakır.

```cpp
~scoped_lock_read();
```

## <a name="try_lock"></a>try_lock

Okuyucu-yazıcı kilidini engelleme olmadan bir yazıcı olarak almayı dener.

### <a name="syntax"></a>Sözdizimi

```cpp
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit alınırsa, **true**değeri; Aksi takdirde, değeri **false**olur.

## <a name="try_lock_read"></a>try_lock_read

Reader-yazıcı kilidini engellemeye gerek kalmadan okuyucu olarak almayı dener.

```cpp
bool try_lock_read();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit alınırsa, **true**değeri; Aksi takdirde, değeri **false**olur.

## <a name="unlock"></a>kaldırın

It, Reader veya Writer 'ın kimin kilitlemesine göre okuyucu yazıcı kilidi 'nin kilidini açar.

```cpp
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Kilit üzerinde bekleyen yazıcılar varsa, kilit sürümü her zaman FıFO düzeninde bir sonraki yazıcıya gider. Bu kilit, yazıcılara sahiptir ve sürekli bir yazıcı yüklemesi altında okuyucuları açabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[critical_section Sınıfı](critical-section-class.md)
