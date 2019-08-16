---
title: _resetstkoflw
ms.date: 11/04/2016
apiname:
- _resetstkoflw
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
apitype: DLLExport
f1_keywords:
- resetstkoflw
- _resetstkoflw
helpviewer_keywords:
- resetstkoflw function
- stack overflow
- stack, recovering
- _resetstkoflw function
ms.assetid: 319529cd-4306-4d22-810b-2063f3ad9e14
ms.openlocfilehash: fc8a625e767daeb964f838c91f74732c9bd337a4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69499491"
---
# <a name="_resetstkoflw"></a>_resetstkoflw

Yığın taşmasından kurtarır.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _resetstkoflw( void );
```

## <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışında, başarısız olursa sıfır.

## <a name="remarks"></a>Açıklamalar

**_Resetstkoflw** işlevi bir yığın taşma koşulunu kurtarır, bu da bir programın önemli bir özel durum hatasıyla başarısız olması yerine devam etmesine izin verir. **_Resetstkoflw** işlevi çağrılmadığından, önceki özel durumdan sonra koruma sayfası yoktur. Bir sonraki sefer bir yığın taşması olduğunda, hiç özel durum yoktur ve işlem uyarı vermeden sonlandırılır.

Bir uygulamadaki bir iş parçacığı **EXCEPTION_STACK_OVERFLOW** özel durumuna neden oluyorsa, iş parçacığı yığınını hasarlı durumda bıraktı. Bu, yığının bozuk olmadığı **EXCEPTION_ACCESS_VIOLATION** veya **EXCEPTION_INT_DIVIDE_BY_ZERO**gibi diğer özel durumlara karşı farklıdır. Program ilk yüklendiğinde yığın rasgele küçük bir değere ayarlanır. Yığın daha sonra iş parçacığının ihtiyaçlarını karşılamak için isteğe bağlı olarak artar. Bu, geçerli yığının sonunda PAGE_GUARD erişimine sahip bir sayfa yerleştirilerek uygulanır. Daha fazla bilgi için bkz. [koruma sayfaları oluşturma](/windows/win32/Memory/creating-guard-pages).

Kod, yığın işaretçisinin bu sayfadaki bir adrese işaret etmesine neden olduğunda, bir özel durum oluşur ve sistem aşağıdaki üç şeyi yapar:

- PAGE_GUARD korumasını koruma sayfasında kaldırır, böylece iş parçacığı belleğe veri okuyup yazabilir.

- Son bir sayfanın altında bir sayfa bulunan yeni bir koruyucu sayfası ayırır.

- Özel durumu tetikleyen yönergeyi yeniden çalıştırır.

Bu şekilde, sistem iş parçacığı için yığının boyutunu otomatik olarak artırabilir. Bir işlemdeki her iş parçacığının en büyük yığın boyutu vardır. Yığın boyutu, [/Stack (yığın ayırmaları)](../../build/reference/stack-stack-allocations.md)veya proje için. def dosyasındaki [STACKSIZE](../../build/reference/stacksize.md) ifadesiyle derleme zamanında ayarlanır.

Bu en büyük yığın boyutu aşıldığında, sistem aşağıdaki üç şeyi yapar:

- , Daha önce açıklandığı gibi koruma sayfasında PAGE_GUARD korumasını kaldırır.

- Son sayfanın altında yeni bir koruyucu sayfası ayırmaya çalışır. Ancak, en büyük yığın boyutu aşıldığı için bu başarısız olur.

- İş parçacığının özel durum bloğunda işleyebilmesi için bir özel durum oluşturur.

Bu noktada yığının artık bir Guard sayfası olmadığını unutmayın. Bir sonraki sefer, bir koruyucu sayfa olması gereken her seferinde yığın sonuna kadar bir süre büyüdükçe, program yığının sonunun ötesinde yazar ve erişim ihlaline neden olur.

**_Resetstkoflw** çağrısını, bir yığın taşması özel durumu sonrasında kurtarma işlemi tamamlandığında koruma sayfasını geri yüklemek için çağırın. Bu işlev, bir **__except** bloğunun ana gövdesinin içinden veya bir **__except** bloğunun dışında çağrılabilir. Bununla birlikte, ne zaman kullanılması gerektiği konusunda bazı kısıtlamalar vardır. **_resetstkoflw** hiçbir şekilde çağrılmamalıdır:

- Filtre ifadesi.

- Bir filtre işlevi.

- Bir filtre işlevinden çağrılan işlev.

- Bir **catch** bloğu.

- Bir **__finally** bloğu.

Bu noktalarda, yığın henüz yeterince uygun değildir.

Yığın taşması özel durumları özel durumlar değil C++ , yapılandırılmış özel durumlar olarak oluşturulur. bu nedenle, bir yığın taşması özel durumunu yakalayacağından, **_resetstkoflw** sıradan bir **catch** bloğunda yararlı değildir. Ancak, C++ özel durum oluşturan yapılandırılmış bir özel durum çeviricisini uygulamak için [_set_se_translator](set-se-translator.md) kullanılırsa (ikinci örnekte olduğu gibi), bir yığın taşması özel durumu bir C++ catch bloğu tarafından C++ işlenebilen bir özel durum oluşur .

Yapılandırılmış özel durum çevirici işlevi tarafından oluşturulan bir özel durumla ulaşılan bir C++ catch bloğunda **_resetstkoflw** çağrısı yapmak güvenli değildir. Bu durumda, yığın alanı serbest bırakılmaz ve yığın işaretçisi, catch bloğundan önce geri çevrilebilir nesneler için çağrılsa bile, catch bloğunun dışına çıkana kadar sıfırlanmaz. Bu işlev, yığın alanı serbest bırakılır ve yığın işaretçisi sıfırlanana kadar çağrılmamalıdır. Bu nedenle, yalnızca catch bloğundan çıkıldıktan sonra çağrılmalıdır. Bir önceki yığın taşmasından kurtarmaya çalışan catch bloğunda oluşan bir yığın taşması kurtarılabilir olmadığından ve taşma sırasında programın yanıt vermemesine neden olabileceği için, olası çok az yığın alanı catch bloğunda kullanılmalıdır. Catch bloğunda, kendisi aynı catch bloğu tarafından işlenen bir özel durum tetikler.

**_Resetstkoflw** 'ın, bir **__except** bloğu içinde olduğu gibi doğru bir konumda kullanılsa bile başarısız olduğu durumlar vardır. Yığını geri döndürmeden sonra bile, yığının son sayfasına yazmadan **_resetstkoflw** yürütmek için yeterli yığın alanı kalmadı, **_resetstkoflw** koruyucu sayfa olarak yığının son sayfasını sıfırlayamaz ve 0 döndürür. hata olduğunu gösterir. Bu nedenle, bu işlevin güvenli kullanımı, yığının kullanım açısından güvenli olduğunu varsaymak yerine dönüş değerinin denetlenmesini içermelidir.

Yapılandırılmış özel durum işleme, uygulama **/clr** ile derlendiğinde bir **STATUS_STACK_OVERFLOW** özel durumu yakalayamaz (bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_resetstkoflw**|\<malloc. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kütüphaneler** [CRT kitaplığı özelliklerinin](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

Aşağıdaki örnek, **_resetstkoflw** işlevinin önerilen kullanımını gösterir.

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
       // at this point, the stack is not yet unwound.
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

### <a name="description"></a>Açıklama

Aşağıdaki örnek, yapılandırılmış özel durumların C++ özel durumlara dönüştürüldüğü bir programda **_resetstkoflw** 'ın önerilen kullanımını gösterir.

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

[_alloca](alloca.md)<br/>
