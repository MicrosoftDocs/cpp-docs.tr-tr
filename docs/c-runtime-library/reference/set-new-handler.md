---
title: _set_new_handler
ms.date: 11/04/2016
apiname:
- _set_new_handler
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_new_handler
- set_new_handler
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
ms.openlocfilehash: bc7718503f59c69868a75cac9383286a548fc307
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356506"
---
# <a name="setnewhandler"></a>_set_new_handler

Varsa, hata işleme mekanizması aktarır denetim **yeni** işleci başarısız bellek ayrılamadı.

## <a name="syntax"></a>Sözdizimi

```cpp
_PNH _set_new_handler( _PNH pNewHandler );
```

### <a name="parameters"></a>Parametreler

*pNewHandler*<br/>
Uygulama tarafından sağlanan belleği işleme işlevinin işaretçisi. Bir bağımsız değişkeni 0 yeni işleyici kaldırılmasına neden olur.

## <a name="return-value"></a>Dönüş Değeri

Önceki özel durum işleme işlevi tarafından kaydedilen bir işaretçi döndürür **_set_new_handler**, böylece önceki işlevi daha sonra geri yüklenebilir. Önceki bir işlev ayarlarsanız dönüş değeri, varsayılan davranışı geri yüklemek için kullanılabilir; Bu değer **NULL**.

## <a name="remarks"></a>Açıklamalar

C++ **_Set_new_handler** işlevi belirtir, Denetim kazançları bir özel durum işleme işlevi **yeni** işleci başarısız bellek ayrılamadı. Varsa **yeni** başarısız çalışma zamanı sistemi otomatik olarak bir bağımsız değişken olarak geçirilen özel durum işleme işlevi çağırır **_set_new_handler**. **_PNH**, New.h içinde tanımlanan, bir tür döndüren bir işlev işaretçisidir **int** ve türünde bir bağımsız değişken **size_t**. Kullanım **size_t** ayrılacak alanı miktarını belirtmek için.

Hiçbir varsayılan işleyici yok.

**_set_new_handler** aslında bir çöp toplama düzeni. Çalışma zamanı sistemi ayırma işlevinizi sıfır olmayan bir değer döndürür ve 0 işlevinizi döndürürse başarısız her zaman yeniden dener.

Bir olayın oluşmasını **_set_new_handler** işlevi bir programda çalışma zamanı sistemi bağımsız değişken listesinde belirtilen özel durum işleme işlevini kaydeder:

```cpp
// set_new_handler1.cpp
#include <new.h>

int handle_program_memory_depletion( size_t )
{
   // Your code
}

int main( void )
{
   _set_new_handler( handle_program_memory_depletion );
   int *pi = new int[BIG_NUMBER];
}
```

Son geçirilen işlev adresi kaydedebilirsiniz **_set_new_handler** çalışır ve daha sonra yeniden devreye sokmak:

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

C++ [_Set_new_mode](set-new-mode.md) işlevi için yeni işleyici modunu ayarlar [malloc](malloc.md). Yeni işleyici modunu gösterir mi, hata durumunda, **malloc** tarafından belirlenen yeni işleyici rutinini çağırmaktır **_set_new_handler**. Varsayılan olarak, **malloc** bellek dağıtma hatasında yeni işleyici rutinini çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, **malloc** bellek ayırmak başarısız **malloc** aynı yeni işleyici rutinini çağırır biçimi **yeni** işleci yok aynı nedenden dolayı başarısız olduğunda. Varsayılan geçersiz kılmak için çağırın:

```cpp
_set_new_mode(1);
```

erken, program veya Newmode.obj ile.

Kullanıcı tanımlı değilse `operator new` yeni işleyici işlevleri otomatik olarak hata durumunda çağrılır değil sağlanır.

Daha fazla bilgi için [yeni](../../cpp/new-operator-cpp.md) ve [Sil](../../cpp/delete-operator-cpp.md) içinde *C++ dil başvurusu*.

Tek bir yoktur **_set_new_handler** işleyicisi için tüm dinamik olarak bağlı dll veya yürütülebilir dosyaları; çağırsanız bile **_set_new_handler** işleyicinizi bir başkası tarafından değiştirilebilir veya değiştirdiğiniz bir işleyici, başka bir DLL veya yürütülebilir dosya ayarlayın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_new_handler**|\<New.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Ayırma başarısız olduğunda, bu örnekte, denetim için MyNewHandler aktarılır. MyNewHandler için geçirilen bağımsız değişken istenen bayt sayısıdır. Ayırma denenen olup olmadığını belirten bir bayrak MyNewHandler döndürülen değer olduğu: ayırma yeniden deneme ve sıfır değeri ayırma başarısız olduğunu gösteren sıfır dışında bir değeri gösterir.

```cpp
// crt_set_new_handler.cpp
// compile with: /c
#include <stdio.h>
#include <new.h>
#define BIG_NUMBER 0x1fffffff

int coalesced = 0;

int CoalesceHeap()
{
   coalesced = 1;  // Flag RecurseAlloc to stop
   // do some work to free memory
   return 0;
}
// Define a function to be called if new fails to allocate memory.
int MyNewHandler( size_t size )
{
   printf("Allocation failed. Coalescing heap.\n");

   // Call a function to recover some heap space.
   return CoalesceHeap();
}

int RecurseAlloc() {
   int *pi = new int[BIG_NUMBER];
   if (!coalesced)
      RecurseAlloc();
   return 0;
}

int main()
{
   // Set the failure handler for new to be MyNewHandler.
   _set_new_handler( MyNewHandler );
   RecurseAlloc();
}
```

```Output
Allocation failed. Coalescing heap.

This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
