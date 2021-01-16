---
description: 'Hakkında daha fazla bilgi edinin: _resetstkoflw'
title: _resetstkoflw
ms.date: 1/14/2021
api_name:
- _resetstkoflw
- _o__resetstkoflw
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
- api-ms-win-crt-private-l1-1-0.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- resetstkoflw
- _resetstkoflw
helpviewer_keywords:
- resetstkoflw function
- stack overflow
- stack, recovering
- _resetstkoflw function
ms.assetid: 319529cd-4306-4d22-810b-2063f3ad9e14
ms.openlocfilehash: 092eea34de10ff77a31b5be35fa84dc1eb887328
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242975"
---
# `_resetstkoflw`

Yığın taşmasından kurtarır.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _resetstkoflw( void );
```

## <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında, başarısız olursa sıfır.

## <a name="remarks"></a>Açıklamalar

**`_resetstkoflw`** İşlevi bir yığın taşması durumundan kurtarır, bir programın önemli bir özel durum hatasıyla başarısız olması yerine devam etmesine izin verir. **`_resetstkoflw`** İşlev çağrılmazsa, önceki özel durumdan sonra koruma sayfası yoktur. Bir sonraki sefer bir yığın taşması olduğunda, hiç özel durum yoktur ve işlem uyarı vermeden sonlandırılır.

Bir uygulamadaki bir iş parçacığı bir **`EXCEPTION_STACK_OVERFLOW`** özel duruma neden oluyorsa, iş parçacığı yığınını hasarlı durumda bıraktı. Bu, veya gibi diğer özel durumlara karşı, **`EXCEPTION_ACCESS_VIOLATION`** **`EXCEPTION_INT_DIVIDE_BY_ZERO`** yığın bozulmamış olabilir. Program ilk yüklendiğinde yığın rasgele küçük bir değere ayarlanır. Yığın daha sonra iş parçacığının ihtiyaçlarını karşılamak için isteğe bağlı olarak artar. Bu, geçerli yığının sonunda PAGE_GUARD erişimine sahip bir sayfa yerleştirilerek uygulanır. Daha fazla bilgi için bkz. [koruma sayfaları oluşturma](/windows/win32/Memory/creating-guard-pages).

Kod, yığın işaretçisinin bu sayfadaki bir adrese işaret etmesine neden olduğunda, bir özel durum oluşur ve sistem aşağıdaki üç şeyi yapar:

- Koruma sayfasındaki PAGE_GUARD korumayı kaldırır, böylece iş parçacığı belleğe veri okuyup yazabilir.

- Son bir sayfanın altında bir sayfa bulunan yeni bir koruyucu sayfası ayırır.

- Özel durumu tetikleyen yönergeyi yeniden çalıştırır.

Bu şekilde, sistem iş parçacığı için yığının boyutunu otomatik olarak artırabilir. Bir işlemdeki her iş parçacığının en büyük yığın boyutu vardır. Yığın boyutu, derleme zamanında [ `/STACK` (yığın ayırmaları)](../../build/reference/stack-stack-allocations.md)veya [`STACKSIZE`](../../build/reference/stacksize.md) `.def` Proje dosyasındaki ifadesiyle ayarlanır.

Bu en büyük yığın boyutu aşıldığında, sistem aşağıdaki üç şeyi yapar:

- Koruma sayfasında daha önce açıklandığı gibi PAGE_GUARD korumayı kaldırır.

- Son sayfanın altında yeni bir koruyucu sayfası ayırmaya çalışır. Ancak, en büyük yığın boyutu aşıldığı için bu başarısız olur.

- İş parçacığının özel durum bloğunda işleyebilmesi için bir özel durum oluşturur.

Bu noktada, yığının artık bir koruyucu sayfası yoktur. Bir sonraki sefer, bir koruyucu sayfa olması gereken her seferinde yığın sonuna kadar bir süre büyüdükçe, program yığının sonunun ötesinde yazar ve erişim ihlaline neden olur.

**`_resetstkoflw`** Bir yığın taşması özel durumu sonrasında kurtarma yapıldığında koruma sayfasını geri yükleme çağrısı yapın. Bu işlev, bir bloğun ana gövdesinin içinden **`__except`** veya bir bloğun dışında çağrılabilir **`__except`** . Bununla birlikte, ne zaman kullanılması gerektiği konusunda bazı kısıtlamalar vardır. **`_resetstkoflw`** çağrılmamalıdır:

- Filtre ifadesi.

- Bir filtre işlevi.

- Bir filtre işlevinden çağrılan işlev.

- Bir **`catch`** blok.

- Bir **`__finally`** blok.

Bu noktalarda, yığın henüz yeterince ölçeklendirmez.

Yığın taşması özel durumları, C++ özel durumları değil, yapılandırılmış özel durumlar olarak oluşturulur, **`_resetstkoflw`** **`catch`** Bu nedenle bir yığın taşması özel durumunu yakalayamayacağından sıradan bir blokta yararlı değildir. Ancak, [`_set_se_translator`](set-se-translator.md) c++ özel durumları oluşturan yapılandırılmış bir özel durum Çeviricisi uygulamak için kullanılırsa (ikinci örnekte olduğu gibi), bir yığın taşması özel durumu c++ catch bloğu tarafından işlenebilen bir c++ özel durumu oluşur.

**`_resetstkoflw`** Yapılandırılmış özel durum çevirici işlevi tarafından oluşturulan bir özel durumla ulaşılan C++ catch bloğunda çağrı yapmak güvenli değildir. Bu durumda, yığın alanı serbest bırakılmaz ve yığın bloğunun, catch bloğundan önce geri çevrilebilir nesneler için çağrılsa bile, catch bloğunun dışına çıkana kadar yığın işaretçisi sıfırlanmaz. Bu işlev, yığın alanı serbest bırakılır ve yığın işaretçisi sıfırlanana kadar çağrılmamalıdır. Bu nedenle, yalnızca catch bloğundan çıkıldıktan sonra çağrılmalıdır. Bir önceki yığın taşmasından kurtarmaya çalışan catch bloğunda oluşan bir yığın taşması kurtarılabilir olmadığından ve catch bloğunda taşma, kendisinin aynı catch bloğu tarafından işlendiği bir özel durum harekete geçirirse programın yanıt vermemesine neden olabileceğinden, catch bloğunda olabildiğince az yığın alanı kullanılmalıdır.

**`_resetstkoflw`** Bir blok içindeki gibi doğru bir konumda kullanılsalar bile başarısız olan durumlar vardır **`__except`** . Yığını geri döndürmeden sonra bile, yığının son sayfasına yazmadan yürütmek için yeterli yığın alanı yok **`_resetstkoflw`** , **`_resetstkoflw`** koruma sayfası olarak yığının son sayfasını sıfırlayamaz ve hata belirten 0 değerini döndürür. Bu işlevin güvenli kullanımı, yığının kullanım açısından güvenli olduğunu varsaymak yerine dönüş değerini denetlemeyi içermelidir.

Yapılandırılmış özel durum işleme **`STATUS_STACK_OVERFLOW`** , uygulama derlendiğinde bir özel durumu yakalayamaz **`/clr`** (bkz. [ `/clr ` (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**`_resetstkoflw`**|\<malloc.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** [CRT kitaplığı özelliklerinin](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

Aşağıdaki örnek, işlevinin önerilen kullanımını gösterir **`_resetstkoflw`** .

```C
// crt_resetstkoflw.c
// Launch program with and without arguments to observe
// the difference made by calling _resetstkoflw.

#include <malloc.h>
#include <stdio.h>
#include <windows.h>

void recursive(int recurse)
{
   _alloca(2000);
   if (recurse)
      recursive(recurse);
}

// Filter for the stack overflow exception.
// This function traps the stack overflow exception, but passes
// all other exceptions through.
int stack_overflow_exception_filter(int exception_code)
{
   if (exception_code == EXCEPTION_STACK_OVERFLOW)
   {
       // Do not call _resetstkoflw here, because
       // at this point, the stack isn't yet unwound.
       // Instead, signal that the handler (the __except block)
       // is to be executed.
       return EXCEPTION_EXECUTE_HANDLER;
   }
   else
       return EXCEPTION_CONTINUE_SEARCH;
}

int main(int ac)
{
   int i = 0;
   int recurse = 1, result = 0;

   for (i = 0 ; i < 10 ; i++)
   {
      printf("loop #%d\n", i + 1);
      __try
      {
         recursive(recurse);

      }

      __except(stack_overflow_exception_filter(GetExceptionCode()))
      {
         // Here, it is safe to reset the stack.

         if (ac >= 2)
         {
            puts("resetting stack overflow");
            result = _resetstkoflw();
         }
      }

      // Terminate if _resetstkoflw failed (returned 0)
      if (!result)
         return 3;
   }

   return 0;
}
```

Program bağımsız değişkenleri olmayan örnek çıkış:

```Output
loop #1
```

Program daha fazla yineleme yürütmeden yanıt vermeyi durduruyor.

Program bağımsız değişkenleriyle:

```Output
loop #1
resetting stack overflow
loop #2
resetting stack overflow
loop #3
resetting stack overflow
loop #4
resetting stack overflow
loop #5
resetting stack overflow
loop #6
resetting stack overflow
loop #7
resetting stack overflow
loop #8
resetting stack overflow
loop #9
resetting stack overflow
loop #10
resetting stack overflow
```

### <a name="description"></a>Description

Aşağıdaki örnek, **`_resetstkoflw`** yapılandırılmış özel durumların C++ özel durumlarına dönüştürüldüğü bir programda önerilen kullanımını gösterir.

### <a name="code"></a>Kod

```cpp
// crt_resetstkoflw2.cpp
// compile with: /EHa
// _set_se_translator requires the use of /EHa
#include <malloc.h>
#include <stdio.h>
#include <windows.h>
#include <eh.h>

class Exception { };

class StackOverflowException : Exception { };

// Because the overflow is deliberate, disable the warning that
// this function will cause a stack overflow.
#pragma warning (disable: 4717)
void CauseStackOverflow (int i)
{
    // Overflow the stack by allocating a large stack-based array
    // in a recursive function.
    int a[10000];
    printf("%d ", i);
    CauseStackOverflow (i + 1);
}

void __cdecl SEHTranslator (unsigned int code, _EXCEPTION_POINTERS*)
{
    // For stack overflow exceptions, throw our own C++
    // exception object.
    // For all other exceptions, throw a generic exception object.
    // Use minimal stack space in this function.
    // Do not call _resetstkoflw in this function.

    if (code == EXCEPTION_STACK_OVERFLOW)
        throw StackOverflowException ( );
    else
        throw Exception( );
}

int main ( )
{
    bool stack_reset = false;
    bool result = false;

    // Set up a function to handle all structured exceptions,
    // including stack overflow exceptions.
    _set_se_translator (SEHTranslator);

    try
    {
        CauseStackOverflow (0);
    }
    catch (StackOverflowException except)
    {
        // Use minimal stack space here.
        // Do not call _resetstkoflw here.
        printf("\nStack overflow!\n");
        stack_reset = true;
    }
    catch (Exception except)
    {
        // Do not call _resetstkoflw here.
        printf("\nUnknown Exception!\n");
    }
    if (stack_reset)
    {
        result = _resetstkoflw();
        // If stack reset failed, terminate the application.
        if (result == 0)
            exit(1);
    }

    void* pv = _alloca(100000);
    printf("Recovered from stack overflow and allocated 100,000 bytes"
           " using _alloca.");

    return 0;
}
```

```Output
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24
Stack overflow!
Recovered from stack overflow and allocated 100,000 bytes using _alloca.
```

## <a name="see-also"></a>Ayrıca bkz.

[`_alloca`](alloca.md)<br/>
