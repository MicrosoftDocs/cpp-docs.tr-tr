---
description: 'Hakkında daha fazla bilgi edinin: _set_new_handler'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 1e693e010bcbb9489426fc5c67e888d50f430765
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312403"
---
# <a name="_set_new_handler"></a>_set_new_handler

Operatör bellek ayıramazsa, denetimi hata işleme mekanizmanıza aktarır **`new`** .

## <a name="syntax"></a>Sözdizimi

```cpp
_PNH _set_new_handler( _PNH pNewHandler );
```

### <a name="parameters"></a>Parametreler

*pNewHandler*<br/>
Uygulama tarafından sağlanan bellek işleme işlevine yönelik işaretçi. 0 bağımsız değişkeni, yeni işleyicinin kaldırılmasına neden olur.

## <a name="return-value"></a>Dönüş Değeri

Önceki işlevin daha sonra geri yüklenebilmesi için, **_set_new_handler** tarafından kaydedilen önceki özel durum işleme işlevine yönelik bir işaretçi döndürür. Önceki bir işlev ayarlanmamışsa, varsayılan davranışı geri yüklemek için dönüş değeri kullanılabilir; Bu değer **null** olabilir.

## <a name="remarks"></a>Açıklamalar

C++ **_set_new_handler** işlevi, **`new`** işleç bellek ayıramazsa denetimi karşılayan bir özel durum işleme işlevi belirtir. **`new`** Başarısız olursa, çalışma zamanı sistemi otomatik olarak **_set_new_handler** bir bağımsız değişken olarak geçirilen özel durum işleme işlevini çağırır. New. h içinde tanımlanan **_PNH**, türü döndüren **`int`** ve **size_t** türünde bir bağımsız değişken alan bir işlev işaretçisidir. Ayrılacak alan miktarını belirtmek için **size_t** kullanın.

Varsayılan işleyici yok.

**_set_new_handler** aslında bir atık toplama düzenidir. İşleviniz sıfır dışında bir değer döndürdüğünde çalışma zamanı sistemi yeniden deneme süresi ayırması, işleviniz 0 döndürürse başarısız olur.

Bir programdaki **_set_new_handler** işlevinin bir oluşumu, bağımsız değişken listesinde belirtilen özel durum işleme işlevini çalışma zamanı sistemiyle kaydeder:

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

**_Set_new_handler** işlevine en son geçirilen işlev adresini kaydedebilir ve daha sonra yeniden devreye girebilirsiniz:

```cpp
   _PNH old_handler = _set_new_handler( my_handler );
   // Code that requires my_handler
   // . . .
   _set_new_handler( old_handler )
   // Code that requires old_handler
   // . . .
```

C++ [_set_new_mode](set-new-mode.md) işlevi, [malloc](malloc.md)için yeni işleyici modunu ayarlar. Yeni işleyici modu, hata durumunda **malloc** 'ın **_set_new_handler** tarafından ayarlanan yeni işleyici yordamını çağırıp çağırmayacağını gösterir. Varsayılan olarak, **malloc** bellek ayırma hatası üzerine yeni işleyici yordamını çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, böylece **malloc** bellek ayıramadığında, **malloc** yeni işleyici yordamını **`new`** aynı nedenden dolayı başarısız olduğunda işlecin yaptığı şekilde çağırır. Varsayılanı geçersiz kılmak için şunu çağırın:

```cpp
_set_new_mode(1);
```

programınızın başlarında veya NewMode. obj ile bağlantılandırın.

Kullanıcı tanımlı bir `operator new` sağlanmışsa, yeni işleyici işlevleri hata durumunda otomatik olarak çağrılmaz.

Daha fazla bilgi için bkz. *C++ dil başvurusunda* [Yeni](../../cpp/new-operator-cpp.md) ve [Sil](../../cpp/delete-operator-cpp.md) .

Dinamik olarak bağlı tüm dll 'Ler veya yürütülebilir dosyalar için tek bir **_set_new_handler** işleyicisi vardır; **_set_new_handler** çağırsanız bile işleyiciniz başka bir dll veya yürütülebilir dosya tarafından ayarlanmış bir işleyiciyi değiştirmiş olabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_new_handler**|\<new.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu örnekte, ayırma başarısız olduğunda denetim MyNewHandler 'a aktarılır. MyNewHandler öğesine geçirilen bağımsız değişken istenen bayt sayısıdır. MyNewHandler 'tan döndürülen değer ayırmanın yeniden denenip denenmeyeceğini belirten bir bayrak olur: sıfır dışında bir değer ayırmanın yeniden deneneceği ve sıfır değerinde ayırmanın başarısız olduğunu gösterir.

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

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[Süz](free.md)<br/>
[realloc](realloc.md)<br/>
