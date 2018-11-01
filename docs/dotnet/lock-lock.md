---
title: lock::lock
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- lock::lock
- lock.lock
- msclr.lock.lock
- msclr::lock::lock
helpviewer_keywords:
- lock constructor
ms.assetid: c9ad6c71-36ec-49c5-8ebd-f5c3a0cc94f0
ms.openlocfilehash: 480e4f6604adc0a6bd0b3b5fff32f37c811a16a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470583"
---
# <a name="locklock"></a>lock::lock

Oluşturur bir `lock` nesne, isteğe bağlı olarak her zaman, belirli bir süre süreyi veya hiç kilit bekleniyor.

## <a name="syntax"></a>Sözdizimi

```
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

#### <a name="parameters"></a>Parametreler

*n_esne*<br/>
Kilitlenecek nesne.

*_Zaman aşımı*<br/>
Zaman aşımı değerini milisaniye cinsinden veya olarak bir <xref:System.TimeSpan>.

## <a name="exceptions"></a>Özel Durumlar

Oluşturur <xref:System.ApplicationException> kilit alma zaman aşımından önce gerçekleşmezse.

## <a name="remarks"></a>Açıklamalar

Oluşturucu, ilk üç formlar üzerinde kilit girişimi `_object` belirtilen zaman aşımı süresi içinde (veya <xref:System.Threading.Timeout.Infinite> hiçbiri belirtilmezse).

Dördüncü Oluşturucu biçiminde üzerinde kilit değil `_object`. `lock_later` bir üyesidir [lock_when numaralandırması](../dotnet/lock-when-enum.md). Kullanım [lock::acquire](../dotnet/lock-acquire.md) veya [lock::try_acquire](../dotnet/lock-try-acquire.md) kilit bu durumda.

Kilit, yok edici çağrıldığında otomatik olarak yayımlanacaktır.

`_object` olamaz <xref:System.Threading.ReaderWriterLock>.  Bu durumda, bir derleyici hatasına neden olur.

## <a name="example"></a>Örnek

Bu örnek, birden çok iş parçacığı arasında bir sınıfın tek bir örneğini kullanır.  Sınıfı bir kilit kendisine iç verilerine erişen her bir iş parçacığı için tutarlı olmasını sağlamak için kullanır.  Ana uygulama iş parçacığı herhangi bir çalışan iş parçacığı hala mevcut ve kadar tüm çalışan iş parçacığı'ndan çıkmak için beklediği görevlerini tamamladınız görmek için düzenli aralıklarla kontrol etmek için aynı sınıf örneği üzerinde bir kilit kullanır.

```
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

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\lock.h >

**Namespace** msclr

## <a name="see-also"></a>Ayrıca Bkz.

[lock Üyeleri](../dotnet/lock-members.md)<br/>
[lock::~lock](../dotnet/lock-tilde-lock.md)<br/>
[lock::acquire](../dotnet/lock-acquire.md)<br/>
[lock::try_acquire](../dotnet/lock-try-acquire.md)