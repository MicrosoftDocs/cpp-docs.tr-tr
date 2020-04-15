---
title: thread Sınıfı
ms.date: 11/04/2016
f1_keywords:
- thread/std::thread
- thread/std::thread::id Class
- thread/std::thread::thread
- thread/std::thread::detach
- thread/std::thread::get_id
- thread/std::thread::hardware_concurrency
- thread/std::thread::join
- thread/std::thread::joinable
- thread/std::thread::native_handle
- thread/std::thread::swap
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
helpviewer_keywords:
- std::thread [C++]
- std::thread [C++], thread
- std::thread [C++], detach
- std::thread [C++], get_id
- std::thread [C++], hardware_concurrency
- std::thread [C++], join
- std::thread [C++], joinable
- std::thread [C++], native_handle
- std::thread [C++], swap
ms.openlocfilehash: 13996a8ec4ab56fc56a78606d1a2ce8d76994c0d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375850"
---
# <a name="thread-class"></a>thread Sınıfı

Uygulama içindeki yürütme iş parçacığıgözlemlemek ve yönetmek için kullanılan bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class thread;
```

## <a name="remarks"></a>Açıklamalar

Bir uygulama içinde yürütme iş parçacığı gözlemlemek ve yönetmek için bir **iş parçacığı** nesnesi kullanabilirsiniz. Varsayılan oluşturucu kullanılarak oluşturulan bir iş parçacığı nesnesi herhangi bir yürütme iş parçacığı ile ilişkili değildir. Çağrılabilir bir nesne kullanılarak oluşturulmuş bir iş parçacığı nesnesi, yeni bir yürütme iş parçacığı oluşturur ve bu iş parçacığındaki çağrılabilir nesneyi çağırır. İş parçacığı nesneleri taşınabilir, ancak kopyalanamaz. Bu nedenle, yürütme iş parçacığı yalnızca bir iş parçacığı nesnesi ile ilişkili olabilir.

Yürütme her iş parçacığı türü `thread::id`benzersiz bir tanımlayıcı vardır. İşlev, `this_thread::get_id` çağrı iş parçacığının tanımlayıcısını döndürür. Üye işlev, `thread::get_id` iş parçacığı nesnesi tarafından yönetilen iş parçacığının tanımlayıcısını döndürür. Varsayılan olarak oluşturulmuş iş parçacığı `thread::get_id` nesnesi için yöntem, tüm varsayılan olarak oluşturulmuş iş parçacığı nesneleri için aynı değere `this_thread::get_id` sahip ve çağrı sırasında birleşebilecek herhangi bir yürütme iş parçacığı için döndürülen değerden farklı bir nesneyi döndürür.

## <a name="members"></a>Üyeler

### <a name="public-classes"></a>Genel Sınıflar

|Adı|Açıklama|
|----------|-----------------|
|[konu::id Sınıf](#id_class)|İlişkili iş parçacığı benzersiz olarak tanımlar.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[thread](#thread)|Bir **iş parçacığı nesnesi** oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Ayırmak](#detach)|İlişkili iş parçacığı **nesnesinden** ayrılır.|
|[get_id](#get_id)|İlişkili iş parçacığının benzersiz tanımlayıcısını döndürür.|
|[hardware_concurrency](#hardware_concurrency)|Statik. Donanım iş parçacığı bağlamlarının sayısının tahminini verir.|
|[Katılın](#join)|İlişkili iş parçacığı tamamlanana kadar engeller.|
|[katılabilir](#joinable)|İlişkili iş parçacığının birleştirilebilir olup olmadığını belirtir.|
|[native_handle](#native_handle)|İş parçacığı tanıtıcısını temsil eden uygulamaya özgü türü döndürür.|
|[Takas](#swap)|Nesne durumunu belirli bir **iş parçacığı** nesnesiyle değiştirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[iş parçacığı::operator=](#op_eq)|Bir iş parçacığı geçerli **iş parçacığı** nesnesi ile ilişkilendirer.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<iş parçacığı>

**Ad alanı:** std

## <a name="threaddetach"></a><a name="detach"></a>konu::detach

İlişkili iş parçacığı ayırır. İşletim sistemi, iş parçacığı kaynaklarını sonlandırma üzerine serbest bırakmakla yükümlü olur.

```cpp
void detach();
```

### <a name="remarks"></a>Açıklamalar

Bir çağrıdan `detach`sonra , [get_id](#get_id) iade [id](#id_class)sonraki aramalar .

Arama nesnesi ile ilişkili iş parçacığı birleştirilebilir değilse, işlev [system_error](../standard-library/system-error-class.md) `invalid_argument`hata kodu olan bir system_error atar.

Çağrı nesnesi ile ilişkili iş parçacığı geçersizse, işlev `system_error` bir hata kodu `no_such_process`olan .

## <a name="threadget_id"></a><a name="get_id"></a>konu::get_id

İlişkili iş parçacığı için benzersiz bir tanımlayıcı döndürür.

```cpp
id get_id() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlişkili iş parçacığıbenzersiz olarak tanımlayan veya `thread::id()` nesneyle ilişkili iş parçacığı yoksa iş [parçacığı::id](#id_class) nesnesi.

## <a name="threadhardware_concurrency"></a><a name="hardware_concurrency"></a>konu::hardware_concurrency

Donanım iş parçacığı bağlamlarının sayısının tahminini döndüren statik yöntem.

```cpp
static unsigned int hardware_concurrency() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Donanım iş parçacığı bağlamlarının sayısının tahmini. Değer hesaplanamıyorsa veya iyi tanımlanmıyorsa, bu yöntem 0 döndürür.

## <a name="threadid-class"></a><a name="id_class"></a>konu::id Sınıf

İşlemdeki her yürütme iş parçacığı için benzersiz bir tanımlayıcı sağlar.

```cpp
class thread::id {
    id() noexcept;
};
```

### <a name="remarks"></a>Açıklamalar

Varsayılan oluşturucu, varolan herhangi bir iş `thread::id` parçacığı için nesneye eşit karşılaştırma yapmayan bir nesne oluşturur.

Varsayılan olarak `thread::id` oluşturulmuş tüm nesneler eşit olarak karşılaştırılır.

## <a name="threadjoin"></a><a name="join"></a>iş parçacığı::join

Çağrı nesnesi ile ilişkili yürütme iş parçacığı tamamlanana kadar engeller.

```cpp
void join();
```

### <a name="remarks"></a>Açıklamalar

Arama başarılı olursa, çağrı nesnesi için [get_id](#get_id) sonraki çağrılar varsayılan bir iş parçacığı `thread::id` döndürün::id varolan iş parçacığı ile eşit karşılaştırmak değildir; [thread::id](#id_class) arama başarılı olmazsa, döndürülen `get_id` değer değişmez.

## <a name="threadjoinable"></a><a name="joinable"></a>iş parçacığı::joinable

İlişkili iş parçacığının *birleştirilebilir*olup olmadığını belirtir.

```cpp
bool joinable() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

ilişkili iş parçacığı *birleştirilebilir*ise **doğru** ; aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bir iş parçacığı nesnesi *birleştirilebilir,* eğer `get_id() != id()`.

## <a name="threadnative_handle"></a><a name="native_handle"></a>konu::native_handle

İş parçacığı tanıtıcısını temsil eden uygulamaya özgü türü döndürür. İş parçacığı tutamacı uygulamaya özgü yollarla kullanılabilir.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type`olarak kullanılan win32 `HANDLE` olarak `void *`tanımlanır.

## <a name="threadoperator"></a><a name="op_eq"></a>iş parçacığı::operator=

Belirtilen bir nesnenin iş parçacığı geçerli nesne ile ilişkilendirer.

```cpp
thread& operator=(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*\
Bir **iş parçacığı nesnesi.**

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Arama nesnesi birleştirilebilirse yöntem ayırma yı çağırır.

İlişkilendirme yapıldıktan `Other` sonra, varsayılan olarak oluşturulmuş bir duruma ayarlanır.

## <a name="threadswap"></a><a name="swap"></a>konu::takas

Nesne durumunu belirtilen bir iş **parçacığı** nesnesinindurumuyla değiştirir.

```cpp
void swap(thread& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*\
Bir **iş parçacığı nesnesi.**

## <a name="threadthread-constructor"></a><a name="thread"></a>konu::thread Constructor

Bir **iş parçacığı nesnesi** oluşturuyor.

```cpp
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*F*\
İş parçacığı tarafından yürütülecek uygulama tanımlı bir işlev.

*A*\
*F'ye*geçirilecek bağımsız değişkenlerin listesi.

*Diğer*\
Varolan bir **iş parçacığı nesnesi.**

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu yürütme iş parçacığı ile ilişkili olmayan bir nesne inşa eder. Yapılandırılan nesne için `get_id` yapılan bir çağrı yla `thread::id()`döndürülen değer.

İkinci oluşturucu, yeni bir yürütme iş parçacığıyla ilişkili bir nesne inşa `INVOKE` eder ve [ \<işlevsel>](../standard-library/functional.md)tanımlanan sözde işlevi yürütür. Yeni bir iş parçacığı başlatmak için yeterli kaynak yoksa, işlev hata kodu `resource_unavailable_try_again`olan bir [system_error](../standard-library/system-error-class.md) nesnesi atar. *F* çağrısı yakalanmamış bir özel durumla sona ererse, [sonlandırma](../standard-library/exception-functions.md#terminate) denir.

Üçüncü oluşturucu, iş parçacığı ile `Other`ilişkili bir nesne inşa eder. `Other`sonra varsayılan olarak oluşturulmuş bir duruma ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<iş parçacığı>](../standard-library/thread.md)
