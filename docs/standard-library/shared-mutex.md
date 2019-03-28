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
ms.openlocfilehash: 97d77399357030feaa90228a1b0cdeb80d48034c
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565392"
---
# <a name="ltsharedmutex"></a>&lt;shared_mutex >

&lt;Shared_mutex > üst bilgi, birden çok iş parçacığı tarafından erişilebilen paylaşılan bir veri koruma için eşitleme temellerine sağlar. Mutex sınıfı tarafından sağlanan özel erişim denetimine ek olarak, paylaşılan bir mutex sınıfları paylaşılan sahipliği münhasır olmayan erişim için birden çok iş parçacığı tarafından da sağlar. Paylaşılan mutex'leri bir yarış durumu neden olmadan birkaç iş parçacığı tarafından okunabilir ancak özel olarak tek bir iş parçacığı tarafından yazılan kaynakları denetlemek için kullanılabilir.

Üst bilgi &lt;shared_mutex > sınıfları tanımlar `shared_mutex` ve `shared_timed_mutex`, Şablon sınıfı `shared_lock`ve şablon işlevi `swap` paylaşılan mutex desteği.

|Sınıflar|Açıklama|
|-------------|-----------------|
|[shared_mutex sınıfı](#class_shared_mutex)|Bir aracı tarafından özel olarak kilitlenmiş veya özel olmayan birden çok aracı tarafından paylaşılan bir paylaşılan mutex türü.|
|[shared_timed_mutex sınıfı](#class_shared_timed_mutex)|Paylaşılan bir aracı tarafından özel olarak kilitlenmiş veya özel olmayan birden çok aracı tarafından paylaşılan mutex türünü zaman aşımına uğradı.|
|[shared_lock sınıfı](#class_shared_lock)|Zamanlanmış kilitleme işlemler ve birden çok aracı tarafından münhasır olmayan paylaşımı desteklemek için paylaşılan bir mutex sarmalayan bir şablon sınıfı.|

|İşlevler|Açıklama|
|---------------|-----------------|
|[değiştirme](#function_swap)|İşlev parametreleri tarafından başvurulan paylaşılan mutex nesnelerinin içeriğini değiştirir.|

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

Sınıfının bir örneğini `shared_mutex` olduğu bir *paylaşılan mutex türünü*, paylaşılan bir kapsam içinde bir mutex sahipliğini denetleyen bir tür. Paylaşılan mutex türünü paylaşılan münhasır olmayan sahipliği desteklemek için tüm gereksinimleri üyelerinin yanı sıra bir mutex türünü karşılar.

Paylaşılan mutex türünü ek yöntemleri destekler `lock_shared`, `unlock_shared`, ve `try_lock_shared`:

- `lock_shared` Yöntemi iş parçacığı mutex paylaşılan sahipliğini alana kadar çağıran iş parçacığını engeller.

- `unlock_shared` Yöntemi çağıran iş parçacığı tarafından tutulan mutex paylaşılan sahipliğini serbest bırakır.

- `try_lock_shared` Yöntemi engellemeden mutex paylaşılan sahipliğini almayı dener. Kendi dönüş türüne dönüştürülebilir **bool** ve **true** yöntemi sahipliğini alır, ancak aksi **false**.

Sınıf `shared_timed_mutex` olduğu bir *paylaşılan zamanlanmış mutex türünü*, her ikisi de gereksinimlerini karşılayan bir paylaşılan bir mutex türünü ve zamanlanmış bir mutex yazın.

Ek yöntemleri bir paylaşılan zamanlanmış mutex türünü destekler `try_lock_shared_for` ve `try_lock_shared_until`:

- `try_lock_shared_for` Yöntemi parametresi ile belirtilen süre bitene kadar mutex paylaşılan sahipliğini almayı dener. Süre pozitif değil ise, yöntem değerine eşdeğer olan `try_lock_shared`. Yöntemi, Paylaşılan sahiplik alındıktan sürece belirtilen süre içinde döndürmez. Dönüş değeri **true** yöntemi sahipliğini alır, ancak aksi **false**.

- `try_lock_shared_until` Yöntemi belirtilen mutlak süre bitene kadar mutex paylaşılan sahipliğini almayı dener. Yöntemi, belirtilen zaman zaten geçtiyse, eşdeğer olan `try_lock_shared`. Sahipliği paylaşılan sürece belirtilen süre edinmenizden önce yöntemin döndürmez. Dönüş değeri **true** yöntemi sahipliğini alır, ancak aksi **false**.

`shared_lock` Şablon sınıfı, kilitleme ve sahipliğin aktarılması için paylaşılan bir mutex zaman aşımına için desteği genişletir. Mutex sahipliğini ya yapım sonrasındaki alınabilir ve başka aktarılamayacağını `shared_lock` nesne. Türündeki nesneler `shared_lock` taşınabilir, ancak kopyalanamaz.

> [!WARNING]
> Visual Studio 2015'te başlayarak, C++ Standart Kitaplığı eşitleme türleri üzerinde Windows eşitleme temellerine temel alır ve artık ConcRT (hedef platformu Windows XP olduğunda hariç) kullanın. İçinde tanımlanmış türlere &lt;shared_mutex > herhangi bir ConcRT türleri ve işlevleri ile birlikte kullanılmamalıdır.

## <a name="classes"></a>Sınıflar

###  <a name="class_shared_mutex"></a> shared_mutex sınıfı

Sınıf `shared_mutex` paylaşılan sahipliği semantiğine sahip bir özyinelemeli olmayan mutex uygular.

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

Sınıf `shared_timed_mutex` zamanlanmış mutex türünün gereksinimlerini karşılayan paylaşılan sahipliği semantiğine sahip bir özyinelemeli olmayan mutex uygular.

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

###  <a name="class_shared_lock"></a> shared_lock sınıfı

Şablon sınıfı `shared_lock` paylaşılan mutex nesnesi bir kapsam içindeki paylaşılan sahipliğini denetler. Şablon parametresi paylaşılan mutex türünde olmalıdır.

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

###  <a name="function_swap"></a> değiştirme

Değiştirir `shared_lock` nesneleri.

```cpp
template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
```

İki içeriğini birbiriyle değiştirir `shared_lock` nesneleri. Etkili bir şekilde aynı `x.swap(y)`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** &lt;shared_mutex >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[&lt;Mutex >](../standard-library/mutex.md)
