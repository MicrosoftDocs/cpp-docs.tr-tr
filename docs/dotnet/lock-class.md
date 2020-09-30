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
ms.openlocfilehash: 7b2f187ec940af95523d0bbfb9265d7d9d6f69e8
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508650"
---
# <a name="lock-class"></a>lock Sınıfı

Bu sınıf, birkaç iş parçacığından bir nesneye erişimi eşitlemek için bir kilit almayı otomatikleştirir.  Oluşturulduğunda kilidi devralır ve yok edildiğinde kilidi bırakır.

## <a name="syntax"></a>Sözdizimi

```cpp
ref class lock;
```

## <a name="remarks"></a>Açıklamalar

`lock` yalnızca CLR nesnelerinde kullanılabilir ve yalnızca CLR kodunda kullanılabilir.

Dahili olarak, kilit sınıfı <xref:System.Threading.Monitor> erişimi eşzamanlı hale getirmek için kullanır. Daha fazla bilgi için, başvurulan makaleye bakın.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak oluşturucular

|Ad|Açıklama|
|---------|-----------|
|[lock::lock](#lock)|`lock`İsteğe bağlı olarak, belirli bir süre boyunca kilidi sonsuza kadar almayı bekleyen veya hiç değil, bir nesne oluşturur.|
|[Lock:: ~ Lock](#tilde-lock)|Bir nesne yapıları kaldırır `lock` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|---------|-----------|
|[lock::acquire](#acquire)|Bir nesne üzerinde bir kilit alır, isteğe bağlı olarak, belirli bir süre boyunca kilidi sonsuza kadar almayı bekler veya hiç değil.|
|[lock::is_locked](#is-locked)|Bir kilidin tutulmakta olup olmadığını gösterir.|
|[lock::release](#release)|Bir kilit yayınlar.|
|[lock::try_acquire](#try-acquire)|Bir nesne üzerinde bir kilit alır, belirli bir süre bekler ve bir **`bool`** özel durum oluşturmak yerine alma başarısını raporlamak için bir döndürür.|

### <a name="public-operators"></a>Ortak işleçler

|Ad|Açıklama|
|---------|-----------|
|[Lock:: operator &nbsp; bool](#operator-bool)|`lock`Bir koşullu ifadede kullanmak için işleci.|
|[Lock:: operator = =](#operator-equality)|Eşitlik işleci.|
|[lock::operator!=](#operator-inequality)|Eşitsizlik işleci.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası**\<msclr\lock.h>

**Ad alanı** msclr

## <a name="locklock"></a><a name="lock"></a> Lock:: Lock

`lock`İsteğe bağlı olarak, belirli bir süre boyunca kilidi sonsuza kadar almayı bekleyen veya hiç değil, bir nesne oluşturur.

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
Milisaniye veya olarak zaman aşımı değeri <xref:System.TimeSpan> .

### <a name="exceptions"></a>Özel durumlar

<xref:System.ApplicationException>Kilit alma zaman aşımından önce gerçekleşmiyorsa atar.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun ilk üç formu, `_object` belirtilen zaman aşımı süresi içinde (veya <xref:System.Threading.Timeout.Infinite> hiçbiri belirtilmemişse) bir kilit almaya çalışır.

Oluşturucunun dördüncü formu, üzerinde bir kilit elde etmez `_object` . `lock_later`[lock_when numaralandırmasının](../dotnet/lock-when-enum.md)bir üyesidir. Bu durumda kilidi almak için [Lock:: Acquire](#acquire) veya [lock:: try_acquire](#try-acquire) kullanın.

Yok edicisi çağrıldığında kilit otomatik olarak serbest bırakılır.

`_object` olamaz <xref:System.Threading.ReaderWriterLock> .  Bu ise, bir derleyici hatası ortaya kalır.

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı üzerinde bir sınıfın tek bir örneğini kullanır. Sınıfı, iç verilerine erişimin her iş parçacığı için tutarlı olduğundan emin olmak için kendi üzerinde bir kilit kullanır. Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığının hala mevcut olup olmadığını denetlemek için düzenli aralıklarla kontrol etmek üzere sınıfının aynı örneğinde bir kilit kullanır. Ana uygulama daha sonra tüm çalışan iş parçacıkları görevlerini tamamlayana kadar çıkış olarak bekler.

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

## <a name="locklock"></a><a name="tilde-lock"></a> Lock:: ~ Lock

Bir nesne yapıları kaldırır `lock` .

```cpp
~lock();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı [Lock:: Release](#release)öğesini çağırır.

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı üzerinde bir sınıfın tek bir örneğini kullanır.  Sınıfı, iç verilerine erişimin her iş parçacığı için tutarlı olduğundan emin olmak için kendi üzerinde bir kilit kullanır.  Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığının hala mevcut olup olmadığını denetlemek için düzenli aralıklarla kontrol etmek üzere sınıfının aynı örneğinde bir kilit kullanır. Ana uygulama daha sonra tüm çalışan iş parçacıkları görevlerini tamamlayana kadar çıkış olarak bekler.

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

## <a name="lockacquire"></a><a name="acquire"></a> Lock:: Acquire

Bir nesne üzerinde bir kilit alır, isteğe bağlı olarak, belirli bir süre boyunca kilidi sonsuza kadar almayı bekler veya hiç değil.

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
Milisaniye cinsinden veya olarak zaman aşımı değeri <xref:System.TimeSpan> .

### <a name="exceptions"></a>Özel durumlar

<xref:System.ApplicationException>Kilit alma zaman aşımından önce gerçekleşmiyorsa atar.

### <a name="remarks"></a>Açıklamalar

Bir zaman aşımı değeri sağlanmazsa, varsayılan zaman aşımı olur <xref:System.Threading.Timeout.Infinite> .

Bir kilit zaten alınırsa, bu işlev hiçbir şey yapmaz.

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı üzerinde bir sınıfın tek bir örneğini kullanır.  Sınıfı, iç verilerine erişimin her iş parçacığı için tutarlı olduğundan emin olmak için kendi üzerinde bir kilit kullanır. Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığının hala mevcut olup olmadığını denetlemek için düzenli aralıklarla kontrol etmek üzere sınıfının aynı örneğinde bir kilit kullanır. Ana uygulama daha sonra tüm çalışan iş parçacıkları görevlerini tamamlayana kadar çıkış olarak bekler.

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

## <a name="lockis_locked"></a><a name="is-locked"></a> Kilit:: is_locked

Bir kilidin tutulmakta olup olmadığını gösterir.

```cpp
bool is_locked();
```

### <a name="return-value"></a>Döndürülen değer

**`true`** bir kilit tutuluyorsa, **`false`** tersi durumda.

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı üzerinde bir sınıfın tek bir örneğini kullanır.  Sınıfı, iç verilerine erişimin her iş parçacığı için tutarlı olduğundan emin olmak için kendi üzerinde bir kilit kullanır.  Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığının hala mevcut olup olmadığını denetlemek için bir kilit kullanır ve tüm çalışan iş parçacıkları görevlerini tamamlayana kadar çıkış ' ı bekler.

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

## <a name="lockoperator-bool"></a><a name="operator-bool"></a> Lock:: operator bool

`lock`Bir koşullu ifadede kullanmak için işleci.

```cpp
operator bool();
```

### <a name="return-value"></a>Döndürülen değer

**`true`** bir kilit tutuluyorsa, **`false`** tersi durumda.

### <a name="remarks"></a>Açıklamalar

Bu işleç gerçekten `_detail_class::_safe_bool` , **`bool`** bir integral türüne dönüştürülemediğinden daha güvenli olan öğesine dönüştürür.

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı üzerinde bir sınıfın tek bir örneğini kullanır.  Sınıfı, iç verilerine erişimin her iş parçacığı için tutarlı olduğundan emin olmak için kendi üzerinde bir kilit kullanır. Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığının hala mevcut olup olmadığını denetlemek için düzenli aralıklarla kontrol etmek üzere sınıfının aynı örneğinde bir kilit kullanır. Ana uygulama, tüm çalışan iş parçacıkları görevlerini tamamlayana kadar çıkış yapmak için bekler.

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

## <a name="lockrelease"></a><a name="release"></a> Lock:: Release

Bir kilit yayınlar.

```cpp
void release();
```

### <a name="remarks"></a>Açıklamalar

Kilit tutulmadığında `release` hiçbir şey yapmaz.

Bu işlevi açıkça çağırmanız gerekmez. Bir `lock` nesne kapsam dışına geçtiğinde, yıkıcısı çağırır `release` .

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı üzerinde bir sınıfın tek bir örneğini kullanır. Sınıfı, iç verilerine erişimin her iş parçacığı için tutarlı olduğundan emin olmak için kendi üzerinde bir kilit kullanır. Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığının hala mevcut olup olmadığını denetlemek için düzenli aralıklarla kontrol etmek üzere sınıfının aynı örneğinde bir kilit kullanır. Ana uygulama daha sonra tüm çalışan iş parçacıkları görevlerini tamamlayana kadar çıkış olarak bekler.

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

## <a name="locktry_acquire"></a><a name="try-acquire"></a> Kilit:: try_acquire

Bir nesne üzerinde bir kilit alır, belirli bir süre bekler ve bir **`bool`** özel durum oluşturmak yerine alma başarısını raporlamak için bir döndürür.

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
Milisaniye cinsinden veya olarak zaman aşımı değeri <xref:System.TimeSpan> .

### <a name="return-value"></a>Döndürülen değer

**`true`** kilit alınırsa, **`false`** tersi durumda.

### <a name="remarks"></a>Açıklamalar

Bir kilit zaten alınırsa, bu işlev hiçbir şey yapmaz.

### <a name="example"></a>Örnek

Bu örnek, birkaç iş parçacığı üzerinde bir sınıfın tek bir örneğini kullanır. Sınıfı, iç verilerine erişimin her iş parçacığı için tutarlı olduğundan emin olmak için kendi üzerinde bir kilit kullanır. Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığının hala mevcut olup olmadığını denetlemek için düzenli aralıklarla kontrol etmek üzere sınıfının aynı örneğinde bir kilit kullanır. Ana uygulama daha sonra tüm çalışan iş parçacıkları görevlerini tamamlayana kadar çıkış olarak bekler.

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

## <a name="lockoperator"></a><a name="operator-equality"></a> Lock:: operator = =

Eşitlik işleci.

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
Eşitlik için Karşılaştırılacak nesne.

### <a name="return-value"></a>Döndürülen değer

**`true`** `t` Kilit nesnesiyle aynı ise, **`false`** Aksi takdirde döndürür.

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

## <a name="lockoperator"></a><a name="operator-inequality"></a> Lock:: operator! =

Eşitsizlik işleci.

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
Eşitsizlik için Karşılaştırılacak nesne.

### <a name="return-value"></a>Döndürülen değer

**`true`** `t` Kilit nesnesinden farklıysa, **`false`** Aksi takdirde döndürür.

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
