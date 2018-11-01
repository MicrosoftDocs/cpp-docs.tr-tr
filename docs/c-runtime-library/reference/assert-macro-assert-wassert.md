---
title: Assert makrosu, _assert, _wassert
ms.date: 11/04/2016
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
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
ms.openlocfilehash: 7ac299213ba3de878f7cf2dc99b44c45273bc3b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590963"
---
# <a name="assert-macro-assert-wassert"></a>Assert makrosu, _assert, _wassert

Bir ifade ve sonucu olduğunda değerlendirir **false**, bir tanılama iletisi yazdırır ve programı durdurur.

## <a name="syntax"></a>Sözdizimi

```C
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

### <a name="parameters"></a>Parametreler

*İfade*<br/>
İçin sıfır dışında değerlendirilen (işaretçi ifadeleri dahil) bir skaler ifade (**true**) veya 0 (**false**).

*message*<br/>
Görüntülenecek ileti.

*Dosya adı*<br/>
Kaynak dosyanın adı, onaylama işlemi başarısız oldu.

*Satır*<br/>
Onaylama başarısız kaynak dosyadaki satır numarası.

## <a name="remarks"></a>Açıklamalar

**Assert** makrosu genellikle program geliştirme sırasında mantık hataları tanımlamak için kullanılır. Beklenmeyen durumlar uygulayarak ortaya çıktığında, program yürütme durdurmak için kullanmak *ifade* bağımsız değişkeni için değerlendirilecek **false** yalnızca zaman programı hatalı biçimde çalışıyor. Onaylama işlemi denetimleri kapatılabilir derleme zamanında makro tanımlayarak **NDEBUG**. Devre dışı bırakabilirsiniz **assert** kaynak dosyalarını kullanarak değiştirmeden makro bir **/DNDEBUG** komut satırı seçeneği. Devre dışı bırakabilirsiniz **assert** makrosu kullanarak, kaynak kodunuzda bir `#define NDEBUG` önce yönerge \<assert.h > dahildir.

**Assert** bir tanılama iletisi makrosu yazdırır *ifade* değerlendiren **false** (0) ve çağrıları [iptal](abort.md) Programı sonlandırmak için yürütme. Hiçbir işlem yapılmadı, *ifade* olduğu **true** (sıfır dışında). Tanılama iletisi başarısız ifadesi, onaylama işlemi başarısız olduğu kaynak dosya ve satır numarası adını içerir.

Tanılama iletisi geniş karakter yazdırılır. Bu nedenle, ifade Unicode karakterler olsa beklendiği gibi çalışır.

Tanılama iletisi hedefinin yordamı çağıran uygulama türüne bağlıdır. Konsol uygulamaları her zaman aracılığıyla iletisini alırsınız **stderr**. Windows tabanlı bir uygulama içinde **assert** Windows çağırır [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) beraber iletiyi görüntülemek için bir ileti kutusu oluşturmak için işlevi bir **Tamam** düğmesi. Kullanıcı tıkladığında **Tamam**, program hemen durdurur.

Uygulama çalışma zamanı kitaplıklarının hata ayıklama sürümü ile ilişkilendirildiğinde **assert** üç düğme bir ileti kutusu oluşturur: **iptal**, **yeniden**ve **Yoksay**. Kullanıcı tıklarsa **iptal**, program hemen durdurur. Kullanıcı tıklarsa **yeniden**, hata ayıklayıcı adı verilir ve tam zamanında (JIT) hata ayıklama etkinleştirilirse kullanıcı programı hata ayıklaması yapabilirsiniz. Kullanıcı tıklarsa **Yoksay**, **assert** normal yürütülmeye devam eder: ileti kutusuyla oluşturma **Tamam** düğmesi. Sonuçlandığını unutmayın **Yoksay** bir hata koşulu olduğunda mevcut tanımsız davranışlara neden olabilir.

CRT hata ayıklama hakkında daha fazla bilgi için bkz. [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

**_Assert** ve **_wassert** iç CRT işlevleri işlevlerdir. Bunlar, nesne dosyalarında onaylar desteklemek için gerekli kodu en aza yardımcı olur. Bu işlevler doğrudan çağrı önermiyoruz.

**Assert** makrosu her iki sürüm ve hata ayıklama sürümleri C çalışma zamanı kitaplıklarının etkin olduğunda **NDEBUG** tanımlı değil. Zaman **NDEBUG** olan tanımlanan, makro kullanılabilir ancak bağımsız değerlendirmez ve hiçbir etkisi olmaz. Etkinleştirildiğinde, **assert** makrosu çağrıları **_wassert** uygulanması için. Diğer onaylama makroları [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md) ve [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md), ayrıca kullanılabilir ancak bunlar yalnızca bunları ne zaman geçirilen ifadeleri değerlendirme [_DEBUG](../../c-runtime-library/debug.md) makro tanımlandıktan ve kodda hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlı olduklarında.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Assert**, **_wassert**|\<Assert.h >|

İmzası **_assert** işlevi kullanılabilir değil bir üstbilgi dosyasında. İmzası **_wassert** işlevi, yalnızca kullanılabilir olduğunda **NDEBUG** Makro tanımlı değil.

## <a name="example"></a>Örnek

Bu programa **analyze_string** işlevini kullanan **assert** çeşitli koşulları test etmeye yönelik makro dize uzunluğu ile ilgili. Program, koşullardan herhangi biri başarısız olursa hatanın nedenini belirten bir ileti yazdırır.

```C
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

Program şu çıktıyı üretir:

```Output
Analyzing string 'abc'
Analyzing string '(null)'
Assertion failed: string != NULL, file crt_assert.c, line 25
```

Çalışma zamanı kitaplığı ve işletim sistemi sürümüne bağlı olarak bir onaylama işlemi hatası sonra aşağıdaki gibi içeren bir ileti kutusu görebilirsiniz:

```Output
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.
```

Bir hata ayıklayıcısı yüklüyse seçin **hata ayıklama** hata ayıklayıcıyı başlatmak için düğmeye veya **Programı Kapat** çıkmak için.

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[raise](raise.md)<br/>
[signal](signal.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR Makroları](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
