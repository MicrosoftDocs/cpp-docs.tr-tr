---
title: _set_se_translator
ms.date: 02/21/2018
apiname:
- _set_se_translator
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
- _set_se_translator
- set_se_translator
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
ms.openlocfilehash: 23eb4e9016666567771832cefed686cb9197b02f
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299702"
---
# <a name="setsetranslator"></a>_set_se_translator

Win32 özel durumlarını (C yapılandırılmış özel durumlar) C++ tür özel durumlara çevirmek için iş parçacığı başına geri çağırma işlevini ayarlayın.

## <a name="syntax"></a>Sözdizimi

```cpp
_se_translator_function _set_se_translator(
    _se_translator_function seTransFunction
);
```

### <a name="parameters"></a>Parametreler

*seTransFunction*<br/>
Yazdığınız C yapılandırılmış özel durum Çeviricisi işlevine yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Önceki işlevin daha sonra geri yüklenebilmesi için **_set_se_translator**tarafından kaydedilen önceki çevirmen işlevine yönelik bir işaretçi döndürür. Önceki bir işlev ayarlanmamışsa, varsayılan davranışı geri yüklemek için dönüş değeri kullanılabilir; Bu değer **nullptr**olabilir.

## <a name="remarks"></a>Açıklamalar

**_Set_se_translator** işlevi, tür özel durumlar olarak C++ Win32 özel durumlarını (C yapılandırılmış özel durumlar) işlemek için bir yol sağlar. Her bir c özel durumunun bir C++ **catch** işleyicisi tarafından işlenmesine izin vermek için, önce bir c özel durum sarmalayıcı sınıfı tanımlayın veya belirli bir sınıf türüne bir c özel durumuna öznitelik, Bu sınıfı kullanmak için, bir C özel durumu başlatıldığında iç özel durum işleme mekanizması tarafından çağrılan özel bir C özel durum Çeviricisi işlevi yüklersiniz. Çeviri işleviniz içinde, eşleşen C++ bir **catch** işleyicisi tarafından yakalanabileceği herhangi bir tür özel durum oluşturabilirsiniz.

**_Set_se_translator**kullanırken [/EHa](../../build/reference/eh-exception-handling-model.md) kullanmanız gerekir.

Özel bir çeviri işlevi belirtmek için, çeviri işlevinizin adını bağımsız değişken olarak kullanarak **_set_se_translator** çağırın. Yazdığınız Translator işlevi, **TRY** blokları olan yığında her bir işlev çağrısı için bir kez çağrılır. Varsayılan çevirmen işlevi yok.

Translator işleviniz, türü belirlenmiş bir C++ özel durum oluşturmamalıdır. Oluşturma (örneğin, bir günlük dosyasına yazma gibi) varsa, program beklendiği gibi davranmayabilir, çünkü Translator işlevinin çağrıldığı sayı, platforma bağımlıdır.

Çok iş parçacıklı bir ortamda, çevirmen işlevleri her iş parçacığı için ayrı olarak korunur. Her yeni iş parçacığının kendi Translator işlevini yüklemesi gerekir. Bu nedenle, her iş parçacığı kendi çeviri işlemeye göre ücretlendirilir. **_set_se_translator** , bir iş parçacığına özeldir; başka bir DLL, farklı bir çeviri işlevi yükleyebilir.

Yazdığınız *seTransFunction* işlevinin yerel olarak derlenen bir işlev olması gerekir (/clr ile derlenmemelidir). Bağımsız değişken olarak bir Win32 **_Exception_işaretçiler** yapısına bir işaretsiz tamsayı ve işaretçi almalıdır. Bağımsız değişkenler, sırasıyla Win32 API **GetExceptionCode** ve **GetExceptionInformation** işlevlerine yapılan çağrıların dönüş değerleridir.

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

**_Set_se_translator**IÇIN, CRT 'ye dinamik olarak bağlanan bazı etkiler; işlemdeki başka bir DLL, **_set_se_translator** çağırabilir ve işleyicinizi kendi kendine değiştirebilir.

Yönetilen koddan (/clr ile derlenen kod) veya karma yerel ve yönetilen kodla **_set_se_translator** kullanırken, çeviricisinin yalnızca yerel kodda oluşturulan özel durumları etkilediğini unutmayın. Yönetilen kodda oluşturulan yönetilen özel durumlar (örneğin, oluşturma sırasında `System::Exception`), çevirmen işlevi aracılığıyla yönlendirilmez. Yönetilen kodda oluşturulan, **RaiseException** Win32 işlevi kullanılarak oluşturulan özel durumlar veya bir sistem özel durumu, sıfıra bölme özel durumuyla başarısız oldu, çevirmen aracılığıyla yönlendirilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_se_translator**|\<Eh. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu örnek, yapılandırılmış bir özel durum Çeviricisi ayarlamak ve bir RAMPADAKI eski bir sınıfı `Scoped_SE_Translator`geri yüklemek için çağrıları sarmalar. Bu sınıf, kapsama özgü çeviriciyi tek bir bildirim olarak tanıtmanıza imkan tanır. Sınıf yıkıcısı, denetim kapsamdan ayrıldığında orijinal çeviriciyi geri yükler.

```cpp
// crt_settrans.cpp
// compile with: cl /W4 /EHa crt_settrans.cpp
#include <stdio.h>
#include <windows.h>
#include <eh.h>
#include <exception>

class SE_Exception : public std::exception
{
private:
    const unsigned int nSE;
public:
    SE_Exception() noexcept : SE_Exception{ 0 } {}
    SE_Exception( unsigned int n ) noexcept : nSE{ n } {}
    unsigned int getSeNumber() const noexcept { return nSE; }
};

class Scoped_SE_Translator
{
private:
    const _se_translator_function old_SE_translator;
public:
    Scoped_SE_Translator( _se_translator_function new_SE_translator ) noexcept
        : old_SE_translator{ _set_se_translator( new_SE_translator ) } {}
    ~Scoped_SE_Translator() noexcept { _set_se_translator( old_SE_translator ); }
};

void SEFunc()
{
    __try
    {
        printf( "In __try, about to force exception\n" );
        int x = 5;
        int y = 0;
        int *p = &y;
        *p = x / *p;
    }
    __finally
    {
        printf( "In __finally\n" );
    }
}

void trans_func( unsigned int u, EXCEPTION_POINTERS* )
{
    throw SE_Exception( u );
}

int main()
{
    Scoped_SE_Translator scoped_se_translator{ trans_func };
    try
    {
        SEFunc();
    }
    catch( const SE_Exception& e )
    {
        printf( "Caught a __try exception, error %8.8x.\n", e.getSeNumber() );
    }
}
```

```Output
In __try, about to force exception
In __finally
Caught a __try exception, error c0000094.
```

## <a name="example"></a>Örnek

**_Set_se_translator** tarafından sağlanan işlevsellik yönetilen kodda kullanılamaz olsa da, yerel kod, **/clr** anahtarı altındaki bir derlemede olsa bile bu eşlemeyi yerel kodda kullanmak mümkündür. kullanılarak `#pragma unmanaged`belirtilir. Eşlenen yönetilen kodda yapılandırılmış bir özel durum oluşturulursa, özel durumu oluşturan ve işleyen kodun işaretlenmesi `#pragma unmanaged`gerekir. Aşağıdaki kodda olası bir kullanım gösterilmektedir. Daha fazla bilgi için bkz. [pragma yönergeleri ve __Pragma Anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <stdio.h>
#include <exception>

int thrower_func( int i ) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class SE_Exception : public std::exception
{
private:
    const unsigned int nSE;
public:
    SE_Exception() noexcept : SE_Exception{ 0 } {}
    SE_Exception( unsigned int n ) noexcept : nSE{ n } {}
    unsigned int getSeNumber() const noexcept { return nSE; }
};

class Scoped_SE_Translator
{
private:
    const _se_translator_function old_SE_translator;
public:
    Scoped_SE_Translator( _se_translator_function new_SE_translator ) noexcept
        : old_SE_translator{ _set_se_translator( new_SE_translator ) } {}
    ~Scoped_SE_Translator() noexcept { _set_se_translator( old_SE_translator ); }
};

#pragma unmanaged
void my_trans_func( unsigned int u, PEXCEPTION_POINTERS )
{
    throw SE_Exception( u );
}

void DoTest()
{
    try
    {
        thrower_func( 10 );
    }
    catch( const SE_Exception& e )
    {
        printf( "Caught SE_Exception, error %8.8x\n", e.getSeNumber() );
    }
    catch(...)
    {
        printf( "Caught unexpected SEH exception.\n" );
    }
}
#pragma managed

int main() {
    Scoped_SE_Translator scoped_se_translator{ my_trans_func };

    DoTest();
}
```

```Output
Caught SE_Exception, error c0000094
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[sonlandırmayı](terminate-crt.md)<br/>
[bek](unexpected-crt.md)<br/>
