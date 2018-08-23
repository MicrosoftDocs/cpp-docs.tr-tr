---
title: _Interlockeddecrement iç işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedDecrement16_rel_cpp
- _InterlockedDecrement16_acq_cpp
- _InterlockedDecrement16_rel
- _InterlockedDecrement64_acq
- _InterlockedDecrement_nf
- _InterlockedDecrement16_nf
- _InterlockedDecrement64_rel_cpp
- _InterlockedDecrement_rel_cpp
- _InterlockedDecrement16_acq
- _InterlockedDecrement64_acq_cpp
- _InterlockedDecrement_rel
- _InterlockedDecrement64_nf
- _InterlockedDecrement16_cpp
- _InterlockedDecrement64
- _InterlockedDecrement_cpp
- _InterlockedDecrement64_rel
- _InterlockedDecrement16
- _InterlockedDecrement
- _InterlockedDecrement64_cpp
- _InterlockedDecrement_acq
- _InterlockedDecrement_acq_cpp
dev_langs:
- C++
helpviewer_keywords:
- InterlockedDecrement64_rel intrinsic
- InterlockedDecrement64 intrinsic
- _InterlockedDecrement16 intrinsic
- _InterlockedDecrement16_acq intrinsic
- _InterlockedDecrement intrinsic
- _InterlockedDecrement_nf intrinsic
- _InterlockedDecrement_acq intrinsic
- _InterlockedDecrement64_rel intrinsic
- _InterlockedDecrement16_rel intrinsic
- InterlockedDecrement intrinsic
- InterlockedDecrement16 intrinsic
- _InterlockedDecrement16_nf intrinsic
- InterlockedDecrement64_acq intrinsic
- _InterlockedDecrement_rel intrinsic
- InterlockedDecrement_acq intrinsic
- _InterlockedDecrement64_acq intrinsic
- _InterlockedDecrement64 intrinsic
- _InterlockedDecrement64_nf intrinsic
- InterlockedDecrement_rel intrinsic
ms.assetid: 5268fce3-86b5-4b2b-b96c-2e531a3fb9b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a30a09b9feae0d5c7e0d24967c133f076286f2fc
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42464692"
---
# <a name="interlockeddecrement-intrinsic-functions"></a>_Interlockeddecrement iç işlevleri
**Microsoft'a özgü**  
  
Win32 Windows SDK'sı için derleyici iç desteği sağlayan [InterlockedDecrement](/windows/desktop/api/winbase/nf-winbase-interlockeddecrement) işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long _InterlockedDecrement(  
   long * lpAddend  
);  
long _InterlockedDecrement_acq(  
   long * lpAddend  
);  
long _InterlockedDecrement_rel(  
   long * lpAddend  
);  
long _InterlockedDecrement_nf(  
   long * lpAddend  
);  
short _InterlockedDecrement16(  
   short * lpAddend  
);  
short _InterlockedDecrement16_acq(  
   short * lpAddend  
);  
short _InterlockedDecrement16_rel(  
   short * lpAddend  
);  
short _InterlockedDecrement16_nf(  
   short * lpAddend  
);  
__int64 _InterlockedDecrement64(  
   __int64 * lpAddend  
);  
__int64 _InterlockedDecrement64_acq(  
   __int64 * lpAddend  
);  
__int64 _InterlockedDecrement64_rel(  
   __int64 * lpAddend  
);   
__int64 _InterlockedDecrement64_nf(  
   __int64 * lpAddend  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out içinde] `lpAddend`  
 Azaltılacak değişken işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri elde edilen indirildiği değerdir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_InterlockedDecrement`, `_InterlockedDecrement16`, `_InterlockedDecrement64`|x86, ARM, x64|  
|`_InterlockedDecrement_acq`, `_InterlockedDecrement_rel`, `_InterlockedDecrement_nf`, `_InterlockedDecrement16_acq`, `_InterlockedDecrement16_rel`, `_InterlockedDecrement16_nf`, `_InterlockedDecrement64_acq`, `_InterlockedDecrement64_rel`, `_InterlockedDecrement64_nf`,|ARM|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bazı farklılıklar vardır `_InterlockedDecrement` , bunlar içeren veri türleri ve olup işlemciye özgü alma göre farklılık veya release semantikleri kullanılır.  
  
 Sırada `_InterlockedDecrement` işlevi 32-bit tamsayı değerleri üzerinde çalışır `_InterlockedDecrement16` 16 bit tam sayı değerler üzerinde çalışır ve `_InterlockedDecrement64` 64-bit tamsayı değerler üzerinde çalışır.  
  
 ARM platformlarında, yapı içleri ile kullanmak `_acq` ve `_rel` almak ve yayın semantiğini gibi kritik bir bölüm başında ve sonunda sonekleri. Yapı içleri ile bir `_nf` ("hiçbir sınır") soneki bellek önünde bir engel hareket değil.  
  
 Değişkeni tarafından işaret edilen `lpAddend` parametresi bir 32-bit sınırında hizalanmış olmalıdır; aksi takdirde, bu işlev üzerinde çok işlemcili x86 başarısız sistemleri ve x86 olmayan sistemler. Daha fazla bilgi için [hizalama](../cpp/align-cpp.md).  
  
 Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
```  
// compiler_intrinsics_interlocked.cpp  
// compile with: /Oi  
#define _CRT_RAND_S  
  
#include <cstdlib>  
#include <cstdio>  
#include <process.h>  
#include <windows.h>  
  
// To declare an interlocked function for use as an intrinsic,  
// include intrin.h and put the function in a #pragma intrinsic   
// statement.  
#include <intrin.h>  
  
#pragma intrinsic (_InterlockedIncrement)  
  
// Data to protect with the interlocked functions.  
volatile LONG data = 1;  
  
void __cdecl SimpleThread(void* pParam);  
  
const int THREAD_COUNT = 6;  
  
int main() {  
   DWORD num;  
   HANDLE threads[THREAD_COUNT];  
   int args[THREAD_COUNT];  
   int i;  
  
   for (i = 0; i < THREAD_COUNT; i++) {  
     args[i] = i + 1;  
     threads[i] = reinterpret_cast<HANDLE>(_beginthread(SimpleThread, 0,   
                           args + i));  
      if (threads[i] == reinterpret_cast<HANDLE>(-1))  
         // error creating threads  
         break;  
   }  
  
   WaitForMultipleObjects(i, threads, true, INFINITE);  
}  
  
// Code for our simple thread  
void __cdecl SimpleThread(void* pParam) {  
   int threadNum = *((int*)pParam);  
   int counter;  
   unsigned int randomValue;  
   unsigned int time;  
   errno_t err = rand_s(&randomValue);  
  
   if (err == 0) {  
      time = (unsigned int) ((double) randomValue / (double) UINT_MAX * 500);  
      while (data < 100) {  
         if (data < 100) {  
            _InterlockedIncrement(&data);  
            printf_s("Thread %d: %d\n", threadNum, data);  
         }  
  
         Sleep(time);   // wait up to half of a second  
      }  
   }  
  
   printf_s("Thread %d complete: %d\n", threadNum, data);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)