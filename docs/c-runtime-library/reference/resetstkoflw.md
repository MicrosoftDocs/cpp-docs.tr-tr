---
title: _resetstkoflw | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- resetstkoflw function
- stack overflow
- stack, recovering
- _resetstkoflw function
ms.assetid: 319529cd-4306-4d22-810b-2063f3ad9e14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31d3f647d2d72cf96c9b935c33376aae698464c8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207582"
---
# <a name="resetstkoflw"></a>_resetstkoflw

Yığın taşmasından kurtarır.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _resetstkoflw( void );
```

## <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır başarısız olursa sıfır dışı.

## <a name="remarks"></a>Açıklamalar

**_Resetstkoflw** koşulundan bir programın önemli özel durum hatasıyla başarısız olmak yerine devam etmesine izin vererek bir yığın taşması, işlev kurtarır. Varsa **_resetstkoflw** işlevi çağrılmazsa, önceki özel durumdan sonra koruma sayfa yok. Bir yığın olduğunu bir sonraki sefer, hiçbir özel durum vardır hiç ve uyarı vermeden işlemi sonlandırır.

Bir uygulama bir iş parçacığında neden olursa bir **exceptıon_stack_overflow** özel durum, iş parçacığı sol kendi yığınını zarar görmüş durumda. Bu gibi diğer özel durumlar aksine, **EXCEPTION_ACCESS_VIOLATION** veya **exceptıon_ınt_dıvıde_by_zero**, burada yığının bozuk. Yığın, program ilk yüklendiğinde rasgele olarak küçük bir değere ayarlanır. Yığın ardından iş parçacığının gereklerini karşılamak için istek üzerine büyür. Bu, geçerli yığın sonunda PAGE_GUARD erişimi olan bir sayfa koyarak uygulanır. Daha fazla bilgi için [koruyucu sayfa oluşturma](/windows/desktop/Memory/creating-guard-pages).

Bu sayfada bir adrese işaret edecek şekilde yığın işaretçisi kodu neden olduğunda, bir özel durum oluşur ve sistem aşağıdaki üç şeyi yapar:

- İş parçacığı okuyup belleğe veri yazma koruma sayfasının PAGE_GUARD korumasını kaldırır.

- Yeni bir koruma ayırır. diğer bir deyişle sayfanın bir altında konumlandırılmış bir sayfa.

- Özel duruma neden olan yönergeyi yeniden çalıştırır.

Bu şekilde, sistem otomatik olarak iş parçacığı yığın boyutunu artırabilir. Bir işlemdeki her iş parçacığının maksimum yığın boyutu vardır. Yığın boyutu derleme zamanında ayarlanır [/STACK (yığın ayırmaları)](../../build/reference/stack-stack-allocations.md), ya da [STACKSIZE](../../build/reference/stacksize.md) proje için .def dosyası deyimi.

Bu maksimum yığın boyutu aşıldığında, sistem aşağıdaki üç şeyi yapar:

- Koruma daha önce açıklandığı gibi sayfasının PAGE_GUARD korumasını kaldırır.

- Sonuncu altına yeni bir koruma sayfası ayırmaya çalışır. Ancak, maksimum yığın boyutu aşıldığı için bu başarısız olur.

- İş parçacığı özel durum bloğunda işleyebilmesi bir özel durum oluşturur.

Bu noktada, yığında artık koruma sayfası olmadığını unutmayın. Program yığının sonuna kadar tüm büyüdükçe sonraki açışınızda büyüttüğü bir koruma sayfası, program yığının sonunun yazar ve erişim ihlaline neden oluyor.

Çağrı **_resetstkoflw** her bir yığın taşması özel durumundan sonra kurtarma yapılır koruma sayfasını geri yüklemek için. Bu işlev ana gövdesi içinden çağrılabilen bir **__except** blok veya dış bir **__except** blok. Ancak, ne zaman kullanılmalıdır bazı kısıtlamalar vardır. **_resetstkoflw** asla çağrılmamalıdır:

- Bir filtre ifadesi.

- Bir filtre işlevi.

- Filtre işlevinden çağrılan işlev.

- A **catch** blok.

- A **__finally** blok.

Bu noktalarda yığın henüz yeterince çözülmüş değildir.

Yığın taşması özel durumları oluşturulur yapılandırılmış özel durumları değil C++ özel durumlarını, bu nedenle **_resetstkoflw** yakalayamayacağından değil **catch** bloğunda bir yığın taşması özel durumu yakalamaz. Ancak, varsa [_set_se_translator](set-se-translator.md) (ikinci örnekteki gibi), C++ özel durumlarını oluşturan bir yapılandırılmış özel durum Çeviricisi uygulamak için kullanılan bir C++ tarafından işlenebilen bir C++ özel durum yığın taşması özel durumu sonuçlarda yakalayın Blok.

Çağırmak güvenli değil **_resetstkoflw** yapılandırılmış özel durum Çevirici işleviyle atılan bir özel durumdan ulaşıldığında bir C++ catch bloğu içinde. Bu durumda, yığın alanı ve yığın işaretçisi catch bloğu dışında olsa bile Yıkıcılar yakalama bloğunun önündeki yıkıcı nesneler için çağrılmış kadar sıfırlanmaz. Bu işlev yığın alanı boşaltılana ve yığın işaretçisi sıfırlanana kadar çağrılmamalıdır. Bu nedenle, yalnızca catch bloğundan çıkıldıktan sonra çağrılmalıdır. Kendisi bir önceki yığın taşmasından kurtarma denemesi catch bloğu içinde oluşan bir yığın taşması program taşma yanıt vermeyi durdurmasına neden olabilir ve kurtarılabilir olmadığından, catch bloğunda olabildiğince küçük yığın alanı kullanılmalıdır catch bloğu Tetikleyicileri catch bloğu bir özel durum kendisi tarafından aynı işlenir.

Bazı durumlarda burada **_resetstkoflw** içinde olduğu gibi bir doğru konumda kullanılsa bile başarısız olabilir bir **__except** blok. Yığın bırakıldıktan sonra bile, yok, hala yürütmek için yeterli yığın alanı **_resetstkoflw** yığının son sayfasına yazmadan **_resetstkoflw** son sayfasında sıfırlayamaz. yığın, 0 döndürür ve koruma sayfası olarak. Bu nedenle, bu işlevin güvenli kullanımı, yığının güvenli olduğunu varsayarak, dönüş değeri yerine denetlenmesini içermelidir.

Yapılandırılmış özel durum işleme yakalamaz bir **STATUS_STACK_OVERFLOW** uygulama ile derlendiğinde bir özel durum **/CLR** (bkz  [ /CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_resetstkoflw**|\<malloc.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** tüm sürümlerini [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, önerilen kullanımını gösterir. **_resetstkoflw** işlevi.

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

Program bağımsız değişken olmadan çıktı örneği:

```Output
loop #1
```

Program, daha fazla yinelemeyi çalıştırmadan yanıt vermeyi durdurur.

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

Aşağıdaki örnek, önerilen kullanımını göstermektedir **_resetstkoflw** yapılandırılmış özel durumları C++ özel durumlarına dönüştürülen olduğu bir programda.

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
