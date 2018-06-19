---
title: _set_se_translator | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d4a5c9e86023ea47f23b648cad1a4dffedf905b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411526"
---
# <a name="setsetranslator"></a>_set_se_translator

Ayarlanmış bir iş parçacığı başına geri çağırma işlevi C++ uygulamasına Win32 özel durumlar (C yapılandırılmış özel durum) çevirmek için yazılan özel durumları.

## <a name="syntax"></a>Sözdizimi

```cpp
_se_translator_function _set_se_translator(
    _se_translator_function seTransFunction
);
```

### <a name="parameters"></a>Parametreler

*seTransFunction*<br/>
Bir C işaretçisine yazdığınız özel durum Çeviricisi işlevi yapılandırılmış.

## <a name="return-value"></a>Dönüş Değeri

Önceki Çeviricisi işlevi için bir işaretçi kayıtlı tarafından döndürür **_set_se_translator**, böylece önceki işlevi daha sonra geri yüklenebilir. Önceki bir işlev ayarlarsanız dönüş değerini varsayılan davranışını geri yüklemek için kullanılabilir; Bu değer **nullptr**.

## <a name="remarks"></a>Açıklamalar

**_Set_se_translator** işlevi Win32 özel durumlar (C yapılandırılmış özel durum) C++ işlemek için bir yol sağlar yazılan özel durumları. C++ tarafından yönetilecek her C özel durumuna izin **catch** işleyici, ilk kullanılan veya bir C özel öznitelik belirli bir sınıf türü için türetilmiş bir C özel durumu sarmalayıcı sınıfı tanımlar. Bu sınıf kullanmak için iç özel durum işleme mekanizması bir C özel durumu her zaman adlı özel bir C özel durumu Çeviricisi işlev yükleyin. Çevirici işlevinizi içinde eşleşen bir C++ tarafından yakalanan yazılan özel durumları throw **catch** işleyicisi.

Kullanmalısınız [/EHa](../../build/reference/eh-exception-handling-model.md) kullanırken **_set_se_translator**.

Özel çeviri işlevi belirtmek için arama **_set_se_translator** çeviri işlevinizin adını bağımsız değişken olarak kullanarak. Her işlev çağrısını sahip yığında için yazdığınız Çeviricisi işlevi bir kez çağrılır **deneyin** engeller. Hiçbir varsayılan çeviricisi işlevi yoktur.

Çevirici işlevi C++ throw daha fazla yapmalısınız belirtilmiş özel durum. (Bir günlük dosyasına örneğin yazmak gibi) atma yanı sıra herhangi bir şey varsa Çeviricisi işlev çağrıldığında sayısı platforma bağımlı olduğu için program beklendiği gibi davranabilir değil.

Birden çok iş parçacıklı bir ortamda Çeviricisi işlevleri her iş parçacığı için ayrı ayrı tutulur. Her yeni bir iş parçacığı kendi Çeviricisi işlevi yüklemeniz gerekir. Bu nedenle, her iş parçacığının kendi çeviri işleme sorumlu olduğu. **_set_se_translator** tek bir iş parçacığı için; özgü başka bir DLL farklı çeviri işlev yükleyebilir.

*SeTransFunction* yazdığınız işlevi (/ CLR ile derlenmemiş) yerel koda derlenmiş bir işlev olmalıdır. Bunu bir işaretsiz tamsayı ve bir işaretçi bir Win32 almalıdır **_exceptıon_poınters** bağımsız değişken olarak yapısı. Win32 API çağrıları dönüş değerleri değişkenleridir **GetExceptionCode** ve **GetExceptionInformation** işlevleri, sırasıyla.

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

İçin **_set_se_translator**, dinamik olarak CRT bağlarken etkileri olan; başka bir işlem DLL'de çağırabilirsiniz **_set_se_translator** ve işleyicinizi kendi ile değiştirin.

Kullanırken **_set_se_translator** yönetilen koddan (/ CLR ile derlenmiş kod) veya yerel ve yönetilen kod karma, Çevirici yalnızca yerel kodda oluşturulan özel durumları etkilediğine dikkat edin. Yönetilen kodda oluşturulan özel durumları tarafından yönetilen (ne zaman gibi yükseltme `System::Exception`) Çeviricisi işlevi yönlendirilmedi. Win32 işlevi kullanılarak yönetilen koddan oluşturulan özel durumları **RaiseException** veya sıfır özel durum sıfıra yönlendirilir gibi Çeviricisi bir sistem özel durumu nedeniyle.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_se_translator**|\<EH.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```cpp
// crt_settrans.cpp
// compile with: cl /W4 /EHa crt_settrans.cpp
#include <stdio.h>
#include <windows.h>
#include <eh.h>

class SE_Exception
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

Tarafından sağlanan işlevselliği rağmen **_set_se_translator** olan yönetilen kodda kullanılamıyor, bu yerel kodu derleme altında olsa bile bu yerel kodda eşleme kullanmak mümkündür **/CLR** Yerel kod kullanarak belirtilen sürece geçiş `#pragma unmanaged`. Yapılandırılmış özel durum eşlenecek yönetilen kodda durum gerekiyorsa oluşturur ve özel durumu işler kodu işaretlenmelidir `#pragma unmanaged`. Aşağıdaki kod, olası bir kullanımını gösterir. Daha fazla bilgi için bkz: [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <assert.h>
#include <stdio.h>

int thrower_func(int i) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class CMyException{
private:
    unsigned int nSE;
public:
    CMyException() : nSE{ 0 } {}
    CMyException(unsigned int n) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

#pragma unmanaged
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS)
{
    throw CMyException(u);
}

void DoTest()
{
    try
    {
        thrower_func(10);
    }
    catch(CMyException e)
    {
        printf("Caught CMyException.\n");
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
Caught CMyException, error c0000094
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[Sonlandırma](terminate-crt.md)<br/>
[beklenmeyen](unexpected-crt.md)<br/>
