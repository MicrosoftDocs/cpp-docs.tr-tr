---
title: Lock::Release | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lock.release
- msclr::lock::release
- lock::release
- msclr.lock.release
dev_langs: C++
helpviewer_keywords: lock::release
ms.assetid: b73d48fc-cf98-4b78-b39d-813d4a12fa84
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e702ffda531d43a2ff8a0d41b10d1f053bdc6e11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="lockrelease"></a>lock::release
Bir kilidi serbest bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void release();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kilit Tutuluyor, `release` hiçbir şey yapmaz.  
  
 Bu işlev açıkça çağırın gerekmez; zaman bir `lock` nesne kapsam dışında kendi yıkıcı çağrıları gider `release`.  
  
## <a name="example"></a>Örnek  
 Bu örnek, birden çok iş parçacıkları arasında bir sınıfın tek bir örneğini kullanır.  Sınıfı bir kilit kendisini iç verilerine erişir her iş parçacığı için tutarlı olduğundan emin olmak için kullanır.  Ana uygulama iş parçacığı bir kilit sınıfı aynı örneğinde hiçbir çalışan iş parçacığı hala var ve tüm çalışan iş parçacığı kadar çıkmak için bekleyeceği görevlerini tamamladınız görmek için düzenli aralıklarla denetlemek için kullanır.  
  
```  
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
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [lock üyeleri](../dotnet/lock-members.md)   
 [lock::~lock](../dotnet/lock-tilde-lock.md)