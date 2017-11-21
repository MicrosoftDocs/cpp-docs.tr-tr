---
title: Lock::try_acquire | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- try_acquire
- lock.try_acquire
- msclr.lock.try_acquire
- lock::try_acquire
- msclr::lock::try_acquire
dev_langs: C++
helpviewer_keywords: lock::try_acquire
ms.assetid: ef0649a9-e611-4495-84bd-2784533221d9
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c63d6a9161eab707b0eab2b831d02210c57a25d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="locktryacquire"></a>lock::try_acquire
Belirtilen bir süre bekleyip ve döndüren bir nesne üzerinde bir kilit alır bir `bool` bir özel durum atma yerine edinme başarısını raporlamak için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
bool try_acquire(  
   int _timeout_ms  
);  
bool try_acquire(  
   System::TimeSpan _timeout  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_timeout`  
 Zaman aşımı değerini milisaniye cinsinden veya farklı bir <xref:System.TimeSpan>.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`Kilit aldıysanız `false` Aksi takdirde.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev bir kilidi zaten alınmış, hiçbir şey yapmaz.  
  
## <a name="example"></a>Örnek  
 Bu örnek, birden çok iş parçacıkları arasında bir sınıfın tek bir örneğini kullanır.  Sınıfı bir kilit kendisini iç verilerine erişir her iş parçacığı için tutarlı olduğundan emin olmak için kullanır.  Ana uygulama iş parçacığı bir kilit sınıfı aynı örneğinde hiçbir çalışan iş parçacığı hala var ve tüm çalışan iş parçacığı kadar çıkmak için bekleyeceği görevlerini tamamladınız görmek için düzenli aralıklarla denetlemek için kullanır.  
  
```  
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
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [lock üyeleri](../dotnet/lock-members.md)   
 [Lock::Acquire](../dotnet/lock-acquire.md)