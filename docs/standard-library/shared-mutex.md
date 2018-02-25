---
title: '&lt;shared_mutex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <shared_mutex>
- shared_mutex/std::swap
- shared_mutex/std::shared_lock
- shared_mutex/std::shared_lock::shared_lock
- shared_mutex/std::shared_lock::operator=
- shared_mutex/std::shared_lock::operator =
- shared_mutex/std::shared_lock::lock
- shared_mutex/std::shared_lock::try_lock
- shared_mutex/std::shared_lock::try_lock_for
- shared_mutex/std::shared_lock::try_lock_until
- shared_mutex/std::shared_lock::unlock
- shared_mutex/std::shared_lock::swap
- shared_mutex/std::shared_lock::release
- shared_mutex/std::shared_lock::owns_lock
- shared_mutex/std::shared_lock::operator bool
- shared_mutex/std::shared_lock::mutex
- shared_mutex/std::shared_mutex
- shared_mutex/std::shared_mutex::native_handle_type
- shared_mutex/std::shared_mutex::shared_mutex
- shared_mutex/std::shared_mutex::operator=
- shared_mutex/std::shared_mutex::operator =
- shared_mutex/std::shared_mutex::lock
- shared_mutex/std::shared_mutex::try_lock
- shared_mutex/std::shared_mutex::unlock
- shared_mutex/std::shared_mutex::lock_shared
- shared_mutex/std::shared_mutex::try_lock_shared
- shared_mutex/std::shared_mutex::unlock_shared
- shared_mutex/std::shared_mutex::native_handle
- shared_mutex/std::shared_timed_mutex
- shared_mutex/std::shared_timed_mutex::shared_timed_mutex
- shared_mutex/std::shared_timed_mutex::operator=
- shared_mutex/std::shared_timed_mutex::operator =
- shared_mutex/std::shared_timed_mutex::lock
- shared_mutex/std::shared_timed_mutex::try_lock
- shared_mutex/std::shared_timed_mutex::try_lock_for
- shared_mutex/std::shared_timed_mutex::try_lock_until
- shared_mutex/std::shared_timed_mutex::unlock
- shared_mutex/std::shared_timed_mutex::lock_shared
- shared_mutex/std::shared_timed_mutex::try_lock_shared
- shared_mutex/std::shared_timed_mutex::try_lock_shared_for
- shared_mutex/std::shared_timed_mutex::try_lock_shared_until
- shared_mutex/std::shared_timed_mutex::unlock_shared
dev_langs:
- C++
ms.assetid: 0b37a97d-ee5d-4050-b29f-09db9f76beb3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f7d657a95822d66d34a6173cc775f99c80411f12
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltsharedmutex"></a>&lt;shared_mutex>

&lt;Shared_mutex > üstbilgisi eşitleme temelleri birden çok iş parçacığı tarafından erişilebilen paylaşılan veri koruması sağlar. Mutex sınıfı tarafından sağlanan özel erişim denetimi ek olarak, paylaşılan mutex sınıfları ayrıca paylaşılan sahipliği özel olmayan erişim için birden çok iş parçacığı tarafından izin verin. Paylaşılan zaman uyumu sağlayıcılar tarafından birkaç iş parçacığı bir yarış durumu neden olmadan okuyabilir, ancak yalnızca tek bir iş parçacığı tarafından yazılmış kaynakları denetlemek için kullanılabilir.

Üstbilgi &lt;shared_mutex > sınıflarını tanımlayan `shared_mutex` ve `shared_timed_mutex`, Şablon sınıfı `shared_lock`ve şablon işlevi `swap` paylaşılan mutex desteği.

|Sınıflar|Açıklama|
|-------------|-----------------|
|[shared_mutex Class](../standard-library/shared-mutex.md#class_shared_mutex)|Özel olarak bir aracı tarafından kilitlenmiş ya da birden çok aracı tarafından yalnızca harici paylaşılan paylaşılan mutex türü.|
|[shared_timed_mutex Class](../standard-library/shared-mutex.md#class_shared_timed_mutex)|Özel olarak bir aracı tarafından kilitlenmiş ya da birden çok aracı tarafından yalnızca harici paylaşılan mutex türü paylaşılan zaman aşımına uğradı.|
|[shared_lock sınıfı](../standard-library/shared-mutex.md#class_shared_lock)|Zamanlanmış kilitleme işlemleri ve özel olmayan birden çok aracı tarafından paylaşımı desteklemek için paylaşılan bir mutex saran bir şablon sınıfı.|

|İşlevler|Açıklama|
|---------------|-----------------|
|[Değiştirme](../standard-library/shared-mutex.md#function_swap)|İşlev parametreleri tarafından başvurulan paylaşılan mutex nesnelerinin içeriğini değiştirir.|

## <a name="syntax"></a>Sözdizimi

```cpp
namespace std {
    class shared_mutex;
    class shared_timed_mutex;
    template <class Mutex>
class shared_lock;
    template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
}
```

## <a name="remarks"></a>Açıklamalar

Sınıfının bir örneği `shared_mutex` olan bir *paylaşılan mutex türünü*, kapsam içinde mutex paylaşılan sahipliğini denetleyen bir türü. Bir paylaşılan mutex türü paylaşılan özel olmayan sahipliği desteklemek için tüm gereksinimleri, üyeleri yanı sıra bir mutex türü karşılar.

Bir paylaşılan mutex türü ek yöntemleri destekler `lock_shared`, `unlock_shared`, ve `try_lock_shared`:

- `lock_shared` Yöntemini çağıran iş parçacığı iş parçacığı mutex paylaşılan sahipliğini alıncaya kadar engeller.

- `unlock_shared` Yöntemini çağıran iş parçacığı tarafından tutulan mutex paylaşılan sahipliğini serbest bırakır.

- `try_lock_shared` Yöntemi çalıştığında engellenmeden mutex paylaşılan sahipliğini elde edilir. Dönüş türü dönüştürülebilir `bool` ve `true` yöntemi sahipliği alır, ancak aksi `false`.

Sınıf `shared_timed_mutex` olan bir *paylaşılan zamanlanmış mutex türünü*, her ikisi de gereksinimlerini karşılayan bir tür paylaşılan mutex ve zaman aşımına mutex yazın.

Bir paylaşılan zamanlanmış mutex türü ek yöntemleri destekler `try_lock_shared_for` ve `try_lock_shared_until`:

- `try_lock_shared_for` Yöntemi çalışır parametresi tarafından belirtilen süresi geçene kadar mutex paylaşılan sahipliğini elde edilir. Süre pozitif değilse yöntemi eşdeğerdir `try_lock_shared`. Yöntemi, paylaşılan sahipliğini elde sürece belirtilen süre içinde döndürmüyor. Dönüş değeri olduğu `true` yöntemi sahipliği alır, ancak aksi `false`.

- `try_lock_shared_until` Yöntemi, belirtilen mutlak süresi geçene kadar mutex paylaşılan sahipliğini almak çalışır. Belirtilen süre zaten geçtiyse, eşdeğer yöntemdir `try_lock_shared`. Sahipliği paylaşılan sürece belirtilen süre elde önce yöntemi döndürmüyor. Dönüş değeri olduğu `true` yöntemi sahipliği alır, ancak aksi `false`.

`shared_lock` Şablon sınıfı kilitleme ve paylaşılan mutex sahipliği aktarımını zaman aşımına desteği genişletir. Sırasında veya sonrasında yapım alınabilir ve başka aktarılabileceği mutex sahipliğini `shared_lock` nesnesi. Nesne türü `shared_lock` taşınabilir ancak kopyalanmadı.

> [!WARNING]
> Visual Studio 2015'te başlayarak, C++ Standart Kitaplığı eşitleme türleri Windows eşitleme temelleri dayanır ve artık ConcRT (hedef platformu Windows XP olduğunda dışında) kullanın. Tanımlanan türleri &lt;shared_mutex > tüm ConcRT türlerin veya işlevlerin kullanılmamalıdır.

## <a name="classes"></a>Sınıflar

###  <a name="class_shared_mutex"></a> shared_mutex sınıfı

Sınıf `shared_mutex` paylaşılan sahipliği semantiği ile özyinelemeli olmayan mutex uygular.

```cpp
class shared_mutex {
public:
   shared_mutex();
   ~shared_mutex();
   shared_mutex(const shared_mutex&) = delete;
   shared_mutex& operator=(const shared_mutex&) = delete;
   // Exclusive ownership
   void lock();
   // blocking
   bool try_lock();
   void unlock();
   // Shared ownership
   void lock_shared();
   // blocking
   bool try_lock_shared();
   void unlock_shared();
   // Getters
   typedef void** native_handle_type; // implementation defined
   native_handle_type native_handle();
   };
```

###  <a name="class_shared_timed_mutex"></a> shared_timed_mutex sınıfı

Sınıf `shared_timed_mutex` zamanlanmış mutex türü gereksinimlerini karşılayan paylaşılan sahipliği semantiği ile özyinelemeli olmayan mutex uygular.

```cpp
class shared_timed_mutex {
public:
   shared_timed_mutex();
   ~shared_timed_mutex();
   shared_timed_mutex(const shared_timed_mutex&) = delete;
   shared_timed_mutex& operator=(const shared_timed_mutex&) = delete;
   // Exclusive ownership
   void lock();
   // blocking
   bool try_lock();
   template <class Rep, class Period>
   bool try_lock_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock();
   // Shared ownership
   void lock_shared();
   // blocking
   bool try_lock_shared();
   template <class Rep, class Period>
   bool try_lock_shared_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_shared_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock_shared();
   };
```

###  <a name="&lt;shared">shared_lock sınıfı</a>

Şablon sınıfı `shared_lock` paylaşılan mutex nesnesi bir kapsamdaki paylaşılan sahipliğini denetler. Şablon parametresi paylaşılan mutex türünden olmalıdır.

```cpp
class shared_lock {
public:
   typedef Mutex mutex_type;
   shared_lock() noexcept;
   explicit shared_lock(mutex_type& m);
   // blocking
   shared_lock(mutex_type& m, defer_lock_t) noexcept;
   shared_lock(mutex_type& m, try_to_lock_t);
   shared_lock(mutex_type& m, adopt_lock_t);
   template <class Clock, class Duration>
   shared_lock(mutex_type& m,
   const chrono::time_point<Clock, Duration>& abs_time);
   template <class Rep, class Period>
   shared_lock(mutex_type& m,
   const chrono::duration<Rep, Period>& rel_time);
   ~shared_lock();
   shared_lock(shared_lock const&) = delete;
   shared_lock& operator=(shared_lock const&) = delete;
   shared_lock(shared_lock&& u) noexcept;
   shared_lock& operator=(shared_lock&& u) noexcept;
   void lock();
   // blocking
   bool try_lock();
   template <class Rep, class Period>
   bool try_lock_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock();
   // Setters
   void swap(shared_lock& u) noexcept;
   mutex_type* release() noexcept;
   // Getters
   bool owns_lock() const noexcept;
   explicit operator bool () const noexcept;
   mutex_type* mutex() const noexcept;
private:
   mutex_type* pm; // exposition only
   bool owns; // exposition only
   };
```

## <a name="functions"></a>İşlevler

###  <a name="function_swap">Değiştirme</a>

Değiştirir `shared_lock` nesneleri.

```cpp
template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
```

İki içeriğini alış verişleri `shared_lock` nesneleri. Etkili bir şekilde aynı `x.swap(y)`.

## <a name="requirements"></a>Gereksinimler

 **Başlık:** &lt;shared_mutex >

 **Namespace:** std

## <a name="see-also"></a>Ayrıca Bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)  
[&lt;mutex>](../standard-library/mutex.md)
