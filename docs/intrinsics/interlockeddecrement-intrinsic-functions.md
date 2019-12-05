---
title: _InterlockedDecrement iç işlevler
ms.date: 09/02/2019
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
ms.openlocfilehash: f6b256ff1551eea4d0b362e78c9780fce29a8513
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857924"
---
# <a name="_interlockeddecrement-intrinsic-functions"></a>_InterlockedDecrement iç işlevler

**Microsoft 'a özgü**

Win32 Windows SDK [ınterlockedazaltma](/windows/win32/api/winnt/nf-winnt-interlockeddecrement) işlevi için derleyicinin iç desteğini sağlar.

## <a name="syntax"></a>Sözdizimi

```C
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

### <a name="parameters"></a>Parametreler

*Lpaddend*\
[in, out] Azaltılangirecek değişkene yönelik işaretçi.

## <a name="return-value"></a>Dönüş değeri

Dönüş değeri, ortaya çıkan, azaltma değeridir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_InterlockedDecrement`, `_InterlockedDecrement16`|x86, ARM, x64, ARM64|
|`_InterlockedDecrement64`|ARM, x64, ARM64|
|`_InterlockedDecrement_acq`, `_InterlockedDecrement_rel`, `_InterlockedDecrement_nf`, `_InterlockedDecrement16_acq`, `_InterlockedDecrement16_rel`, `_InterlockedDecrement16_nf`, `_InterlockedDecrement64_acq`, `_InterlockedDecrement64_rel`, `_InterlockedDecrement64_nf`,|ARM, ARM64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

`_InterlockedDecrement` üzerinde, içerdikleri veri türlerine göre farklılık gösteren ve işlemciye özgü alma veya yayınlama semantiğinin kullanılıp kullanılmadığını gösteren çeşitli çeşitlemeler vardır.

`_InterlockedDecrement` işlevi 32 bitlik tamsayı değerlerinde çalışırken, `_InterlockedDecrement16` 16 bit tam sayı değerlerinde çalışır ve 64 bit tamsayı değerlerinde çalışır `_InterlockedDecrement64`.

ARM platformlarında, önemli bir bölümün başlangıcında ve sonunda olduğu gibi alma ve yayınlama semantiklerine ihtiyacınız varsa `_acq` ve `_rel` sonekleri ile iç bilgileri kullanın. `_nf` ("sınır yok") son ek olan iç bilgiler bellek engeli olarak davranmaz.

`lpAddend` parametresi tarafından işaret edilen değişken 32 bitlik bir sınıra hizalanmalıdır; Aksi takdirde, bu işlev çok işlemcili x86 sistemlerinde ve x86 olmayan sistemlerde başarısız olur. Daha fazla bilgi için bkz. [ALIGN](../cpp/align-cpp.md).

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

## <a name="example"></a>Örnek

```cpp
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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç](../intrinsics/compiler-intrinsics.md) bilgileri\
[Anahtar sözcükler](../cpp/keywords-cpp.md)\
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
