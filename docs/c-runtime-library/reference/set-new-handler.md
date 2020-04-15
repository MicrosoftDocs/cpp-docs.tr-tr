---
title: _set_new_handler
ms.date: 4/2/2020
api_name:
- _set_new_handler
- _o__set_new_handler
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_new_handler
- set_new_handler
helpviewer_keywords:
- _set_new_handler function
- set_new_handler function
- error handling
- transferring control to error handler
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
ms.openlocfilehash: c3f1b9bd8bf2a4404e2239858e4c3c59b755bacd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332370"
---
# <a name="_set_new_handler"></a>_set_new_handler

**Yeni** işleç bellek tahsis etmezse denetimi hata işleme mekanizmanıza aktarın.

## <a name="syntax"></a>Sözdizimi

```cpp
_PNH _set_new_handler( _PNH pNewHandler );
```

### <a name="parameters"></a>Parametreler

*pNewHandler*<br/>
Uygulama tarafından sağlanan bellek işleme işlevini işaretçi. 0 bağımsız değişkeni yeni işleyicinin kaldırılmasına neden olur.

## <a name="return-value"></a>Dönüş Değeri

Önceki işlevin daha sonra geri yüklenabilmesi **için, _set_new_handler**tarafından kayıtlı önceki özel durum işleme işlevine bir işaretçiyi döndürür. Önceki işlev ayarlanmadıysa, iade değeri varsayılan davranışı geri yüklemek için kullanılabilir; bu değer **NULL**olabilir.

## <a name="remarks"></a>Açıklamalar

C++ **_set_new_handler** işlevi, **yeni** işleç bellek ayırmayı başamazsa denetimi ele alan bir özel durum işleme işlevi belirtir. **Yeni** başarısız olursa, çalışma zamanı sistemi otomatik olarak **_set_new_handler**için bir bağımsız değişken olarak geçirilen özel durum işleme işlevini çağırır. **_PNH,** New.h tanımlanan, türü **int** döndürür ve tür **size_t**bir argüman alır bir işlev için bir işaretçi. Tahsis edilecek alan miktarını belirtmek için **size_t** kullanın.

Varsayılan işleyici yok.

**_set_new_handler** aslında bir çöp toplama şemasıdır. Çalışma zamanı sistem ayırmayı, işleviniz her sıfır olmayan bir değeri döndürür ve işleviniz 0'ı döndürürse başarısız olur.

Programdaki **_set_new_handler** işlevinin oluşması, bağımsız değişken listesinde belirtilen özel durum işleme işlevini çalışma zamanı sistemine kaydeder:

```cpp
// set_new_handler1.cpp
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

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

**_set_new_handler** işlevine en son geçirilen işlev adresini kaydedebilir ve daha sonra eski haline getirebilirsiniz:

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

C++ [_set_new_mode](set-new-mode.md) işlevi [malloc](malloc.md)için yeni işleyici modunu ayarlar. Yeni işleyici modu, hata, **malloc** **_set_new_handler**tarafından ayarlanan yeni işleyici yordamı aramak olup olmadığını gösterir. Varsayılan olarak, **malloc** bellek tahsis başarısız yeni işleyici yordamı aramaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, böylece **malloc** bellek ayırmayı başaramayınca, **malloc** **yeni** işleyici yordamını yeni işlecinin aynı nedenle başarısız olduğu gibi çağırır. Varsayılanı geçersiz kılmak için şu çağrıyı

```cpp
_set_new_mode(1);
```

programınızın erken veya Newmode.obj ile bağlantı.

Kullanıcı tanımlı `operator new` bir sağlanırsa, yeni işleyici işlevleri otomatik olarak hata çağrılmaz.

Daha fazla bilgi için *C++ Dil*Referansı'nda [yeni](../../cpp/new-operator-cpp.md) ve [silme](../../cpp/delete-operator-cpp.md) ye bakın.

Tüm dinamik olarak birbirine bağlı DL'ler veya çalıştırılabilir ler için tek bir **_set_new_handler** işleyicisi vardır; **_set_new_handler** çağırsanız bile işleyiciniz başka bir dll veya çalıştırılabilir tarafından ayarlanmış bir işleyiciyi değiştirebilirsiniz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_new_handler**|\<new.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu örnekte, ayırma başarısız olduğunda, denetim MyNewHandler aktarılır. MyNewHandler'a geçirilen bağımsız değişken, istenen bayt sayısıdır. MyNewHandler'dan döndürülen değer, ayırmanın yeniden denenip denemeyeceğini belirten bir bayraktır: sıfır olmayan bir değer ayırmanın yeniden denenmesi gerektiğini gösterir ve sıfır değer ayırmanın başarısız olduğunu gösterir.

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
[Ücret -siz](free.md)<br/>
[realloc](realloc.md)<br/>
