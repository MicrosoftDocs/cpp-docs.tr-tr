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
ms.openlocfilehash: 43418da36aa2d87608a9d672e4345d24011be0b3
ms.sourcegitcommit: 9813e146a4eb30929d8352872859e8fcb7ff6d2f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54805961"
---
# <a name="lock-class"></a>lock Sınıfı

Bu sınıf, erişim, çeşitli iş parçacıklarından nesneyi eşitlemek için bir kilit almayı otomatikleştirir.  Oluşturulan, kilit alır ve yayınlar kaldırıldığında kilidi.

## <a name="syntax"></a>Sözdizimi

```cpp
ref class lock;
```

## <a name="remarks"></a>Açıklamalar

`lock` yalnızca CLR nesneler için kullanılabilir ve yalnızca CLR kod içinde kullanılabilir.

Dahili olarak, kilit sınıfı kullanır <xref:System.Threading.Monitor> erişimi eşitlemek için. Daha fazla bilgi için başvurulan makalesine bakın.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel oluşturucular

|Ad|Açıklama|
|---------|-----------|
|[lock::lock](#lock)|Oluşturur bir `lock` nesne, isteğe bağlı olarak her zaman, belirli bir süre süreyi veya hiç kilit bekleniyor.|
|[lock::~lock](#tilde-lock)|Destructs bir `lock` nesne.|

### <a name="public-methods"></a>Genel yöntemler

|Ad|Açıklama|
|---------|-----------|
|[lock::acquire](#acquire)|İsteğe bağlı olarak her zaman, belirli bir süre süreyi veya hiç kilit için bekleyen bir nesne üzerinde bir kilit alır.|
|[lock::is_locked](#is-locked)|Kilit tutulan olup olmadığını gösterir.|
|[lock::release](#release)|Bir kilidi serbest bırakır.|
|[lock::try_acquire](#try-acquire)|Belirtilen bir zaman miktarı için bekleyen ve döndüren bir nesne üzerinde bir kilit alması bir `bool` bir özel durum oluşturmaktansa edinme başarısını raporlamak için.|

### <a name="public-operators"></a>Genel işleçler

|Ad|Açıklama|
|---------|-----------|
|[Lock::operator&nbsp;bool](#operator-bool)|Kullanarak işleci `lock` koşullu ifadede.|
|[lock::operator==](#operator-equality)|Eşitlik işleci.|
|[lock::operator!=](#operator-inequality)|Eşitsizlik işleci.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\lock.h >

**Namespace** msclr



## <a name="lock"></a>Lock::LOCK

Oluşturur bir `lock` nesne, isteğe bağlı olarak her zaman, belirli bir süre süreyi veya hiç kilit bekleniyor.

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

*n_esne*<br/>
Kilitlenecek nesne.

*_Zaman aşımı*<br/>
Zaman aşımı değerini milisaniye cinsinden veya olarak bir <xref:System.TimeSpan>.

### <a name="exceptions"></a>Özel Durumlar

Oluşturur <xref:System.ApplicationException> oluşmuyorsa zaman aşımından önce kilit edinme.

### <a name="remarks"></a>Açıklamalar

Oluşturucunun ilk üç formlar üzerinde kilit çalıştığınızda `_object` belirtilen zaman aşımı süresi içinde (veya <xref:System.Threading.Timeout.Infinite> hiçbiri belirtilmezse).

Dördüncü Oluşturucu biçiminde üzerinde kilit değil `_object`. `lock_later` bir üyesidir [lock_when numaralandırması](../dotnet/lock-when-enum.md). Kullanım [lock::acquire](../dotnet/lock-acquire.md) veya [lock::try_acquire](../dotnet/lock-try-acquire.md) kilit bu durumda.

Kilit, yok edici çağrıldığında otomatik olarak yayımlanacaktır.

`_object` olamaz <xref:System.Threading.ReaderWriterLock>.  Bu durumda, bir derleyici hatasına neden olur.

### <a name="example"></a>Örnek

Bu örnek, çeşitli iş parçacıkları arasında bir sınıfın tek bir örneğini kullanır. Sınıfı bir kilit kendisine iç verilerine erişen her bir iş parçacığı için tutarlı olduğundan emin olmak için kullanır. Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığı hala mevcut olup olmadığını görmek için düzenli aralıklarla denetleyin için aynı sınıf örneği üzerinde bir kilit kullanır. Ana uygulama, tüm çalışan iş parçacıklarının görevlerini tamamlayıncaya kadar çıkmak için bekler.

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

## <a name="tilde-lock"></a>Kilit:: ~ lock

Destructs bir `lock` nesne.

```cpp
~lock();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çağrıları [lock::release](../dotnet/lock-release.md).

### <a name="example"></a>Örnek

Bu örnek, çeşitli iş parçacıkları arasında bir sınıfın tek bir örneğini kullanır.  Sınıfı bir kilit kendisine iç verilerine erişen her bir iş parçacığı için tutarlı olduğundan emin olmak için kullanır.  Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığı hala mevcut olup olmadığını görmek için düzenli aralıklarla denetleyin için aynı sınıf örneği üzerinde bir kilit kullanır. Ana uygulama, tüm çalışan iş parçacıklarının görevlerini tamamlayıncaya kadar çıkmak için bekler.

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

## <a name="acquire"></a>Lock::Acquire

İsteğe bağlı olarak her zaman, belirli bir süre süreyi veya hiç kilit için bekleyen bir nesne üzerinde bir kilit alır.

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

*_Zaman aşımı*<br/>
Zaman aşımı değerini milisaniye cinsinden veya olarak bir <xref:System.TimeSpan>.

### <a name="exceptions"></a>Özel Durumlar

Oluşturur <xref:System.ApplicationException> oluşmuyorsa zaman aşımından önce kilit edinme.

### <a name="remarks"></a>Açıklamalar

Bir zaman aşımı değeri belirtilirse, bu değilse, varsayılan zaman aşımı olan <xref:System.Threading.Timeout.Infinite>.

Bu işlev, bir kilidi zaten alınmış, hiçbir şey yapmaz.

### <a name="example"></a>Örnek

Bu örnek, çeşitli iş parçacıkları arasında bir sınıfın tek bir örneğini kullanır.  Sınıfı bir kilit kendisine iç verilerine erişen her bir iş parçacığı için tutarlı olduğundan emin olmak için kullanır. Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığı hala mevcut olup olmadığını görmek için düzenli aralıklarla denetleyin için aynı sınıf örneği üzerinde bir kilit kullanır. Ana uygulama, tüm çalışan iş parçacıklarının görevlerini tamamlayıncaya kadar çıkmak için bekler.

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

## <a name="is-locked"></a>Lock::is_locked

Kilit tutulan olup olmadığını gösterir.

```cpp
bool is_locked();
```

### <a name="return-value"></a>Dönüş değeri

`true` bir kilidi açık tutulduğu, `false` Aksi takdirde.

### <a name="example"></a>Örnek

Bu örnek, çeşitli iş parçacıkları arasında bir sınıfın tek bir örneğini kullanır.  Sınıfı bir kilit kendisine iç verilerine erişen her bir iş parçacığı için tutarlı olduğundan emin olmak için kullanır.  Ana uygulama iş parçacığı herhangi bir çalışan iş parçacığı hala mevcut ve kadar tüm çalışan iş parçacığı'ndan çıkmak için beklediği görevlerini tamamladınız görmek için düzenli aralıklarla kontrol etmek için aynı sınıf örneği üzerinde bir kilit kullanır.

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

## <a name="operator-bool"></a>Lock::operator bool

Kullanarak işleci `lock` koşullu ifadede.

```cpp
operator bool();
```

### <a name="return-value"></a>Dönüş değeri

`true` bir kilidi açık tutulduğu, `false` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu işleç gerçekten dönüştürür `_detail_class::_safe_bool` daha güvenli olan `bool` bir integral türe dönüştürülemediğinden.

### <a name="example"></a>Örnek

Bu örnek, çeşitli iş parçacıkları arasında bir sınıfın tek bir örneğini kullanır.  Sınıfı bir kilit kendisine iç verilerine erişen her bir iş parçacığı için tutarlı olduğundan emin olmak için kullanır. Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığı hala mevcut olup olmadığını görmek için düzenli aralıklarla denetleyin için aynı sınıf örneği üzerinde bir kilit kullanır. Ana uygulama, tüm çalışan iş parçacıklarının görevlerini tamamlayıncaya kadar çıkmak için bekler.

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

## <a name="release"></a>Lock::Release

Bir kilidi serbest bırakır.

```cpp
void release();
```

### <a name="remarks"></a>Açıklamalar

Kilit tutulan, `release` hiçbir şey yapmaz.

Bu işlev açıkça çağırmanız gerekmez. Olduğunda bir `lock` nesne, yıkıcı çağrıları kapsam dışına gider `release`.

### <a name="example"></a>Örnek

Bu örnek, çeşitli iş parçacıkları arasında bir sınıfın tek bir örneğini kullanır. Sınıfı bir kilit kendisine iç verilerine erişen her bir iş parçacığı için tutarlı olduğundan emin olmak için kullanır. Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığı hala mevcut olup olmadığını görmek için düzenli aralıklarla denetleyin için aynı sınıf örneği üzerinde bir kilit kullanır. Ana uygulama, tüm çalışan iş parçacıklarının görevlerini tamamlayıncaya kadar çıkmak için bekler.

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

## <a name="try-acquire"></a>Lock::try_acquire

Belirtilen bir zaman miktarı için bekleyen ve döndüren bir nesne üzerinde bir kilit alması bir `bool` bir özel durum oluşturmaktansa edinme başarısını raporlamak için.

```cpp
bool try_acquire(
   int _timeout_ms
);
bool try_acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>Parametreler

*_Zaman aşımı*<br/>
Zaman aşımı değerini milisaniye cinsinden veya olarak bir <xref:System.TimeSpan>.

### <a name="return-value"></a>Dönüş değeri

`true` Kilit alındıysa `false` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir kilidi zaten alınmış, hiçbir şey yapmaz.

### <a name="example"></a>Örnek

Bu örnek, çeşitli iş parçacıkları arasında bir sınıfın tek bir örneğini kullanır. Sınıfı bir kilit kendisine iç verilerine erişen her bir iş parçacığı için tutarlı olduğundan emin olmak için kullanır. Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığı hala mevcut olup olmadığını görmek için düzenli aralıklarla denetleyin için aynı sınıf örneği üzerinde bir kilit kullanır. Ana uygulama, tüm çalışan iş parçacıklarının görevlerini tamamlayıncaya kadar çıkmak için bekler.

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

## <a name="operator-equality"></a>Lock::operator ==

Eşitlik işleci.

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşitlik için karşılaştırma yapılacak nesne.

### <a name="return-value"></a>Dönüş değeri

Döndürür `true` varsa `t` kilit ait nesne aynı `false` Aksi takdirde.

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

## <a name="operator-inequality"></a>Lock::operator! =

Eşitsizlik işleci.

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Eşitsizlik için karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş değeri

Döndürür `true` varsa `t` farklı kilit 's nesneden `false` Aksi takdirde.

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