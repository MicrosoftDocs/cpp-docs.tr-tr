---
title: '&lt;shared_mutex&gt;'
ms.date: 03/27/2019
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
ms.assetid: 0b37a97d-ee5d-4050-b29f-09db9f76beb3
ms.openlocfilehash: 7dd72550bc8658158b399e88573526269202f8f4
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450430"
---
# <a name="ltsharedmutex"></a>&lt;shared_mutex >

Shared_mutex &lt;> üstbilgisi, birden çok iş parçacığı tarafından erişilebilen paylaşılan verilerin korunması için eşitleme temelleri sağlar. Karşılıklı dışlama sınıfları tarafından sunulan özel erişim denetimine ek olarak, paylaşılan mutex sınıfları Ayrıca, özel olmayan erişim için birden çok iş parçacığı tarafından paylaşılan sahiplik sağlar. Paylaşılan zaman uyumu sağlayıcılar, bir yarış durumuna neden olmadan birçok iş parçacığı tarafından okunabilen kaynakları denetlemek için kullanılabilir, ancak tek bir iş parçacığı tarafından özel olarak yazılması gerekir.

Üst bilgi &lt;shared_mutex >, sınıfları `shared_mutex` ve `shared_timed_mutex`, şablon sınıfını `shared_lock`ve paylaşılan mutex desteği için şablon işlevini `swap` tanımlar.

|Sınıflar|Açıklama|
|-------------|-----------------|
|[shared_mutex sınıfı](#class_shared_mutex)|Yalnızca bir aracı tarafından kilitlenen veya birden çok aracı tarafından özel olarak paylaşılabilen paylaşılan bir mutex türü.|
|[shared_timed_mutex sınıfı](#class_shared_timed_mutex)|Yalnızca bir aracı tarafından kilitlenen veya birden çok aracı tarafından özel olarak paylaşılabilen paylaşılan zaman uyumsuz bir mutex türü.|
|[shared_lock sınıfı](#class_shared_lock)|Zaman uyumsuz kilitleme işlemlerini ve çoklu aracıların özel olmayan paylaşımını desteklemek için paylaşılan bir mutex 'i sarmalayan bir şablon sınıfı.|

|İşlevler|Açıklama|
|---------------|-----------------|
|[Kur](#function_swap)|İşlev parametrelerinin başvurduğu paylaşılan mutex nesnelerinin içeriğini değiştirir.|

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

Sınıfının `shared_mutex` bir örneği, bir kapsam içindeki bir mutex 'in paylaşılan sahipliğini denetleyen bir tür olan *paylaşılan bir mutex türüdür*. Paylaşılan bir mutex türü, bir mutex türünün tüm gereksinimlerini ve ayrıca paylaşılan özel olmayan sahipliği desteklemeye yönelik üyeleri karşılar.

Paylaşılan bir mutex türü, ve `lock_shared` `try_lock_shared`ek yöntemleri `unlock_shared`destekler:

- `lock_shared` Yöntemi, iş parçacığı, mutex 'in paylaşılan sahipliğini edinene kadar çağıran iş parçacığını engeller.

- `unlock_shared` Yöntemi, çağıran iş parçacığı tarafından tutulan mutex 'in paylaşılan sahipliğini yayınlar.

- `try_lock_shared` Yöntemi, karşılıklı mutex 'in paylaşılan sahipliğini engelleme olmadan almaya çalışır. Dönüş türü **bool** değerine dönüştürülebilir ve Yöntem sahipliği alırsa **true** , değilse **false 'tur**.

Sınıfı `shared_timed_mutex` , hem paylaşılan bir mutex türünün hem de zaman uyumu türünün gereksinimlerini karşılayan bir tür olan *paylaşılan bir zaman uyumu türüdür*.

Paylaşılan bir zaman uyumu türü, ek yöntemleri `try_lock_shared_for` ve `try_lock_shared_until`şunları destekler:

- `try_lock_shared_for` Yöntemi, parametre tarafından belirtilen süre geçtikten sonra mutex 'in paylaşılan sahipliğini almaya çalışır. Süre pozitif değilse, yöntemi değerine `try_lock_shared`eşdeğerdir. Bu yöntem, paylaşılan sahiplik alınmadıysa belirtilen süre içinde döndürmüyor. Yöntemi sahiplik alırsa, aksi durumda **false**ise dönüş değeri **doğrudur** .

- `try_lock_shared_until` Yöntemi, belirtilen mutlak süre geçtikten sonra mutex 'in paylaşılan sahipliğini almaya çalışır. Belirtilen saat zaten geçmişse, yöntemi değerine `try_lock_shared`eşdeğerdir. Bu yöntem, paylaşılan sahiplik alınmadığı takdirde belirtilen süreden önce döndürmez. Yöntemi sahiplik alırsa, aksi durumda **false**ise dönüş değeri **doğrudur** .

Şablon `shared_lock` sınıfı, paylaşılan bir mutex 'e zaman zaman kilitleme ve sahiplik aktarma desteğini genişletir. Mutex 'in sahipliği, oluşturma sırasında veya sonrasında elde edilebilir ve başka bir `shared_lock` nesneye aktarılabilir. Türündeki `shared_lock` nesneler taşınabilir, ancak kopyalanamayabilir.

> [!WARNING]
> Visual Studio 2015 ' den başlayarak C++ standart kitaplık eşitleme türleri Windows eşitleme temel temellerine dayalıdır ve artık ConcRT kullanmaz (hedef platformun Windows XP olduğu durumlar dışında). &lt;Shared_mutex > tanımlı türler, herhangi bir ConcRT türü veya işlevleriyle kullanılmamalıdır.

## <a name="classes"></a>Sınıflar

###  <a name="class_shared_mutex"></a>shared_mutex sınıfı

Sınıf `shared_mutex` , paylaşılan sahiplik semantiğinin özyinelemeli olmayan bir mutex 'i uygular.

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

###  <a name="class_shared_timed_mutex"></a>shared_timed_mutex sınıfı

Sınıfı `shared_timed_mutex` , zaman uyumsuz bir mutex türünün gereksinimlerini karşılayan paylaşılan sahiplik semantiğinin özyinelemeli olmayan bir mutex 'i uygular.

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

###  <a name="class_shared_lock"></a>shared_lock sınıfı

Şablon sınıfı `shared_lock` , bir kapsam içindeki paylaşılan bir mutex nesnesinin paylaşılan sahipliğini denetler. Şablon parametresi, paylaşılan bir mutex türü olmalıdır.

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

###  <a name="function_swap"></a>Kur

`shared_lock` Nesneleri değiştirir.

```cpp
template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
```

İki `shared_lock` nesnenin içeriğini değiş tokuş eder. Etkin şekilde aynı `x.swap(y)`.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** &lt;shared_mutex >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[&lt;mutex >](../standard-library/mutex.md)
