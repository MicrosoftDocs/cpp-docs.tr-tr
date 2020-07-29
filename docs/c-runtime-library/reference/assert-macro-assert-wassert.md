---
title: onaylama makrosu, _assert _wassert
ms.date: 11/04/2016
api_name:
- assert
- _assert
- _wassert
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 173974cfd9d3f9b3fc054bb71ad70b757f8ef819
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232631"
---
# <a name="assert-macro-_assert-_wassert"></a>onaylama makrosu, _assert _wassert

Bir ifadeyi değerlendirir ve sonuç olduğunda **`false`** bir tanılama iletisi yazdırır ve programı iptal eder.

## <a name="syntax"></a>Söz dizimi

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

*ifadesini*<br/>
Sıfır () **`true`** veya 0 () olarak değerlendirilen skaler bir ifade (işaretçi ifadeleri dahil) **`false`** .

*İleti*<br/>
Görüntülenecek ileti.

*filename*<br/>
Onaylama işlemi başarısız kaynak dosyanın adı.

*satırı*<br/>
Başarısız onaylama kaynak dosyasındaki satır numarası.

## <a name="remarks"></a>Açıklamalar

**Onaylama** makrosu genellikle program geliştirme sırasında mantık hatalarını belirlemek için kullanılır. Yalnızca program yanlış çalıştığında değerlendirmek için *ifade* bağımsız değişkenini uygulayarak beklenmeyen durumlar meydana geldiğinde program yürütmesini durdurmak için bunu kullanın **`false`** . Onaylama denetimleri, **ndebug**makrosunu tanımlayarak derleme zamanında kapatılabilir. Bir **/Dndebug** komut satırı seçeneğini kullanarak kaynak dosyalarınızı değiştirmeden **onaylama** makrosunu kapatabilirsiniz. Dahil etmeden önce bir yönergesi kullanarak kaynak kodunuzda **onaylama** makrosunu kapatabilirsiniz `#define NDEBUG` \<assert.h> .

**Onaylama** makrosu, *ifade* (0) değerini değerlendirirken bir tanılama iletisi yazdırır **`false`** ve program yürütmeyi sonlandırmak için [iptali](abort.md) çağırır. *İfade* **`true`** (sıfır dışında) ise hiçbir işlem yapılmaz. Tanılama iletisi başarısız ifadeyi, kaynak dosyanın adını ve onaylama işlemi başarısız olan satır numarasını içerir.

Tanılama iletisi geniş karakterlerle yazdırılır. Bu nedenle, ifadede Unicode karakterler olsa bile beklendiği gibi çalışacaktır.

Tanı iletisinin hedefi, yordamı çağıran uygulamanın türüne bağlıdır. Konsol uygulamaları her zaman **stderr**aracılığıyla iletiyi alır. Windows tabanlı bir uygulamada, **onaylama** , Iletiyi bir **Tamam** düğmesiyle birlikte göstermek üzere bir Ileti kutusu oluşturmak için Windows [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) işlevini çağırır. Kullanıcı **Tamam**' a tıkladığında program hemen iptal edilir.

Uygulama, çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, onay üç düğme içeren bir **ileti kutusu oluşturur:** **Abort**, **retry**ve **Ignore**. Kullanıcı **Durdur**' a tıkladığında program hemen iptal edilir. Kullanıcı **yeniden dene**' ye tıkladığında, hata ayıklayıcı çağrılır ve tam ZAMANıNDA (JIT) hata ayıklama etkinse Kullanıcı programda hata ayıklayabilirler. Kullanıcı **Yoksay**' ı tıklarsa, **onaylama** normal yürütmeye devam eder: **Tamam** düğmesi ile ileti kutusunu oluşturma. Bir hata koşulu varken **Yoksay** ' a tıklamak tanımsız davranışa neden olabilir.

CRT hata ayıklama hakkında daha fazla bilgi için bkz. [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

**_Assert** ve **_WASSERT** işlevleri iç CRT işlevlerdir. Bunlar, onayları desteklemek için nesne dosyalarınızda gereken kodu en aza indirmenize yardımcı olur. Bu işlevleri doğrudan çağırmanız önerilmez.

Onay **makrosu,** **ndebug** tanımlanmadığında C çalışma zamanı kitaplıklarının hem yayın hem de hata ayıklama sürümlerinde etkinleştirilir. **Ndebug** tanımlandığında, makro kullanılabilir ancak bağımsız değişkenini değerlendirmez ve herhangi bir etkiye sahip değildir. Etkinleştirildiğinde, **onaylama** makrosu uygulamasının uygulamasına **_wassert** çağırır. Diğer onaylama makroları, [_assert](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md) ve [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md)da kullanılabilir, ancak yalnızca [_DEBUG](../../c-runtime-library/debug.md) makrosu tanımlandığında ve C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı kodlarda olduklarında, bunlara geçirilen ifadeleri değerlendirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**onaylama**, **_wassert**|\<assert.h>|

**_Assert** işlevinin imzası bir üstbilgi dosyasında kullanılamaz. **_Wassert** işlevinin Imzası yalnızca **ndebug** makrosu tanımlanmadığı zaman kullanılabilir.

## <a name="example"></a>Örnek

Bu programda **analyze_string** işlevi, dize ve uzunlukla ilgili çeşitli koşulları test etmek için **onaylama** makrosunu kullanır. Koşullardan herhangi biri başarısız olursa, program hatanın nedenini belirten bir ileti yazdırır.

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

Program bu çıktıyı oluşturur:

```Output
Analyzing string 'abc'
Analyzing string '(null)'
Assertion failed: string != NULL, file crt_assert.c, line 25
```

Onaylama hatasından sonra, işletim sisteminin ve çalışma zamanı kitaplığının sürümüne bağlı olarak, aşağıdakine benzer bir ileti kutusu görebilirsiniz:

```Output
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.
```

Bir hata ayıklayıcı yüklüyse, hata ayıklayıcıyı başlatmak için **Hata Ayıkla** düğmesini seçin veya çıkmak Için **programı kapatın** .

## <a name="see-also"></a>Ayrıca bkz.

[Hata Işleme](../../c-runtime-library/error-handling-crt.md)<br/>
[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[durdur](abort.md)<br/>
[tetikle](raise.md)<br/>
[sinyal](signal.md)<br/>
[_ASSERT, _ASSERTE _ASSERT_EXPR makrolar](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
