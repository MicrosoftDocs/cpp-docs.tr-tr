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
ms.openlocfilehash: 5dfb0e858bb412daf159ee9efc7dcc13be690886
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336732"
---
# <a name="ltshared_mutex"></a>&lt;shared_mutex>

shared_mutex &lt;> üstbilgi, birden çok iş parçacığı tarafından erişilebilen paylaşılan verilerin korunması için eşitleme ilkel sağlar. Mutex sınıfları tarafından sağlanan özel erişim denetimine ek olarak, paylaşılan mutex sınıfları ayrıca münhasır olmayan erişim için birden çok iş parçacığı tarafından paylaşılan sahiplik sağlar. Paylaşılan mutexes bir yarış koşulu neden olmadan çeşitli iş parçacıkları tarafından okunabilir kaynakları denetlemek için kullanılabilir, ancak tek bir iş parçacığı tarafından yalnızca yazılmalıdır.

Üstbilgi &lt;shared_mutex> sınıfları `shared_mutex` `shared_timed_mutex`ve sınıf `shared_lock`şablonunu ve `swap` paylaşılan mutex desteği için şablon işlevini tanımlar.

|Sınıflar|Açıklama|
|-------------|-----------------|
|[shared_mutex Sınıfı](#class_shared_mutex)|Yalnızca bir aracı tarafından kilitlenebilen veya yalnızca birden çok aracı tarafından paylaşılabilen paylaşılan mutex türü.|
|[shared_timed_mutex Sınıfı](#class_shared_timed_mutex)|Yalnızca bir aracı tarafından kilitlenebilen veya yalnızca birden çok aracı tarafından paylaşılmayan paylaşılan zamanlanmış mutex türü.|
|[shared_lock Sınıfı](#class_shared_lock)|Zamanlanmış kilit işlemlerini ve birden çok aracı nın münhasır olmayan paylaşımını desteklemek için paylaşılan bir mutex'i saran bir sınıf şablonu.|

|İşlevler|Açıklama|
|---------------|-----------------|
|[Takas](#function_swap)|İşlev parametreleri tarafından başvurulan paylaşılan mutex nesnelerin içeriğini değiştirir.|

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

Sınıfın `shared_mutex` bir örneği paylaşılan bir *mutex türüdür*, bir kapsam içinde bir mutex paylaşılan sahipliğini denetleyen bir tür. Paylaşılan mutex türü, bir mutex türünün tüm gereksinimlerini ve paylaşılan münhasır olmayan mülkiyeti desteklemek için üyeleri karşılar.

Paylaşılan mutex türü ek `lock_shared`yöntemleri `unlock_shared`destekler `try_lock_shared`, ve:

- Yöntem, `lock_shared` iş parçacığı mutex paylaşılan sahipliğini elde edene kadar arama iş parçacığı engeller.

- Yöntem, `unlock_shared` çağrı iş parçacığı tarafından tutulan mutex paylaşılan sahipliğini serbest bırakır.

- Yöntem `try_lock_shared` engellemeden mutex paylaşılan sahipliğini elde etmeye çalışır. Onun dönüş türü **bool** dönüştürülebilir ve yöntem sahipliğini elde ederse **doğrudur,** ancak aksi takdirde **yanlıştır**.

Sınıf `shared_timed_mutex` paylaşılan *zamanlanmış mutex türüdür,* paylaşılan mutex türü ve zamanlanmış mutex türü hem gereksinimlerini karşılayan bir türüdür.

Paylaşılan zamanlanmış mutex türü ek `try_lock_shared_for` `try_lock_shared_until`yöntemleri destekler ve:

- Yöntem, `try_lock_shared_for` parametre tarafından belirtilen süre geçene kadar mutex'in ortak sahipliğini elde etmeye çalışır. Süre pozitif değilse, yöntem `try_lock_shared`. Ortak sahiplik elde edilmedikçe yöntem belirtilen süre içinde geri dönmez. Yöntem sahipliği ni elde ederse, ancak başka **false**bir şekilde yanlışsa, iade değeri **doğrudur.**

- Yöntem, `try_lock_shared_until` belirtilen mutlak süre geçene kadar mutex'in ortak sahipliğini elde etmeye çalışır. Belirtilen süre zaten geçmişse, `try_lock_shared`yöntem . Ortak sahiplik elde edilmedikçe yöntem belirtilen süreden önce dönmez. Yöntem sahipliği ni elde ederse, ancak başka **false**bir şekilde yanlışsa, iade değeri **doğrudur.**

Sınıf `shared_lock` şablonu, zamanlanmış kilitleme ve sahipliğin paylaşılan bir mutex'e aktarılması için desteği genişletir. Mutex'in mülkiyeti inşaatta veya inşaattan sonra elde `shared_lock` edilebilir ve başka bir nesneye aktarılabilir. Tür `shared_lock` nesneleri taşınabilir, ancak kopyalanamaz.

> [!WARNING]
> Visual Studio 2015'ten itibaren, C++ Standart Kitaplık eşitleme türleri Windows senkronizasyon ilkellerine dayanır ve artık ConcRT kullanmaz (hedef platform Windows XP hariç). &lt;shared_mutex> tanımlanan türler herhangi bir ConcRT türü veya işlevi ile kullanılmamalıdır.

## <a name="classes"></a>Sınıflar

### <a name="shared_mutex-class"></a><a name="class_shared_mutex"></a>shared_mutex Sınıfı

Sınıf, `shared_mutex` paylaşılan sahiplik semantiklerine sahip özyinelemeli olmayan bir mutex uygular.

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

### <a name="shared_timed_mutex-class"></a><a name="class_shared_timed_mutex"></a>shared_timed_mutex Sınıfı

Sınıf, `shared_timed_mutex` zamanlanmış mutex türünün gereksinimlerini karşılayan paylaşılan sahiplik semantiklerine sahip özyinelemeli olmayan bir mutex uygular.

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

### <a name="shared_lock-class"></a><a name="class_shared_lock"></a>shared_lock Sınıfı

Sınıf `shared_lock` şablonu, bir kapsam içinde paylaşılan bir mutex nesnesinin paylaşılan sahipliğini denetler. Şablon parametresi paylaşılan bir mutex türü olmalıdır.

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

### <a name="swap"></a><a name="function_swap"></a>Takas

`shared_lock` Nesneleri değiştirir.

```cpp
template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
```

İki `shared_lock` nesnenin içeriğini değiştirir. Etkili olarak `x.swap(y)`aynı .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** &lt;shared_mutex>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[&lt;mutex>](../standard-library/mutex.md)
