---
title: _set_se_translator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_se_translator
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
dev_langs: C++
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 82e9a4d904f28f528dbc9ed6871d9cd350d36014
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setsetranslator"></a>_set_se_translator
Tanıtıcıları Win32 özel durumlar (C yapılandırılmış özel durum) olarak C++ özel durum belirtilmiş.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_se_translator_function _set_se_translator(  
   _se_translator_function seTransFunction  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `seTransFunction`  
 Bir C işaretçisine yazdığınız özel durum Çeviricisi işlevi yapılandırılmış.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Önceki Çeviricisi işlevi için bir işaretçi kayıtlı tarafından döndürür `_set_se_translator`, böylece önceki işlevi daha sonra geri yüklenebilir. Önceki bir işlev ayarlarsanız dönüş değerini varsayılan davranışını geri yüklemek için kullanılabilir; Bu değer NULL olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 `_set_se_translator` İşlevi Win32 özel durumlar (C yapılandırılmış özel durum) C++ işlemek için bir yol sağlar yazılan özel durumları. C++ tarafından yönetilecek her C özel durumuna izin `catch` işleyici, ilk kullanılan veya bir C özel öznitelik belirli bir sınıf türü için türetilmiş bir C özel durumu sarmalayıcı sınıfı tanımlar. Bu sınıf kullanmak için iç özel durum işleme mekanizması bir C özel durumu her zaman adlı özel bir C özel durumu Çeviricisi işlev yükleyin. Çevirici işlevinizi içinde eşleşen bir C++ tarafından yakalanan yazılan özel durumları throw `catch` işleyicisi.  
  
 Kullanmalısınız [/EHa](../../build/reference/eh-exception-handling-model.md) kullanırken `_set_se_translator`.  
  
 Özel çeviri işlevi belirtmek için arama `_set_se_translator` çeviri işlevinizi bağımsız değişkeni olarak adı. Her işlev çağrısını sahip yığında için yazdığınız Çeviricisi işlevi bir kez çağrılır `try` engeller. Hiçbir varsayılan çeviricisi işlevi yoktur.  
  
 Çevirici işlevi C++ throw daha fazla yapmalısınız belirtilmiş özel durum. (Bir günlük dosyasına örneğin yazmak gibi) atma yanı sıra herhangi bir şey varsa Çeviricisi işlev çağrıldığında sayısı platforma bağımlı olduğu için program beklendiği gibi davranabilir değil.  
  
 Birden çok iş parçacıklı bir ortamda Çeviricisi işlevleri her iş parçacığı için ayrı ayrı tutulur. Her yeni bir iş parçacığı kendi Çeviricisi işlevi yüklemeniz gerekir. Bu nedenle, her iş parçacığının kendi çeviri işleme sorumlu olduğu. `_set_se_translator`bir iş parçacığına özgü; başka bir DLL farklı çeviri işlev yükleyebilir.  
  
 `seTransFunction` Yazdığınız işlevi (/ CLR ile derlenmemiş) yerel koda derlenmiş bir işlev olmalıdır. Bunu bir işaretsiz tamsayı ve bir işaretçi bir Win32 almalıdır `_EXCEPTION_POINTERS` bağımsız değişken olarak yapısı. Win32 API çağrıları dönüş değerleri değişkenleridir `GetExceptionCode` ve `GetExceptionInformation` işlevleri, sırasıyla.  
  
```  
typedef void (*_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );  
```  
  
 İçin `_set_se_translator`, dinamik olarak CRT bağlarken etkileri olan; başka bir işlem DLL'de çağırabilirsiniz `_set_se_translator` ve işleyicinizi kendi ile değiştirin.  
  
 Kullanırken `_set_se_translator` yönetilen koddan (/ CLR ile derlenmiş kod) veya yerel ve yönetilen kod karma, Çevirici yalnızca yerel kodda oluşturulan özel durumları etkilediğine dikkat edin. Yönetilen kodda oluşturulan özel durumları tarafından yönetilen (ne zaman gibi yükseltme `System::Exception`) Çeviricisi işlevi yönlendirilmedi. Win32 işlevi kullanılarak yönetilen koddan oluşturulan özel durumları `RaiseException` veya sıfır özel durum sıfıra yönlendirilir gibi Çeviricisi bir sistem özel durumu nedeniyle.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_set_se_translator`|\<EH.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_settrans.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <windows.h>  
#include <eh.h>  
  
void SEFunc();  
void trans_func( unsigned int, EXCEPTION_POINTERS* );  
  
class SE_Exception  
{  
private:  
    unsigned int nSE;  
public:  
    SE_Exception() {}  
    SE_Exception( unsigned int n ) : nSE( n ) {}  
    ~SE_Exception() {}  
    unsigned int getSeNumber() { return nSE; }  
};  
int main( void )  
{  
    try  
    {  
        _set_se_translator( trans_func );  
        SEFunc();  
    }  
    catch( SE_Exception e )  
    {  
        printf( "Caught a __try exception with SE_Exception.\n" );  
    }  
}  
void SEFunc()  
{  
    __try  
    {  
        int x, y=0;  
        x = 5 / y;  
    }  
    __finally  
    {  
        printf( "In finally\n" );  
    }  
}  
void trans_func( unsigned int u, EXCEPTION_POINTERS* pExp )  
{  
    printf( "In trans_func.\n" );  
    throw SE_Exception();  
}  
```  
  
```Output  
In trans_func.  
In finally  
Caught a __try exception with SE_Exception.  
```  
  
## <a name="example"></a>Örnek  
 Tarafından sağlanan işlevselliği rağmen `_set_se_translator` olan yönetilen kodda kullanılamıyor, onu yerel kodu derleme altında olsa bile bu yerel kodda eşleme kullanmak da mümkündür `/clr` yerel kod kullanarakbelirtilensürece,geçiş`#pragma unmanaged`. İle yapılandırılmış bir özel durum eşlenecek yönetilen kodda durum gerekiyorsa oluşturur ve özel durumu işler kodu işaretlenmelidir `pragma`. Aşağıdaki kod, olası bir kullanımını gösterir. Daha fazla bilgi için bkz: [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).  
  
```  
// crt_set_se_translator_clr.cpp  
// compile with: /clr  
#include <windows.h>  
#include <eh.h>  
#include <assert.h>  
#include <stdio.h>  
  
int thrower_func(int i) {  
   int j = i/0;  
  return 0;  
}  
  
class CMyException{  
};  
  
#pragma unmanaged  
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS pExp )  
{  
printf("Translating the structured exception to a C++"  
             " exception.\n");  
throw CMyException();  
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
  
int main(int argc, char** argv) {  
    _set_se_translator(my_trans_func);  
    DoTest();  
    return 0;  
}  
```  
  
```Output  
Translating the structured exception to a C++ exception.  
Caught CMyException.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme rutinleri](../../c-runtime-library/exception-handling-routines.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [sonlandırma](../../c-runtime-library/reference/terminate-crt.md)   
 [beklenmeyen](../../c-runtime-library/reference/unexpected-crt.md)