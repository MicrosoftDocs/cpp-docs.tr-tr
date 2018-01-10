---
title: Assert makrosu, _assert, _wassert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- assert
- _assert
- _wassert
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- assert
- _assert
- _wassert
- assert/_wassert
dev_langs: C++
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5a0fe8083cfc131f7e8b1f2133943a1c91f614a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="assert-macro-assert-wassert"></a>Assert makrosu, _assert, _wassert
İfade bir ve sonucu olduğunda değerlendirir `false`, bir tanılama iletisi yazdırır ve programı durdurur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
assert(   
   expression   
);  
void _assert(  
   char const* message,  
   char const* filename,  
   unsigned line  
);  
void _wassert(  
   wchar_t const* message,  
   wchar_t const* filename,  
   unsigned line  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `expression`  
 İçin sıfır olmayan değerlendiren (işaretçi ifadeleri dahil) bir skaler ifade (`true`) veya 0 (`false`).  
  
 `message`  
 Görüntülenecek ileti.  
  
 `filename`  
 Onaylama işlemi başarısız oldu kaynak dosyanın adı.  
  
 `line`  
 Başarısız onaylama kaynak dosyasında satır numarası.  
  
## <a name="remarks"></a>Açıklamalar  
 `assert` Makrosu genellikle program geliştirme sırasında mantık hataları belirlemek için kullanılır. Program yürütme uygulayarak beklenmeyen durumlar ortaya çıktığında durdurmak için kullanın `expression` için değerlendirmek için bağımsız değişken `false` yalnızca zaman program yanlış çalışıyor. Onaylama işlemi denetimleri açılabilir derleme zamanında makrosu tanımlayarak `NDEBUG`. Devre dışı bırakabilirsiniz `assert` kullanarak kaynak dosyalarınız değiştirmeden makrosu bir **/DNDEBUG** komut satırı seçeneği. Devre dışı bırakabilirsiniz `assert` makrosu kullanarak kaynak kodunuzda bir `#define NDEBUG` önce yönerge \<assert.h > bulunur.  
  
 `assert` Bir tanılama iletisi makrosu baskı siparişi `expression` değerlendiren `false` (0) ve çağrıları [abort](../../c-runtime-library/reference/abort.md) program yürütme sonlandırılacak. Hiçbir işlem yapılmadı `expression` olan `true` (sıfır). Tanılama ileti başarısız ifadesi, onaylama işlemi başarısız olduğu kaynak dosyası ve satır numarası adını içerir.  
  
 Tanılama iletisi geniş karakter yazdırılır. Dolayısıyla, ifade Unicode karakterler olsa beklendiği gibi çalışmaz.  
  
 Tanılama iletiyi hedef sıradan adlı uygulama türüne göre değişir. Konsol uygulamaları her zaman üzerinden ileti alma `stderr`. Windows tabanlı bir uygulama içinde `assert` Windows çağırır [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) iletiyle boyunca görüntülenecek bir ileti kutusu oluşturmak için işlevi bir **Tamam** düğmesi. Kullanıcı tıkladığında **Tamam**, program hemen durdurur.  
  
 Uygulama çalışma zamanı kitaplıkları ile bir hata ayıklama sürümü bağlandığında `assert` üç düğmeleriyle bir ileti kutusu oluşturur: **Abort**, **yeniden deneme**, ve **Yoksay**. Kullanıcı tıklarsa **Abort**, program hemen durdurur. Kullanıcı tıklarsa **yeniden**, hata ayıklayıcı olarak adlandırılır ve tam zamanında (JIT) hata ayıklama etkinleştirilirse kullanıcı programı ayıklayabilirsiniz. Kullanıcı tıklarsa **Yoksay**, `assert` normal yürütülmesinin ile devam eder: ileti kutusu oluşturma **Tamam** düğmesi. Bu tıklatarak Not **Yoksay** ne zaman bir hata koşulu var. tanımsız davranışlara neden olabilir.  
  
 CRT hata ayıklama hakkında daha fazla bilgi için bkz: [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).  
  
 `_assert` Ve `_wassert` işlevlerdir iç CRT işlevleri. Nesne dosyalarınızda onaylar desteklemek için gereken kodu en aza indirmenize yardımcı olurlar. Bu işlevler doğrudan çağırmanız önermiyoruz.  
  
 `assert` Makrosu her iki sürüm ve hata ayıklama sürümlerinde C çalışma zamanı kitaplıkları etkin olduğunda `NDEBUG` tanımlı değil. Zaman `NDEBUG` olan tanımlanan makrosu kullanılabilir ancak bağımsız değişken değerlendirmez ve herhangi bir etkisi olmaz. Etkinleştirildiğinde, `assert` makrosu çağrıları `_wassert` uygulaması için. Diğer onaylama makroları [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) ve [_ASSERT_EXPR](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), de kullanılabilir, ancak bunlar yalnızca bunları ne zaman geçirilen ifadeleri değerlendirme [_DEBUG](../../c-runtime-library/debug.md) makrosu tanımlanmış ve C çalışma zamanı kitaplıkları hata ayıklama sürümü ile bağlantılı kodda olduklarında.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`assert`, `_wassert`|\<Assert.h >|  
  
 İmzası `_assert` işlevi kullanılamaz bir üstbilgi dosyası. İmzası `_wassert` işlevi yalnızca kullanılabilir olduğunda `NDEBUG` makrosu tanımlı değil.  
  
## <a name="example"></a>Örnek  
 Bu programı `analyze_string` işlev kullandığı `assert` makrosu birkaç koşullarda test etmek için ilgili dize ve uzunluğu. Koşullardan herhangi biri başarısız olursa, başarısızlığın nedenini belirten bir ileti program yazdırır.  
  
```  
// crt_assert.c  
// compile by using: cl /W4 crt_assert.c  
#include <stdio.h>  
#include <assert.h>  
#include <string.h>  
  
void analyze_string( char *string );   // Prototype  
  
int main( void )  
{  
   char  test1[] = "abc", *test2 = NULL, test3[] = "";  
  
   printf ( "Analyzing string '%s'\n", test1 ); fflush( stdout );  
   analyze_string( test1 );  
   printf ( "Analyzing string '%s'\n", test2 ); fflush( stdout );  
   analyze_string( test2 );  
   printf ( "Analyzing string '%s'\n", test3 ); fflush( stdout );  
   analyze_string( test3 );  
}  
  
// Tests a string to see if it is NULL,   
// empty, or longer than 0 characters.  
void analyze_string( char * string )  
{  
   assert( string != NULL );        // Cannot be NULL  
   assert( *string != '\0' );       // Cannot be empty  
   assert( strlen( string ) > 2 );  // Length must exceed 2  
}  
```  
  
 Program, bu bir çıktı üretir:  
  
```Output  
Analyzing string 'abc'  
Analyzing string '(null)'  
Assertion failed: string != NULL, file crt_assert.c, line 25  
```  
  
 Çalışma zamanı kitaplığı ve işletim sistemi sürümüne bağlı olarak onaylama hatası sonra aşağıdakine benzer içeren bir ileti kutusu görebilirsiniz:  
  
```Output  
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.  
```  
  
 Bir hata ayıklayıcısı yüklediyseniz seçin **hata ayıklama** hata ayıklayıcı başlatmak için düğmesini veya **Programı Kapat** çıkmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata işleme](../../c-runtime-library/error-handling-crt.md)   
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [Yükselt](../../c-runtime-library/reference/raise.md)   
 [Sinyal](../../c-runtime-library/reference/signal.md)   
 [_ASSERT, _ASSERTE, _ASSERT_EXPR makroları](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)   
 [_DEBUG](../../c-runtime-library/debug.md)