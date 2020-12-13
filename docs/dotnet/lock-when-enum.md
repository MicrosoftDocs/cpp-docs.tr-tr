---
description: 'Hakkında daha fazla bilgi edinin: lock_when Enum'
title: lock_when Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::lock_when
- msclr.lock_when
- lock_when
helpviewer_keywords:
- lock_when enum
ms.assetid: 6b87bbe9-63cd-450d-a02e-bb91ffd0dcea
ms.openlocfilehash: 5fcc0e428056f5076803ec1ba82bb20207e37189
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344490"
---
# <a name="lock_when-enum"></a>lock_when Numaralandırması

Ertelenmiş kilitlemeyi belirtir.

## <a name="syntax"></a>Syntax

```
enum lock_when {
   lock_later
};
```

## <a name="remarks"></a>Açıklamalar

[Lock:: Lock](./lock-class.md#lock)öğesine geçirildiğinde `lock_later` kilidin Şu anda alınmamalıdır.

## <a name="example"></a>Örnek

Bu örnek, birden çok iş parçacığında bir sınıfın tek bir örneğini kullanır.  Sınıfı, iç verilerine erişimin her iş parçacığı için tutarlı olduğundan emin olmak için kendi üzerinde bir kilit kullanır.  Ana uygulama iş parçacığı, herhangi bir çalışan iş parçacığının hala mevcut olup olmadığını denetlemek için bir kilit kullanır ve tüm çalışan iş parçacıkları görevlerini tamamlayana kadar çıkış ' ı bekler.

```cpp
// msl_lock_lock_when.cpp
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

**Üst bilgi dosyası**\<msclr\lock.h>

**Ad alanı** msclr

## <a name="see-also"></a>Ayrıca bkz.

[ine](../dotnet/lock.md)
