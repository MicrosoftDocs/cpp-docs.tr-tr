---
title: lock Sınıfı
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::lock::lock
- msclr::lock::is_locked
- msclr::lock.is_locked
- msclr::lock::acquire
- msclr::lock::try_acquire
- msclr::lock::release
- msclr::lock::operator==
- msclr::lock::operator!=
helpviewer_keywords:
- msclr::lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
ms.openlocfilehash: ea09dd3d4a2eaf4cf7708d09509cfecfa4a6c6d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373073"
---
# <a name="lock-class"></a>lock Sınıfı

Bu sınıf, bir nesneye erişimi çeşitli iş parçacığından eşitlemek için kilitalmayı otomatikleştirir.  İnşa edildiğinde kilidi edinir ve yok edildiğinde kilidi serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```cpp
ref class lock;
```

## <a name="remarks"></a>Açıklamalar

`lock`yalnızca CLR nesneleri için kullanılabilir ve yalnızca CLR kodunda kullanılabilir.

Dahili olarak, kilit <xref:System.Threading.Monitor> sınıfı erişimi eşitlemek için kullanır. Daha fazla bilgi için başvurulan makaleye bakın.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Kamu yapıcılar

|Adı|Açıklama|
|---------|-----------|
|[lock::lock](#lock)|Belirli bir `lock` süre için kilidi sonsuza kadar elde etmek için isteğe bağlı olarak bekleyen bir nesne veya hiç oluşturmaz.|
|[kilit::~kilit](#tilde-lock)|Bir `lock` nesneyi yok eder.|

### <a name="public-methods"></a>Genel yöntemler

|Adı|Açıklama|
|---------|-----------|
|[lock::acquire](#acquire)|Belirli bir süre için, isteğe bağlı olarak kilidi sonsuza kadar elde etmek için bekleyen bir nesne üzerinde bir kilit kazanır.|
|[lock::is_locked](#is-locked)|Kilidin tutulup tutulmadığını gösterir.|
|[lock::release](#release)|Bir kilit salgılar.|
|[lock::try_acquire](#try-acquire)|Belirli bir süre yi bekleyen ve bir özel durum yerine `bool` edinme başarısını bildirmek için bir nesne üzerinde kilit kazanır.|

### <a name="public-operators"></a>Kamu operatörleri

|Adı|Açıklama|
|---------|-----------|
|[kilit::operatör&nbsp;bool](#operator-bool)|Koşullu `lock` bir ifadede kullanmak için işleç.|
|[kilit::operator==](#operator-equality)|Eşitlik operatörü.|
|[lock::operator!=](#operator-inequality)|Eşitsizlik operatörü.|

## <a name="requirements"></a>Gereksinimler

**Başlık dosyası** \<msclr\lock.h>

**Namespace** msclr

## <a name="locklock"></a><a name="lock"></a>kilit::kilit

Belirli bir `lock` süre için kilidi sonsuza kadar elde etmek için isteğe bağlı olarak bekleyen bir nesne veya hiç oluşturmaz.

```cpp
template<class T> lock(
   T ^ _object
);
template<class T> lock(
   T ^ _object,
   int _timeout
);
template<class T> lock(
   T ^ _object,
   System::TimeSpan _timeout
);
template<class T> lock(
   T ^ _object,
   lock_later
);
```

### <a name="parameters"></a>Parametreler

*_object*<br/>
Kilitlenecek nesne.

*_timeout*<br/>
Milisaniye cinsinden veya bir <xref:System.TimeSpan>.

### <a name="exceptions"></a>Özel durumlar

<xref:System.ApplicationException> Zaman aramadan önce kilit edinimi gerçekleşmezse atar.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun ilk üç biçimi, belirtilen zaman `_object` anına (veya <xref:System.Threading.Timeout.Infinite> hiçbiri belirtilmemişse) kilit almaya çalışır.

Yapıcının dördüncü formu kilitlenmez. `_object` `lock_later`[lock_when enum](../dotnet/lock-when-enum.md)üyesidir. Bu durumda kilidi elde etmek için [kilit::acquire](../dotnet/lock-acquire.md) veya [lock::try_acquire](../dotnet/lock-try-acquire.md) kullanın.

Yıkıcı çağrıldığında kilit otomatik olarak serbest bırakılır.

`_object`<xref:System.Threading.ReaderWriterLock>olamaz.  Varsa, derleyici hatası neden olur.

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı arasında bir sınıfın tek bir örneğini kullanır. Sınıf, kendi iç verilerine erişenher iş parçacığı için tutarlı olduğundan emin olmak için kendisi üzerinde bir kilit kullanır. Ana uygulama iş parçacığı, herhangi bir alt iş parçacığı hala var olup olmadığını görmek için periyodik olarak kontrol etmek için sınıfın aynı örneğinde bir kilit kullanır. Ana uygulama daha sonra tüm alt iş parçacıkları görevlerini tamamlayana kadar çıkmak için bekler.

```cpp
// msl_lock_lock.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="locklock"></a><a name="tilde-lock"></a>kilit::~kilit

Bir `lock` nesneyi yok eder.

```cpp
~lock();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı [kilit çağırır::release](../dotnet/lock-release.md).

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı arasında bir sınıfın tek bir örneğini kullanır.  Sınıf, kendi iç verilerine erişenher iş parçacığı için tutarlı olduğundan emin olmak için kendisi üzerinde bir kilit kullanır.  Ana uygulama iş parçacığı, herhangi bir alt iş parçacığı hala var olup olmadığını görmek için periyodik olarak kontrol etmek için sınıfın aynı örneğinde bir kilit kullanır. Ana uygulama daha sonra tüm alt iş parçacıkları görevlerini tamamlayana kadar çıkmak için bekler.

```cpp
// msl_lock_dtor.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockacquire"></a><a name="acquire"></a>kilit::edinme

Belirli bir süre için, isteğe bağlı olarak kilidi sonsuza kadar elde etmek için bekleyen bir nesne üzerinde bir kilit kazanır.

```cpp
void acquire();
void acquire(
   int _timeout
);
void acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>Parametreler

*_timeout*<br/>
Milisaniye cinsinden veya bir <xref:System.TimeSpan>.

### <a name="exceptions"></a>Özel durumlar

<xref:System.ApplicationException> Zaman aramadan önce kilit edinimi gerçekleşmezse atar.

### <a name="remarks"></a>Açıklamalar

Bir zaman açıkçı değeri sağlanmazsa, varsayılan zaman süreyi. <xref:System.Threading.Timeout.Infinite>

Bir kilit zaten elde edilmişse, bu işlev hiçbir şey yapmaz.

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı arasında bir sınıfın tek bir örneğini kullanır.  Sınıf, kendi iç verilerine erişenher iş parçacığı için tutarlı olduğundan emin olmak için kendisi üzerinde bir kilit kullanır. Ana uygulama iş parçacığı, herhangi bir alt iş parçacığı hala var olup olmadığını görmek için periyodik olarak kontrol etmek için sınıfın aynı örneğinde bir kilit kullanır. Ana uygulama daha sonra tüm alt iş parçacıkları görevlerini tamamlayana kadar çıkmak için bekler.

```cpp
// msl_lock_acquire.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockis_locked"></a><a name="is-locked"></a>kilit::is_locked

Kilidin tutulup tutulmadığını gösterir.

```cpp
bool is_locked();
```

### <a name="return-value"></a>Döndürülen değer

`true`bir kilit tutulursa, `false` aksi takdirde.

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı arasında bir sınıfın tek bir örneğini kullanır.  Sınıf, kendi iç verilerine erişenher iş parçacığı için tutarlı olduğundan emin olmak için kendisi üzerinde bir kilit kullanır.  Ana uygulama iş parçacığı, herhangi bir alt iş parçacığı nın hala var olup olmadığını düzenli olarak denetlemek için sınıfın aynı örneğinde bir kilit kullanır ve tüm alt iş parçacıkları görevlerini tamamlayana kadar çıkmak için bekler.

```cpp
// msl_lock_is_locked.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l.is_locked()) { // check if we got the lock
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockoperator-bool"></a><a name="operator-bool"></a>kilit::operatör bool

Koşullu `lock` bir ifadede kullanmak için işleç.

```cpp
operator bool();
```

### <a name="return-value"></a>Döndürülen değer

`true`bir kilit tutulursa, `false` aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu işleç aslında `_detail_class::_safe_bool` integral türüne dönüştürülemez çünkü daha `bool` güvenli olan dönüştürür.

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı arasında bir sınıfın tek bir örneğini kullanır.  Sınıf, kendi iç verilerine erişenher iş parçacığı için tutarlı olduğundan emin olmak için kendisi üzerinde bir kilit kullanır. Ana uygulama iş parçacığı, herhangi bir alt iş parçacığı hala var olup olmadığını görmek için periyodik olarak kontrol etmek için sınıfın aynı örneğinde bir kilit kullanır. Ana uygulama, tüm alt iş parçacıkları görevlerini tamamlayana kadar çıkmak için bekler.

```cpp
// msl_lock_op_bool.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l) { // use bool operator to check for lock
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockrelease"></a><a name="release"></a>kilit::serbest bırakma

Bir kilit salgılar.

```cpp
void release();
```

### <a name="remarks"></a>Açıklamalar

Kilit tutulmuyorsa, `release` hiçbir şey yapmaz.

Bu işlevi açıkça aramanız gerekmez. Bir `lock` nesne kapsam dışına çıktığında, yıkıcı sı. `release`

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı arasında bir sınıfın tek bir örneğini kullanır. Sınıf, kendi iç verilerine erişenher iş parçacığı için tutarlı olduğundan emin olmak için kendisi üzerinde bir kilit kullanır. Ana uygulama iş parçacığı, herhangi bir alt iş parçacığı hala var olup olmadığını görmek için periyodik olarak kontrol etmek için sınıfın aynı örneğinde bir kilit kullanır. Ana uygulama daha sonra tüm alt iş parçacıkları görevlerini tamamlayana kadar çıkmak için bekler.

```cpp
// msl_lock_release.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="locktry_acquire"></a><a name="try-acquire"></a>kilit::try_acquire

Belirli bir süre yi bekleyen ve bir özel durum yerine `bool` edinme başarısını bildirmek için bir nesne üzerinde kilit kazanır.

```cpp
bool try_acquire(
   int _timeout_ms
);
bool try_acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>Parametreler

*_timeout*<br/>
Milisaniye cinsinden veya bir <xref:System.TimeSpan>.

### <a name="return-value"></a>Döndürülen değer

`true`kilit elde edildiyse, `false` aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bir kilit zaten elde edilmişse, bu işlev hiçbir şey yapmaz.

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı arasında bir sınıfın tek bir örneğini kullanır. Sınıf, kendi iç verilerine erişenher iş parçacığı için tutarlı olduğundan emin olmak için kendisi üzerinde bir kilit kullanır. Ana uygulama iş parçacığı, herhangi bir alt iş parçacığı hala var olup olmadığını görmek için periyodik olarak kontrol etmek için sınıfın aynı örneğinde bir kilit kullanır. Ana uygulama daha sonra tüm alt iş parçacıkları görevlerini tamamlayana kadar çıkmak için bekler.

```cpp
// msl_lock_try_acquire.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockoperator"></a><a name="operator-equality"></a>kilit::operator==

Eşitlik operatörü.

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşitlik için karşılaştırılması gereken nesne.

### <a name="return-value"></a>Döndürülen değer

Kilit `true` `t` nesnesi ile aynıysa, `false` aksi takdirde döndürür.

### <a name="example"></a>Örnek

```cpp
// msl_lock_op_eq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   lock l1(o1);
   if (l1 == o1) {
      Console::WriteLine("Equal!");
   }
}
```

```Output
Equal!
```

## <a name="lockoperator"></a><a name="operator-inequality"></a>kilit::operatör!=

Eşitsizlik operatörü.

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşitsizlik için karşılaştırılacak nesne.

### <a name="return-value"></a>Döndürülen değer

Kilidin `t` nesnesinden farklıysa, `false` aksi takdirde döndürür. `true`

### <a name="example"></a>Örnek

```cpp
// msl_lock_op_ineq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   Object^ o2 = gcnew Object;
   lock l1(o1);
   if (l1 != o2) {
      Console::WriteLine("Inequal!");
   }
}
```

```Output
Inequal!
```
