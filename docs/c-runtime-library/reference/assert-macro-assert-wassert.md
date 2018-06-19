---
title: Assert makrosu, _assert, _wassert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0318abde877e9b647c1781408d2e22cc9d70824e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397847"
---
# <a name="assert-macro-assert-wassert"></a>Assert makrosu, _assert, _wassert

İfade bir ve sonucu olduğunda değerlendirir **yanlış**, bir tanılama iletisi yazdırır ve programı durdurur.

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

*ifade* için sıfır olmayan değerlendiren (işaretçi ifadeleri dahil) bir skaler ifade (**true**) veya 0 (**false**).

*İleti* görüntülenecek ileti.

*filename* kaynağının adını dosya onaylama işlemi başarısız oldu.

*Satır* başarısız onaylama kaynak dosyasında satır sayısı.

## <a name="remarks"></a>Açıklamalar

**Assert** makrosu genellikle program geliştirme sırasında mantık hataları belirlemek için kullanılır. Beklenmeyen koşullar uygulayarak ortaya çıktığında program yürütme durdurmak için kullanın *ifade* için değerlendirmek için bağımsız değişken **false** yalnızca zaman program yanlış çalışıyor. Onaylama işlemi denetimleri açılabilir derleme zamanında makrosu tanımlayarak **NDEBUG**. Devre dışı bırakabilirsiniz **assert** kullanarak kaynak dosyalarınız değiştirmeden makrosu bir **/DNDEBUG** komut satırı seçeneği. Devre dışı bırakabilirsiniz **assert** makrosu kullanarak kaynak kodunuzda bir `#define NDEBUG` önce yönerge \<assert.h > bulunur.

**Assert** bir tanılama iletisi makrosu baskı siparişi *ifade* değerlendiren **false** (0) ve çağrıları [abort](abort.md) Programı sonlandırmak için yürütme. Hiçbir işlem yapılmadı *ifade* olan **true** (sıfır). Tanılama ileti başarısız ifadesi, onaylama işlemi başarısız olduğu kaynak dosyası ve satır numarası adını içerir.

Tanılama iletisi geniş karakter yazdırılır. Dolayısıyla, ifade Unicode karakterler olsa beklendiği gibi çalışmaz.

Tanılama iletiyi hedef sıradan adlı uygulama türüne göre değişir. Konsol uygulamaları her zaman üzerinden ileti alma **stderr**. Windows tabanlı bir uygulama içinde **assert** Windows çağırır [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) iletiyle boyunca görüntülenecek bir ileti kutusu oluşturmak için işlevi bir **Tamam** düğmesi. Kullanıcı tıkladığında **Tamam**, program hemen durdurur.

Uygulama çalışma zamanı kitaplıkları ile bir hata ayıklama sürümü bağlandığında **assert** üç düğmeleriyle bir ileti kutusu oluşturur: **Abort**, **yeniden deneme**ve **Yoksay**. Kullanıcı tıklarsa **Abort**, program hemen durdurur. Kullanıcı tıklarsa **yeniden**, hata ayıklayıcı olarak adlandırılır ve tam zamanında (JIT) hata ayıklama etkinleştirilirse kullanıcı programı ayıklayabilirsiniz. Kullanıcı tıklarsa **Yoksay**, **assert** normal yürütülmesinin ile devam eder: ileti kutusu oluşturma **Tamam** düğmesi. Bu tıklatarak Not **Yoksay** ne zaman bir hata koşulu var. tanımsız davranışlara neden olabilir.

CRT hata ayıklama hakkında daha fazla bilgi için bkz: [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

**_Assert** ve **_wassert** işlevlerdir iç CRT işlevleri. Nesne dosyalarınızda onaylar desteklemek için gereken kodu en aza indirmenize yardımcı olurlar. Bu işlevler doğrudan çağırmanız önermiyoruz.

**Assert** makrosu her iki sürüm ve hata ayıklama sürümlerinde C çalışma zamanı kitaplıkları etkin olduğunda **NDEBUG** tanımlı değil. Zaman **NDEBUG** olan tanımlanan makrosu kullanılabilir ancak bağımsız değişken değerlendirmez ve herhangi bir etkisi olmaz. Etkinleştirildiğinde, **assert** makrosu çağrıları **_wassert** uygulaması için. Diğer onaylama makroları [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md) ve [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md), de kullanılabilir, ancak bunlar yalnızca bunları ne zaman geçirilen ifadeleri değerlendirme [_DEBUG](../../c-runtime-library/debug.md) makrosu tanımlanmış ve C çalışma zamanı kitaplıkları hata ayıklama sürümü ile bağlantılı kodda olduklarında.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Assert**, **_wassert**|\<Assert.h >|

İmzası **_assert** işlevi kullanılamaz bir üstbilgi dosyası. İmzası **_wassert** işlevi yalnızca kullanılabilir olduğunda **NDEBUG** makrosu tanımlı değil.

## <a name="example"></a>Örnek

Bu programı **analyze_string** işlev kullandığı **assert** makrosu birkaç koşullarda test etmek için ilgili dize ve uzunluğu. Koşullardan herhangi biri başarısız olursa, başarısızlığın nedenini belirten bir ileti program yazdırır.

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

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[raise](raise.md)<br/>
[signal](signal.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR Makroları](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
