---
title: _resetstkoflw
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: dfe0de4f48173a0e79bcdcfb24bfdf7a21f47a04
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332814"
---
# <a name="_resetstkoflw"></a>_resetstkoflw

Yığın taşması kurtarır.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _resetstkoflw( void );
```

## <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır, başarısız olursa sıfır.

## <a name="remarks"></a>Açıklamalar

**_resetstkoflw** işlevi, bir yığın taşma durumundan kurtarır ve bir programın önemli bir özel durum hatasıyla başarısız olmak yerine devam etmesine olanak sağlar. **_resetstkoflw** işlevi çağrılmazsa, önceki özel durum sonra hiçbir koruma sayfaları vardır. Bir sonraki yığın taşma olduğunda, hiçbir istisna yoktur ve işlem uyarı olmadan sona erer.

Bir uygulamadaki iş parçacığı **EXCEPTION_STACK_OVERFLOW** özel bir duruma neden olursa, iş parçacığı yığınını hasarlı durumda bırakmıştır. Bu, yığının zarar görmediğini **EXCEPTION_ACCESS_VIOLATION** veya **EXCEPTION_INT_DIVIDE_BY_ZERO**gibi diğer özel durumlara zıttır. Program ilk yüklendiğinde yığın rasgele küçük bir değere ayarlanır. Yığın daha sonra iş parçacığının gereksinimlerini karşılamak için isteğe bağlı olarak büyür. Bu, geçerli yığının sonuna PAGE_GUARD erişimi olan bir sayfa yerleştirilerek uygulanır. Daha fazla bilgi için [bkz.](/windows/win32/Memory/creating-guard-pages)

Kod yığın işaretçisinin bu sayfadaki bir adresi işaret etmesiyle ilgili bir özel durum oluşur ve sistem aşağıdaki üç şeyi yapar:

- İş parçacığının belleğe veri okuyup yazabilmesi için koruma sayfasındaki PAGE_GUARD korumasını kaldırır.

- Sonuncusunun bir sayfasının altında bulunan yeni bir koruma sayfası ayırır.

- Özel durumu yükselten talimatı yeniden çalıştırın.

Bu şekilde, sistem iş parçacığı için yığının boyutunu otomatik olarak artırabilir. Bir işlemdeki her iş parçacığının maksimum yığın boyutu vardır. Yığın boyutu derleme zamanında [/STACK (Stack Ayırmaları)](../../build/reference/stack-stack-allocations.md)veya proje için .def dosyasındaki [STACKSIZE](../../build/reference/stacksize.md) deyimi tarafından ayarlanır.

Bu maksimum yığın boyutu aşıldığında, sistem aşağıdaki üç şeyi yapar:

- Daha önce açıklandığı gibi koruma sayfasındaki PAGE_GUARD korumasını kaldırır.

- Sonuncusunun altına yeni bir koruma sayfası ayırmaya çalışır. Ancak, en büyük yığın boyutu aşıldığından bu başarısız olur.

- İş parçacığının özel durum bloğunda işleyebilir, özel durum yükseltir.

Bu noktada, yığının artık bir koruma sayfası olmadığını unutmayın. Bir sonraki program yığını sonuna kadar büyüttüğünde, koruma sayfasının olması gereken yerde, program yığının sonuna kadar yazar ve bir erişim ihlaline neden olur.

Yığın taşması özel durumu sonrasında kurtarma yapıldığında koruma sayfasını geri yüklemek için **_resetstkoflw** çağırın. Bu **işlev, bir __except** bloğunana gövdesinin içinden veya **__except** bloğun un dışından çağrılabilir. Ancak, ne zaman kullanılması gerektiği konusunda bazı kısıtlamalar vardır. **_resetstkoflw** asla şu nedenlerden çağrılmamalıdır:

- Filtre ifadesi.

- Bir filtre işlevi.

- Filtre işlevinden çağrılan bir işlev.

- Bir **yakalama** bloğu.

- **Bir __finally** bloğu.

Bu noktalarda, yığın henüz yeterince çözülmemiş değildir.

Yığın taşması özel durumları, C++ özel durumları olarak değil, yapılandırılmış özel durumlar olarak oluşturulur, bu nedenle **_resetstkoflw,** yığın taşma özel durum yakalamaz çünkü sıradan bir **catch** bloğunda yararlı değildir. Ancak, [_set_se_translator](set-se-translator.md) C++ özel durumlar (ikinci örnekte olduğu gibi) atan yapılandırılmış bir özel durum çevirmeni uygulamak için kullanılırsa, yığın taşması özel durumu C++ catch bloğu tarafından işlenebilen bir C++ özel durumuyla sonuçlanır.

Yapılandırılmış özel durum çevirmen işlevi tarafından atılan bir özel durum ulaşılan bir C++ catch bloğunda **_resetstkoflw** aramak güvenli değildir. Bu durumda, yığın alanı serbest bırakılmaz ve yığın işaretçisi catch bloğu dışında kadar sıfırlanmaz, yıkıcılar catch bloğundan önce yok edilebilir nesneler için çağrılmış olsa bile. Yığın alanı serbest bırakılından ve yığın işaretçisi sıfırlanana kadar bu işlev çağrılmamalıdır. Bu nedenle, yalnızca catch bloğundan çıktıktan sonra çağrılmalıdır. Catch bloğunda mümkün olduğunca az yığın alanı kullanılmalıdır, çünkü bir önceki yığın taşmasından kurtulmaya çalışan catch bloğunda oluşan bir yığın taşma kurtarılamaz ve yakalama bloğundaki taşma aynı catch bloğu tarafından işlenen bir özel durumu tetiklediği için programın yanıt vermeyi durdurmasına neden olabilir.

**__except** bloğu gibi doğru bir konumda kullanılsa bile **_resetstkoflw** başarısız olabileceği durumlar vardır. Yığını gevşettikten sonra bile, yığının son sayfasına yazmadan **_resetstkoflw** yürütmek için hala yeterli yığın alanı kalmamışsa, **_resetstkoflw** yığının son sayfasını koruma sayfası olarak sıfırlayamazsa ve hatayı gösteren 0 döndürür. Bu nedenle, bu işlevin güvenli kullanımı yığının kullanımı güvenli olduğunu varsayarak yerine iade değerini denetlemeyi içermelidir.

Yapılandırılan özel durum işleme, uygulama **/clr** ile derlendiğinde **STATUS_STACK_OVERFLOW** bir özel durum yakalamaz (bkz. [/clr (Ortak Dil Çalışma Süresi Derlemesi).](../../build/reference/clr-common-language-runtime-compilation.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_resetstkoflw**|\<malloc.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

**Kütüphaneler:** [CRT Kitaplık Özellikleri'nin](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

Program bağımsız değişkeni olmayan örnek çıktı:

```Output
loop #1
```

Program daha fazla yineleme yürütmeden yanıt vermeyi durdurur.

Program bağımsız değişkenleri ile:

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

Aşağıdaki örnek, yapılandırılmış özel durumların C++ özel durumlara dönüştürüldüğü bir programda **_resetstkoflw** önerilen kullanımını gösterir.

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
