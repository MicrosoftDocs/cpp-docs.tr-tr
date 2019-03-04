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
ms.openlocfilehash: 111d48b9c4a575078f2342bfaa944871bbd628f5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268661"
---
# <a name="readerwriterlock-class"></a>reader_writer_lock Sınıfı

Dönen yalnızca yerel yazıcı tercih kuyruk tabanlı Okuyucu-Yazıcı kilidi. Kilit ilk yazıcılarının - ilk (FIFO) erişimi verir ve yazıcılar sürekli bir yük altında okuyucular starves.

## <a name="syntax"></a>Sözdizimi

```
class reader_writer_lock;
```

## <a name="members"></a>Üyeler

### <a name="public-classes"></a>Genel sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[reader_writer_lock::scoped_lock sınıfı](#scoped_lock_class)|Almak için kullanılan bir özel durum güvenli RAII sarmalayıcı `reader_writer_lock` yazarı olarak nesneleri kilitleme.|
|[reader_writer_lock::scoped_lock_read sınıfı](#scoped_lock_read_class)|Almak için kullanılan bir özel durum güvenli RAII sarmalayıcı `reader_writer_lock` okuyucu olarak nesneleri kilitleme.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[reader_writer_lock](#ctor)|Yeni bir oluşturur `reader_writer_lock` nesne.|
|[~ reader_writer_lock yok Edicisi](#dtor)|Yok eder `reader_writer_lock` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lock](#lock)|Okuyucu-Yazıcı kilidi yazarı olarak alır.|
|[lock_read](#lock_read)|Okuyucu-Yazıcı kilidi okuyucu olarak alır. Yazıcılar varsa, etkin okuyucular aldıkları kadar beklemesi gerekir. Okuyucu, yalnızca bir kilit ilgiden kaydeder ve yazarlar, serbest bırakmak için bekler.|
|[try_lock](#try_lock)|Okuyucu-Yazıcı yazarı olarak engellemeden kilit dener.|
|[try_lock_read](#try_lock_read)|Okuyucu-Yazıcı okuyucu olarak engellemeden kilit dener.|
|[Kilit açma](#unlock)|Okuyucu-Yazıcı kilidi kimin bunu, okuyucuya veya yazara kilitli üzerinde temel kilidini açar.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [eşitleme veri yapıları](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`reader_writer_lock`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="lock"></a> Kilit

Okuyucu-Yazıcı kilidi yazarı olarak alır.

```
void lock();
```

### <a name="remarks"></a>Açıklamalar

Yazılımınız genellikle güvenlidir [scoped_lock](#scoped_lock_class) almak ve yayın yapısı bir `reader_writer_lock` nesnesi bir yazıcı bir özel durum olarak güvenli bir yoludur.

Bir yazıcı kilidi almak denemeden sonra gelecek herhangi okuyucular yazıcılar başarıyla alındı ve kilidi serbest kadar engeller. Bu kilit yazıcılar doğru güçlü eğilimi nedeniyle ve yazıcılar sürekli bir yük altında okuyucular yeterli kaynak kalmamasına neden.

Böylece satırdaki sonraki yazan bir yazıcı kilidi çıkmadan serbest yazıcılar zincirlenir.

Arayan girintileme kilidi zaten tutarsa bir [improper_lock](improper-lock-class.md) özel durumu oluşturulur.

##  <a name="lock_read"></a> lock_read

Okuyucu-Yazıcı kilidi okuyucu olarak alır. Yazıcılar varsa, etkin okuyucular aldıkları kadar beklemesi gerekir. Okuyucu, yalnızca bir kilit ilgiden kaydeder ve yazarlar, serbest bırakmak için bekler.

```
void lock_read();
```

### <a name="remarks"></a>Açıklamalar

Yazılımınız genellikle güvenlidir [scoped_lock_read](#scoped_lock_read_class) almak ve yayın yapısı bir `reader_writer_lock` nesnesi bir okuyucu bir özel durum olarak güvenli bir yoludur.

Kilit bekleyen yazıcılar varsa, okuyucu satırdaki tüm yazıcılar alınan ve kilidi serbest kadar bekler. Bu kilit yazıcılar doğru güçlü eğilimi nedeniyle ve yazıcılar sürekli bir yük altında okuyucular yeterli kaynak kalmamasına neden.

##  <a name="ctor"></a> reader_writer_lock

Yeni bir oluşturur `reader_writer_lock` nesne.

```
reader_writer_lock();
```

##  <a name="dtor"></a> ~ reader_writer_lock

Yok eder `reader_writer_lock` nesne.

```
~reader_writer_lock();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştığında kilit artık tutulan beklenmektedir. Okuyucu Yazar kilidi ile kilit yok etmek üzere izin verme hala sonuçlarını tanımsız davranışlara tutulan.

##  <a name="scoped_lock_class"></a>  reader_writer_lock::scoped_lock sınıfı

Almak için kullanılan bir özel durum güvenli RAII sarmalayıcı `reader_writer_lock` yazarı olarak nesneleri kilitleme.

```
class scoped_lock;
```

## <a name="scoped_lock_ctor"></a> scoped_lock::scoped_lock

Oluşturur bir `scoped_lock` alır ve nesne `reader_writer_lock` geçirilen nesne `_Reader_writer_lock` parametre olarak bir yazıcı. Kilit başka bir iş parçacığı tarafından yapılmazsa, bu çağrı engeller.

```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```

#### <a name="parameters"></a>Parametreler

*_Reader_writer_lock*<br/>
`reader_writer_lock` Yazarı olarak almak için nesne.

## <a name="scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock

Yok eder bir `reader_writer_lock` nesne ve onun oluşturucuda sağlanan kilidi serbest bırakır.

```
~scoped_lock();
```

##  <a name="scoped_lock_read_class"></a>  reader_writer_lock::scoped_lock_read sınıfı

Almak için kullanılan bir özel durum güvenli RAII sarmalayıcı `reader_writer_lock` okuyucu olarak nesneleri kilitleme.

```
class scoped_lock_read;
```

##  <a name="try_lock"></a> try_lock

Okuyucu-Yazıcı yazarı olarak engellemeden kilit dener.

## <a name="scoped_lock_read_ctor"></a> scoped_lock_read::scoped_lock_read

Oluşturur bir `scoped_lock_read` alır ve nesne `reader_writer_lock` geçirilen nesne `_Reader_writer_lock` parametre olarak bir okuyucu. Başka bir iş parçacığı olarak bir yazıcı kilidi açık tutulduğu veya yazıcılar vardır, bu çağrı engeller.

```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```

#### <a name="parameters"></a>Parametreler

*_Reader_writer_lock*<br/>
`reader_writer_lock` Okuyucu olarak almak için nesne.

## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">  reader_writer_lock::scoped_lock_read:: ~ scoped_lock_read yok Edicisi

Yok eder bir `scoped_lock_read` nesne ve onun oluşturucuda sağlanan kilidi serbest bırakır.

```
~scoped_lock_read();
```

## <a name="try_lock"></a> try_lock

```
bool try_lock();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit alındıysa değeri **true**; Aksi takdirde, değeri **false**.

##  <a name="try_lock_read"></a> try_lock_read

Okuyucu-Yazıcı okuyucu olarak engellemeden kilit dener.

```
bool try_lock_read();
```

### <a name="return-value"></a>Dönüş Değeri

Kilit alındıysa değeri **true**; Aksi takdirde, değeri **false**.

##  <a name="unlock"></a> Kilit açma

Okuyucu-Yazıcı kilidi kimin bunu, okuyucuya veya yazara kilitli üzerinde temel kilidini açar.

```
void unlock();
```

### <a name="remarks"></a>Açıklamalar

Kilit bekleyen yazıcılar varsa, kilit sürümü her zaman sonraki yazıcı FIFO sırayla geçer. Bu kilit yazıcılar doğru güçlü eğilimi nedeniyle ve yazıcılar sürekli bir yük altında okuyucular yeterli kaynak kalmamasına neden.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[critical_section Sınıfı](critical-section-class.md)
