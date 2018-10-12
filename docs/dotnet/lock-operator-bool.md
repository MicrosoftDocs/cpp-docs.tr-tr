---
title: Lock::operator bool | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- operator bool
- msclr.lock.operator bool
- lock.operator bool
- msclr::lock::operator bool
- lock::operator bool
dev_langs:
- C++
helpviewer_keywords:
- lock::operator bool
ms.assetid: 007f0372-f812-4f1e-ba43-2584bd96eb11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d0aee08fc59130e829d9448ba4f28a9823a461ed
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161781"
---
# <a name="lockoperator-bool"></a>lock::operator bool

Kullanarak işleci `lock` koşullu ifadede.

## <a name="syntax"></a>Sözdizimi

```
operator bool();
```

## <a name="return-value"></a>Dönüş Değeri

**doğru** bir kilidi açık tutulduğu, **false** Aksi takdirde.

## <a name="remarks"></a>Açıklamalar

Bu işleç gerçekten dönüştürür `_detail_class::_safe_bool` daha güvenli olan **bool** bir integral türe dönüştürülemediğinden.

## <a name="example"></a>Örnek

Bu örnek, birden çok iş parçacığı arasında bir sınıfın tek bir örneğini kullanır.  Sınıfı bir kilit kendisine iç verilerine erişen her bir iş parçacığı için tutarlı olmasını sağlamak için kullanır.  Ana uygulama iş parçacığı herhangi bir çalışan iş parçacığı hala mevcut ve kadar tüm çalışan iş parçacığı'ndan çıkmak için beklediği görevlerini tamamladınız görmek için düzenli aralıklarla kontrol etmek için aynı sınıf örneği üzerinde bir kilit kullanır.

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

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\lock.h >

**Namespace** msclr

## <a name="see-also"></a>Ayrıca Bkz.

[lock Üyeleri](../dotnet/lock-members.md)<br/>
[lock::is_locked](../dotnet/lock-is-locked.md)