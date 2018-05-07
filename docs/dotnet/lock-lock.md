---
title: Lock::LOCK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- lock::lock
- lock.lock
- msclr.lock.lock
- msclr::lock::lock
dev_langs:
- C++
helpviewer_keywords:
- lock constructor
ms.assetid: c9ad6c71-36ec-49c5-8ebd-f5c3a0cc94f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: df35eed8711e83174316ac9912f7ba535ef9ebf9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="locklock"></a>lock::lock
Oluşturan bir `lock` nesnesi, isteğe bağlı olarak her zaman, belirtilen bir miktar süre ya da hiç için kilit bekleniyor.  
  
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
 `_object`  
 Kilitlenecek nesne.  
  
 `_timeout`  
 Zaman aşımı değerini milisaniye cinsinden veya farklı bir <xref:System.TimeSpan>.  
  
## <a name="exceptions"></a>Özel Durumlar  
 Oluşturur <xref:System.ApplicationException> kilit edinme zaman aşımından önce gerçekleşmezse.  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturucusu ilk üç formlarını üzerinde kilit elde etmeye `_object` belirtilen zaman aşımı süresi içinde (veya <xref:System.Threading.Timeout.Infinite> hiçbiri belirtilen).  
  
 Oluşturucusu dördüncü biçiminde bir üzerinde kilit yok `_object`. `lock_later` üye [lock_when numaralandırması](../dotnet/lock-when-enum.md). Kullanım [lock::acquire](../dotnet/lock-acquire.md) veya [lock::try_acquire](../dotnet/lock-try-acquire.md) bu durumda kilidinin alınması.  
  
 Yok Edicisi çağrıldığında kilidi otomatik olarak yayınlanacaktır.  
  
 `_object` olamaz <xref:System.Threading.ReaderWriterLock>.  Derleyici Hatası ise, neden olur.  
  
## <a name="example"></a>Örnek  
 Bu örnek, birden çok iş parçacıkları arasında bir sınıfın tek bir örneğini kullanır.  Sınıfı bir kilit kendisini iç verilerine erişir her iş parçacığı için tutarlı olduğundan emin olmak için kullanır.  Ana uygulama iş parçacığı bir kilit sınıfı aynı örneğinde hiçbir çalışan iş parçacığı hala var ve tüm çalışan iş parçacığı kadar çıkmak için bekleyeceği görevlerini tamamladınız görmek için düzenli aralıklarla denetlemek için kullanır.  
  
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
 **Üstbilgi dosyası** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [lock üyeleri](../dotnet/lock-members.md)   
 [Kilit:: ~ lock](../dotnet/lock-tilde-lock.md)   
 [Lock::Acquire](../dotnet/lock-acquire.md)   
 [lock::try_acquire](../dotnet/lock-try-acquire.md)