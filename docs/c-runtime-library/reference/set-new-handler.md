---
title: _set_new_handler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 11ffd955f18a58c8b3d767697b7f7146f2b8db5a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="setnewhandler"></a>_set_new_handler

Varsa, hata işleme mekanizması aktarır denetim **yeni** işleci başarısız bellek ayıramadı.

## <a name="syntax"></a>Sözdizimi

```cpp
_PNH _set_new_handler( _PNH pNewHandler );
```

### <a name="parameters"></a>Parametreler

*pNewHandler*<br/>
Uygulama tarafından sağlanan bellek işlevi işleme yönelik işaretçi. Bir bağımsız değişkeni 0 kaldırılacak yeni işleyici neden olur.

## <a name="return-value"></a>Dönüş Değeri

Önceki özel durum tarafından kaydedilen işlevi işleme için bir işaretçi döndüren **_set_new_handler**, böylece önceki işlevi daha sonra geri yüklenebilir. Önceki bir işlev ayarlarsanız dönüş değerini varsayılan davranışını geri yüklemek için kullanılabilir; Bu değer **NULL**.

## <a name="remarks"></a>Açıklamalar

C++ **_set_new_handler** işlevi belirtir, denetim elde bir özel durum işleme işlevi **yeni** işleci başarısız bellek ayıramadı. Varsa **yeni** başarısız, çalışma zamanı sistemi otomatik olarak bir bağımsız değişken olarak geçirilen özel durum işleme işlevi çağırır **_set_new_handler**. **_PNH**, New.h içinde tanımlanan, işaretçi türü döndüren bir işlev için **int** ve bir bağımsız değişken türü **size_t**. Kullanım **size_t** ayrılacak alanı belirtmek için.

Hiçbir varsayılan işleyici yok.

**_set_new_handler** temelde çöp toplama düzenidir. Çalışma zamanı sistem ayırma işlevinizi sıfır olmayan bir değer döndürür ve işlevinizi 0 döndürürse başarısız her zaman yeniden dener.

Bir örneğini **_set_new_handler** işlevi bir programı çalıştırma sistemiyle bağımsız değişken listesinde belirtilen özel durum işleme işlevi kaydeder:

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

Son geçirilen işlev adresi kaydedebilirsiniz **_set_new_handler** işlev ve daha sonra yeniden devreye sokmanız:

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

C++ [_set_new_mode](set-new-mode.md) işlevi ayarlar için yeni işleyici modu [malloc](malloc.md). Yeni işleyici modunu gösterir, hatasında kullanılıp **malloc** belirlediği yeni işleyici yordamı çağırmaktır **_set_new_handler**. Varsayılan olarak, **malloc** yeni işleyici yordamı bellek ayırma hatası çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, **malloc** bellek ayırmak başarısız **malloc** yeni işleyici yordamını aynı çağırıyor biçimi **yeni** işleci mu aynı nedenden dolayı başarısız olduğunda. Varsayılan değer geçersiz kılmak için arayın:

```cpp
_set_new_mode(1);
```

erken, program veya Newmode.obj bağlantısıyla.

Kullanıcı tanımlı değilse `operator new` yeni işleyici işlevleri otomatik olarak hatada denir değil sağlanır.

Daha fazla bilgi için bkz: [yeni](../../cpp/new-operator-cpp.md) ve [silmek](../../cpp/delete-operator-cpp.md) içinde *C++ dil başvurusu*.

Tek bir yoktur **_set_new_handler** işleyicisi tüm dinamik olarak bağlı DLL'leri ya da çalıştırılabilir öğelerinde; bile çağırırsanız **_set_new_handler** işleyiciniz başka tarafından değiştirilebilir veya değiştirdiğiniz bir başka bir DLL veya yürütülebilir dosya tarafından ayarlanan işleyici.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_new_handler**|\<New.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Ayırma başarısız olduğunda, bu örnekte, denetimi için MyNewHandler aktarılır. MyNewHandler için geçirilen bağımsız değişken istenen bayt sayısıdır. Ayırma denenen olup olmadığını belirten bir bayrak MyNewHandler döndürülen değer olan: ayırma yeniden ve sıfır değeri ayırma başarısız olduğunu gösteren sıfır olmayan bir değer gösterir.

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
