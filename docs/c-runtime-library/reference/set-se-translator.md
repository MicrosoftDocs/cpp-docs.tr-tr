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
ms.openlocfilehash: 18ee500d7b884d1934c29dc91d9bcb03d507680d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356556"
---
# <a name="setsetranslator"></a>_set_se_translator

Win32 özel durumları (C yapısal özel durumlarını) C++ çevirmek için bir iş parçacığı başına geri çağırma işlevini yazılan özel durumları ayarlayın.

## <a name="syntax"></a>Sözdizimi

```cpp
_se_translator_function _set_se_translator(
    _se_translator_function seTransFunction
);
```

### <a name="parameters"></a>Parametreler

*seTransFunction*<br/>
Bir C işaretçisine yazdığınız özel durum Çevirici işlevi yapılandırılmış.

## <a name="return-value"></a>Dönüş Değeri

Önceki translator işlevi işaretçisi kayıtlı tarafından döndürür **_set_se_translator**, böylece önceki işlevi daha sonra geri yüklenebilir. Önceki bir işlev ayarlarsanız dönüş değeri, varsayılan davranışı geri yüklemek için kullanılabilir; Bu değer **nullptr**.

## <a name="remarks"></a>Açıklamalar

**_Set_se_translator** işlevi olarak Win32 özel durumlar (C yapısal özel durumlarını) işlemek için bir yol sağlar C++ belirlenmiş özel durumlar. Bir C++ tarafından işlenmek üzere her C özel durumuna izin **catch** işleyicisi önce kullanılan veya bir C özel durumu için belirli bir sınıf türü nitelemek için türetilmiş bir C özel durum sarmalayıcı sınıfı tanımlayın. Bu sınıf kullanmak için iç özel durum işleme mekanizmasını C özel durum harekete geçirilen her zaman çağrılan özel bir C özel durum Çevirici işlevi yükleyin. Translator işlevinizi içinde eşleşen bir C++ tarafından yakalanabilir yazılan tüm özel durum oluşturabilecek **catch** işleyici.

Kullanmalısınız [/eha](../../build/reference/eh-exception-handling-model.md) kullanırken **_set_se_translator**.

Özel çeviri işlevi belirtmek için çağrı **_set_se_translator** çeviri işlevinizin adını, bağımsız değişkeni olarak kullanma. Her yığında olan işlev çağrısını için yazdığınız translator işlevi bir kez çağrılır **deneyin** engeller. Hiçbir varsayılan translator işlevi yoktur.

Bir C++ throw daha fazla translator işlevinizi yapmalısınız yazılan özel durum. (Bir günlük dosyasına, örneğin yazma gibi) özel durum atma yanı sıra herhangi bir şey varsa kaç kez translator işlevin çağrıldığı platforma bağımlı olduğundan, program beklendiği gibi çalışmayabilir.

Çok iş parçacıklı bir ortamda Çevirici işlevleri her bir iş parçacığı için ayrı olarak korunur. Her yeni bir iş parçacığı kendi translator işlevi yüklemeniz gerekir. Bu nedenle, her iş parçacığının kendi çeviri işleme sorumlu olduğu. **_set_se_translator** bir iş parçacığına özgü farklı çeviri işlevi başka bir DLL yükleyebilirsiniz.

*SeTransFunction* yazdığınız işlevi (/ CLR ile derlenmiş değil) yerel olarak derlenmiş bir işlev olmalıdır. Bunu bir işaretsiz tamsayı ve bir işaretçi için bir Win32 almalıdır **_exceptıon_poınters** bağımsız değişkenler olarak yapısı. Win32 API çağrılarının dönüş değerlerini bağımsız değişkenler **GetExceptionCode** ve **Getexceptionınformation** işlevleri, sırasıyla.

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

İçin **_set_se_translator**, dinamik olarak CRT'ye bağlarken etkileri olan; başka bir DLL işleminde çağırabilirsiniz **_set_se_translator** işleyicinizi kendi ile değiştirin.

Kullanırken **_set_se_translator** yönetilen koddan (/ CLR ile derlenmiş kod) veya yerel ve yönetilen kod karma, translator yalnızca yerel kod içinde oluşturulan özel durumları etkilediğini unutmayın. Herhangi bir yönetilen yönetilen kodda oluşturulan özel durumları (ne zaman gibi yükseltme `System::Exception`) Çevirici işleviyle yönlendirilmedi. Win32 işlevini kullanarak yönetilen kod içinde oluşturulan özel durumları **RaiseException** veya sıfır özel durum ile bir bölme yönlendirilir gibi translator bir sistem özel durumu nedeniyle.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_se_translator**|\<EH.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

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
    unsigned int nSE;
public:
    SE_Exception() : nSE{ 0 } {}
    SE_Exception( unsigned int n ) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
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

void trans_func(unsigned int u, EXCEPTION_POINTERS*)
{
    throw SE_Exception(u);
}

int main()
{
    auto original = _set_se_translator(trans_func);
    try
    {
        SEFunc();
    }
    catch(SE_Exception& e)
    {
        printf("Caught a __try exception, error %8.8x.\n", e.getSeNumber());
    }
    _set_se_translator(original);
}
```

```Output
In __try, about to force exception
In __finally
Caught a __try exception, error c0000094.
```

## <a name="example"></a>Örnek

İşlevler tarafından sağlanan rağmen **_set_se_translator** olan yönetilen kodda kullanılabilir değil, bir derlemede altında o yerel kod olsa bile bu yerel kodda eşleme kullanmak mümkündür **/CLR** Yerel kod kullanarak belirtilen sürece geçiş `#pragma unmanaged`. Eşlenecek yönetilen kodda durum yapılandırılmış bir özel durum oluşturulursa, oluşturur ve özel durumu işleyen kodu işaretlenmelidir `#pragma unmanaged`. Aşağıdaki kod, olası bir kullanımını gösterir. Daha fazla bilgi için [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <assert.h>
#include <stdio.h>
#include <exception>

int thrower_func(int i) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class SE_Exception : public std::exception {
private:
    unsigned int nSE;
public:
    SE_Exception() : nSE{ 0 } {}
    SE_Exception(unsigned int n) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

#pragma unmanaged
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS)
{
    throw SE_Exception(u);
}

void DoTest()
{
    try
    {
        thrower_func(10);
    }
    catch(SE_Exception& e)
    {
        printf("Caught SE_Exception, error %8.8x\n", e.getSeNumber());
    }
    catch(...)
    {
        printf("Caught unexpected SEH exception.\n");
    }
}
#pragma managed

int main() {
    auto original = _set_se_translator(my_trans_func);
    DoTest();
    _set_se_translator(original);
}
```

```Output
Caught SE_Exception, error c0000094
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[sonlandırma](terminate-crt.md)<br/>
[beklenmeyen](unexpected-crt.md)<br/>
