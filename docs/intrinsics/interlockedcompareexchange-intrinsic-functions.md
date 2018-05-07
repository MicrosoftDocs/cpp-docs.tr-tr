---
title: _InterlockedCompareExchange iç işlevler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedCompareExchange_HLERelease
- _InterlockedCompareExchange8_nf
- _InterlockedCompareExchange16_acq_cpp
- _InterlockedCompareExchange_acq_cpp
- _InterlockedCompareExchange16_rel_cpp
- _InterlockedCompareExchange64_rel_cpp
- _InterlockedCompareExchange_cpp
- _InterlockedCompareExchange16_cpp
- _InterlockedCompareExchange64_acq_cpp
- _InterlockedCompareExchange_acq
- _InterlockedCompareExchange64_rel
- _InterlockedCompareExchange64_nf
- _InterlockedCompareExchange_rel_cpp
- _InterlockedCompareExchange16_nf
- _InterlockedCompareExchange8
- _InterlockedCompareExchange64_np
- _InterlockedCompareExchange16_rel
- _InterlockedCompareExchange64_acq
- _InterlockedCompareExchange8_rel
- _InterlockedCompareExchange_HLEAcquire
- _InterlockedCompareExchange64_HLERelease
- _InterlockedCompareExchange64_cpp
- _InterlockedCompareExchange_np
- _InterlockedCompareExchange8_acq
- _InterlockedCompareExchange16_acq
- _InterlockedCompareExchange_rel
- _InterlockedCompareExchange64_HLEAcquire
- _InterlockedCompareExchange64
- _InterlockedCompareExchange16
- _InterlockedCompareExchange
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedCompareExchange16 intrinsic
- _InterlockedCompareExchange_acq intrinsic
- InterlockedCompareExchange_acq intrinsic
- _InterlockedCompareExchange intrinsic
- InterlockedCompareExchange64 intrinsic
- _InterlockedCompareExchange64_acq intrinsic
- InterlockedCompareExchange16 intrinsic
- _InterlockedCompareExchange_rel intrinsic
- InterlockedCompareExchange intrinsic
- InterlockedCompareExchange64_acq intrinsic
- InterlockedCompareExchange_rel intrinsic
- _InterlockedCompareExchange64 intrinsic
- InterlockedCompareExchange64_rel intrinsic
- _InterlockedCompareExchange64_rel intrinsic
ms.assetid: c3ad79c0-a523-4930-a3a4-69a65d7d5c81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b0fc52585171df740f70e12d81d849e3726dcd7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="interlockedcompareexchange-intrinsic-functions"></a>_InterlockedCompareExchange iç işlevler
**Microsoft özel**  
  
 Bir exchange ve ınterlocked karşılaştırmak gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long _InterlockedCompareExchange(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
long _InterlockedCompareExchange_acq(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
long _InterlockedCompareExchange_HLEAcquire(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
long _InterlockedCompareExchange_HLERelease(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
long _InterlockedCompareExchange_np(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
long _InterlockedCompareExchange_rel(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
char _InterlockedCompareExchange8(  
   char volatile * Destination,  
   char Exchange,  
   char Comparand  
);  
char _InterlockedCompareExchange8_acq(  
   char volatile * Destination,  
   char Exchange,  
   char Comparand  
);  
char _InterlockedCompareExchange8_nf(  
   char volatile * Destination,  
   char Exchange,  
   char Comparand  
);  
char _InterlockedCompareExchange8_rel(  
   char volatile * Destination,  
   char Exchange,  
   char Comparand  
);  
short _InterlockedCompareExchange16(  
   short volatile * Destination,  
   short Exchange,  
   short Comparand  
);  
short _InterlockedCompareExchange16_acq(  
   short volatile * Destination,  
   short Exchange,  
   short Comparand  
);  
short _InterlockedCompareExchange16_nf(  
   short volatile * Destination,  
   short Exchange,  
   short Comparand  
);  
short _InterlockedCompareExchange16_np(  
   short volatile * Destination,  
   short Exchange,  
   short Comparand  
);  
short _InterlockedCompareExchange16_rel(  
   short volatile * Destination,  
   short Exchange,  
   short Comparand  
);  
__int64 _InterlockedCompareExchange64(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_acq(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_HLEAcquire (  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_HLERelease(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_nf(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_np(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_rel(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [içinde out] `Destination`  
 Hedef değer işaretçi. Oturum açma göz ardı edilir.  
  
 [in] `Exchange`  
 Exchange değeri. Oturum açma göz ardı edilir.  
  
 [in] `Comparand`  
 Hedefe Karşılaştırılacak değer. Oturum açma göz ardı edilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri ilk değeri `Destination` işaretçi.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|Üstbilgi|  
|---------------|------------------|------------|  
|`_InterlockedCompareExchange`, `_InterlockedCompareExchange8`, `_InterlockedCompareExchange16`, `_InterlockedCompareExchange64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_InterlockedCompareExchange_acq`, `_InterlockedCompareExchange_rel`, `_InterlockedCompareExchange8_acq`, `_InterlockedCompareExchange8_nf`, `_InterlockedCompareExchange8_rel`,`_InterlockedCompareExchange16_acq`, `_InterlockedCompareExchange16_nf`, `_InterlockedCompareExchange16_rel`, `_InterlockedCompareExchange64_acq`, `_InterlockedCompareExchange64_nf`, `_InterlockedCompareExchange64_rel`,|ARM|\<intrin.h >|  
|`_InterlockedCompareExchange_np`, `_InterlockedCompareExchange16_np`, `_InterlockedCompareExchange64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
|`_InterlockedCompareExchange_HLEAcquire`, `_InterlockedCompareExchange_HLERelease`, `_InterlockedCompareExchange64_HLEAcquire`, `_InterlockedCompareExchange64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h >|  
  
## <a name="remarks"></a>Açıklamalar  
 `_InterlockedCompareExchange` bir atomik karşılaştırması gerçekleştirir `Destination` değerini `Comparand` değeri. Varsa `Destination` değerdir eşit `Comparand` değeri `Exchange` değeri tarafından belirtilen adresi depolanır `Destination`. Aksi takdirde, hiçbir işlem yapılmadı.  
  
 `_InterlockedCompareExchange` derleyici iç Win32 desteği sağlar [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] [InterlockedCompareExchange](http://msdn.microsoft.com/library/ms683560.aspx) işlevi.  
  
 Birkaç Çeşitlemeler vardır `_InterlockedCompareExchange` , bunlar içeren veri türleri ve işlemci özgü olup elde göre farklılık veya yayın semantiği kullanılır.  
  
 Sırada `_InterlockedCompareExchange` işlev çalışır uzun tamsayı değerlerine `_InterlockedCompareExchange8` 8 bit tam sayı değerleri üzerinde çalışır `_InterlockedCompareExchange16` kısa tamsayı değerler üzerinde çalışır ve `_InterlockedCompareExchange64` 64 bit tam sayı değerleri üzerinde çalışır.  
  
 İç bilgiler ile ARM platformlarda kullanın `_acq` ve `_rel` sonekleri edinme ve yayın anlamları gibi önemli bir bölümü başında ve sonunda. ARM iç bilgileri ile bir `_nf` ("hiçbir dilimi") soneki bir bellek engeli hareket değil.  
  
 İç bilgiler ile bir `_np` ("hiçbir hazırlık") soneki derleyici tarafından eklenen bir olası hazırlık işlemin engelleme.  
  
 Donanım kilidi Elision (HLE) yönergeleri, iç bilgileri ile destek Intel platformlarda `_HLEAcquire` ve `_HLERelease` son ekleri kapsayacak performans donanım kilidi yazma adımda ortadan kaldırarak hızlandırabilir işlemci ipucu. Bu yapı HLE desteklemeyen platformlarda çağrıldıklarında ipucu yoksayıldı.  
  
 Bu yordamlar, yalnızca iç bilgileri kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `_InterlockedCompareExchange` basit alt düzey iş parçacığı eşitleme için kullanılır. Bir yaklaşım, birden çok iş parçacıklı programlama için temel olarak kendi sınırlamaları vardır; ınterlocked iç bilgileri tipik kullanımını göstermek için sunulur. En iyi sonuçlar için Windows API kullanın. Birden çok iş parçacıklı programlama hakkında daha fazla bilgi için bkz: [çoklu iş parçacığı kullanan Win32 programı yazma](../parallel/writing-a-multithreaded-win32-program.md).  
  
```  
// intrinExample.cpp  
// compile with: /EHsc /O2  
// Simple example of using _Interlocked* intrinsics to  
// do manual synchronization  
//  
// Add [-DSKIP_LOCKING] to the command line to disable  
// the locking. This will cause the threads to execute out  
// of sequence.  
  
#define _CRT_RAND_S  
  
#include "windows.h"  
  
#include <iostream>  
#include <queue>  
#include <intrin.h>  
  
using namespace std;  
  
// --------------------------------------------------------------------  
  
// if defined, will not do any locking on shared data  
//#define SKIP_LOCKING  
  
// A common way of locking using _InterlockedCompareExchange.  
// Please refer to other sources for a discussion of the many issues  
// involved. For example, this particular locking scheme performs well   
// when lock contention is low, as the while loop overhead is small and  
// locks are acquired very quickly, but degrades as many callers want  
// the lock and most threads are doing a lot of interlocked spinning.  
// There are also no guarantees that a caller will ever acquire the  
// lock.  
namespace MyInterlockedIntrinsicLock  
{  
    typedef unsigned LOCK, *PLOCK;  
  
#pragma intrinsic(_InterlockedCompareExchange, _InterlockedExchange)  
  
    enum {LOCK_IS_FREE = 0, LOCK_IS_TAKEN = 1};  
  
    void Lock(PLOCK pl)   
    {  
#if !defined(SKIP_LOCKING)  
        // If *pl == LOCK_IS_FREE, it is set to LOCK_IS_TAKEN  
        // atomically, so only 1 caller gets the lock.  
        // If *pl == LOCK_IS_TAKEN,  
        // the result is LOCK_IS_TAKEN, and the while loop keeps spinning.  
        while (_InterlockedCompareExchange((long *)pl,  
                                           LOCK_IS_TAKEN, // exchange  
                                           LOCK_IS_FREE)  // comparand  
               == LOCK_IS_TAKEN)  
        {  
            // spin!  
        }  
        // This will also work.  
        //while (_InterlockedExchange(pl, LOCK_IS_TAKEN) ==   
        //                             LOCK_IS_TAKEN)  
        //{  
        //    // spin!  
        //}  
  
        // At this point, the lock is acquired.  
#endif  
    }  
  
    void Unlock(PLOCK pl) {  
#if !defined(SKIP_LOCKING)  
        _InterlockedExchange((long *)pl, LOCK_IS_FREE);  
#endif  
    }  
}  
  
// ------------------------------------------------------------------  
  
// Data shared by threads  
  
queue<int> SharedQueue;  
MyInterlockedIntrinsicLock::LOCK SharedLock;  
int TicketNumber;  
  
// ------------------------------------------------------------------  
  
DWORD WINAPI  
ProducerThread(  
    LPVOID unused  
    )  
{  
    unsigned int randValue;  
    while (1) {  
        // Acquire shared data. Enter critical section.  
        MyInterlockedIntrinsicLock::Lock(&SharedLock);  
  
        //cout << ">" << TicketNumber << endl;  
        SharedQueue.push(TicketNumber++);  
  
        // Release shared data. Leave critical section.  
        MyInterlockedIntrinsicLock::Unlock(&SharedLock);  
  
        rand_s(&randValue);  
        Sleep(randValue % 20);  
    }  
  
    return 0;  
}  
  
DWORD WINAPI  
ConsumerThread(  
    LPVOID unused  
    )  
{  
    while (1) {  
        // Acquire shared data. Enter critical section  
        MyInterlockedIntrinsicLock::Lock(&SharedLock);  
  
        if (!SharedQueue.empty()) {  
            int x = SharedQueue.front();  
            cout << "<" << x << endl;  
            SharedQueue.pop();  
        }  
  
        // Release shared data. Leave critical section  
        MyInterlockedIntrinsicLock::Unlock(&SharedLock);  
  
        unsigned int randValue;  
        rand_s(&randValue);  
        Sleep(randValue % 20);  
    }  
    return 0;  
}  
  
int main(  
    void  
    )  
{  
    const int timeoutTime = 500;  
    int unused1, unused2;  
    HANDLE threads[4];  
  
    // The program creates 4 threads:  
    // two producer threads adding to the queue  
    // and two consumers taking data out and printing it.  
    threads[0] = CreateThread(NULL,  
                              0,  
                              ProducerThread,  
                              &unused1,  
                              0,  
                              (LPDWORD)&unused2);  
  
    threads[1] = CreateThread(NULL,  
                              0,  
                              ConsumerThread,  
                              &unused1,  
                              0,  
                              (LPDWORD)&unused2);  
  
    threads[2] = CreateThread(NULL,  
                              0,  
                              ProducerThread,  
                              &unused1,  
                              0,  
                              (LPDWORD)&unused2);  
  
    threads[3] = CreateThread(NULL,  
                              0,  
                              ConsumerThread,  
                              &unused1,  
                              0,  
                              (LPDWORD)&unused2);  
  
    WaitForMultipleObjects(4, threads, TRUE, timeoutTime);  
  
    return 0;  
}  
```  
  
```Output  
<0  
<1  
<2  
<3  
<4  
<5  
<6  
<7  
<8  
<9  
<10  
<11  
<12  
<13  
<14  
<15  
<16  
<17  
<18  
<19  
<20  
<21  
<22  
<23  
<24  
<25  
<26  
<27  
<28  
<29  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_InterlockedCompareExchange128](../intrinsics/interlockedcompareexchange128.md)   
 [_InterlockedCompareExchangePointer iç işlevler](../intrinsics/interlockedcompareexchangepointer-intrinsic-functions.md)   
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)