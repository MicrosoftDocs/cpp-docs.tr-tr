---
title: _resetstkoflw | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d62044e3af91846e93f7c62dc6a6f810df506ef6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="resetstkoflw"></a>_resetstkoflw

Yığın taşması kurtarır.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _resetstkoflw( void );
```

## <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, başarısız olursa sıfır sıfır olmayan.

## <a name="remarks"></a>Açıklamalar

**_Resetstkoflw** işlevi kurtarır önemli özel durum hatası ile başarısız oluyor yerine devam etmek bir program sağlayan bir yığın taşması koşulunu gelen. Varsa **_resetstkoflw** işlev çağrılmaz, önceki özel durumdan sonra koruma sayfa yok. Bir yığın olduğunu başlattığınızda taşması, hiçbir özel durum hiç ve vardır uyarmadan işlemi sonlandırır.

Bir uygulama bir iş parçacığında neden olursa bir **EXCEPTION_STACK_OVERFLOW** özel durum, iş parçacığı sol kendi yığını bozuk bir durumda. Bu diğer özel durumlar aksine olduğu gibi **EXCEPTION_ACCESS_VIOLATION** veya **EXCEPTION_INT_DIVIDE_BY_ZERO**, burada yığını bozuk. Program ilk yüklendiğinde yığın rasgele düşük bir değere ayarlanır. Yığın sonra iş parçacığı ihtiyaçlarını karşılamak için isteğe bağlı olarak artar. Bu, geçerli yığının sonuna PAGE_GUARD erişim içeren bir sayfa koyarak uygulanır. Daha fazla bilgi için bkz: [koruma sayfaları oluşturma](http://msdn.microsoft.com/library/windows/desktop/aa366549).

Bu sayfada bir adresine işaret edecek şekilde yığın işaretçisi kod neden olduğunda, bir özel durum oluşur ve sistem aşağıdaki üç şey yapar:

- Böylece iş parçacığı okumak ve yazmak için bellek koruma sayfasında PAGE_GUARD korumasını kaldırır.

- Yeni bir koruma ayırır sayfasında başka bir deyişle sonuncu aşağıda bulunan bir sayfa.

- Özel durum oluşturuldu yönerge yeniden çalıştırır.

Bu şekilde, sistem otomatik olarak iş parçacığı için yığın boyutunu artırabilirsiniz. Bir işlemdeki her bir iş parçacığı maksimum yığın boyutu vardır. Yığın boyutu tarafından derleme zamanında ayarlanır [/STACK (yığın ayırmaları)](../../build/reference/stack-stack-allocations.md), ya da [STACKSIZE](../../build/reference/stacksize.md) projesi için .def dosyası deyimi.

Bu maksimum yığın boyutunu aşıldığında, sistem aşağıdaki üç şey yapar:

- Daha önce açıklandığı gibi koruma sayfasında PAGE_GUARD korumasını kaldırır.

- Sonuncu altında yeni bir koruma sayfa ayırmaya çalışır. Ancak, en fazla yığın boyutunu aştığından bu başarısız olur.

- Bir özel durum, iş parçacığı özel durum bloğunda işleyebilecek şekilde yükseltir.

Bu noktada, yığın artık koruma sayfası sahip olduğunu unutmayın. Program yığının sonuna tüm büyür sonraki açışınızda koruma sayfası olması gerektiğini burada program yığının sonuna yazar ve erişim ihlaline neden oluyor.

Çağrı **_resetstkoflw** kurtarma yığın taşması özel durumdan sonra yapılır her koruma sayfası geri yüklemek için. Bu işlev ana gövdesi içinde çağrılabilir bir **__except** blok veya dış bir **__except** bloğu. Ancak, ne zaman kullanılmalı bazı kısıtlamalar vardır. **_resetstkoflw** hiçbir zaman öğesinden çağrılması:

- Bir filtre ifadesi.

- Bir filtre işlevi.

- Bir filtre işlevinden adlı bir işlev.

- A **catch** bloğu.

- A **__finally** bloğu.

Bu noktalarda yığın henüz yeterince unwound değil.

Yığın taşması özel durum oluşturulur yapılandırılmış özel durum olarak C++ özel durumlarını değil, bu nedenle **_resetstkoflw** bir sıradan kullanışlı değildir **catch** bir yığın taşması özel durumu yakalamaz çünkü engelleyin. Ancak, varsa [_set_se_translator](set-se-translator.md) (ikinci örnekteki gibi), C++ özel durum atar yapılandırılmış özel durum Çeviricisi uygulamak için kullanılan bir C++ tarafından işlenebilen bir C++ özel durum yığın taşması özel durumu sonuçlarında catch Blok.

Çağırmak güvenli değildir **_resetstkoflw** yapılandırılmış özel durum Çeviricisi işlevi tarafından oluşturulan bir özel gelen ulaşıldığında bir C++ catch bloğu içinde. Bu durumda, yığın alanı serbest ve catch bloğu dışında rağmen Yıkıcılar catch bloğu önce destructible tüm nesneler için çağrıldıktan kadar yığın işaretçisi sıfırlanmaz. Bu işlev yığın alanı serbest ve yığın işaretçisi sıfırlama kadar çağrılmamalıdır. Bu nedenle, yalnızca catch bloğu çıktıktan sonra çağrılmalıdır. Kendisi bir önceki yığın taşması Kurtarmaya çalışılıyor catch bloğu içinde oluşan bir yığın taşması programının taşma yanıt vermeyi durdurmasına neden olabilir ve kurtarılabilir olmadığından, mümkün olduğunca küçük yığın alanı içindeki yakalama bloğunun kullanılmalıdır catch bloğu Tetikleyicileri kendisi tarafından aynı işlenir bir özel durum catch bloğu.

Bazı durumlarda nerede **_resetstkoflw** içinde gibi bir doğru konumda kullanılan olsa bile başarısız olabilir bir **__except** bloğu. Hatta yığını geriye doğru izleme sonra yok, hala sol yürütmek için yeterli yığın alanı **_resetstkoflw** yığınının son sayfasına yazmadan **_resetstkoflw** son sayfasına sıfırlayamaz yığın koruma sayfası ve hata olduğunu gösteren 0, döndürür. Bu nedenle, bu işlevin güvenli kullanım yığın güvenli olduğu varsayılarak dönüş değerini yerine denetimi içermelidir.

Yapılandırılmış özel durum işleme değil catch bir **STATUS_STACK_OVERFLOW** ile uygulama derlendiğinde özel durum **/CLR** (bkz:  [ /CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_resetstkoflw**|\<malloc.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** tüm sürümlerini [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, önerilen kullanımını gösterir **_resetstkoflw** işlevi.

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

Örnek program bağımsız değişkenler olmadan çıktı:

```Output
loop #1
```

Program, daha fazla yineleme çalıştırmadan yanıt vermiyor.

Program bağımsız değişkenler:

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

Aşağıdaki örnek, önerilen kullanımını gösterir **_resetstkoflw** burada yapılandırılmış özel durum dönüştürülür C++ özel durumlarını programı.

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
