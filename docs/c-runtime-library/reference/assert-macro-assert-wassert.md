---
title: onaylama makrosu, _assert _wassert
description: Onaylama makroları ve C çalışma zamanı işlevlerinin etkileri.
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
ms.openlocfilehash: 071424f2201ceda43438fe1056801811fe444a01
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609077"
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

*line*<br/>
Başarısız onaylama kaynak dosyasındaki satır numarası.

## <a name="remarks"></a>Açıklamalar

`assert`Makro genellikle program geliştirme sırasında mantık hatalarını belirlemek için kullanılır. Yalnızca program yanlış çalıştığında değerlendirmek için *ifade* bağımsız değişkenini uygulayarak beklenmeyen durumlar meydana geldiğinde program yürütmesini durdurmak için bunu kullanın **`false`** . Onaylama denetimleri, **ndebug**makrosunu tanımlayarak derleme zamanında kapatılabilir. `assert`Bir **/Dndebug** komut satırı seçeneğini kullanarak kaynak dosyalarınızı değiştirmeden makroyu kapatabilirsiniz. `assert`Dahil etmeden önce bir yönergesi kullanarak kaynak kodunuzda makroyu kapatabilirsiniz `#define NDEBUG` \<assert.h> .

`assert`Bir *ifade* **`false`** (0) olarak değerlendirilirse ve [`abort`](abort.md) program yürütmeyi durdurmak için çağrılar olduğunda makro bir tanılama iletisi yazdırır. *İfade* **`true`** (sıfır dışında) ise hiçbir işlem yapılmaz. Tanılama iletisi başarısız ifadeyi, kaynak dosyanın adını ve onaylama işlemi başarısız olan satır numarasını içerir.

Tanılama iletisi geniş ( `wchar_t` ) karakterlerle yazdırılır. Bu nedenle, ifadede Unicode karakterler olsa bile beklendiği gibi çalışacaktır.

Tanı iletisinin hedefi, yordamı çağıran uygulamanın türüne bağlıdır. Konsol uygulamaları, iletiyi **stderr**aracılığıyla alır. Windows tabanlı bir uygulamada, `assert` iletiyi üç düğme ile göstermek üzere bir ileti kutusu oluşturmak Için Windows [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) Işlevini çağırır: **Abort**, **retry**ve **Ignore**. Kullanıcı **Durdur**' a tıkladığında program hemen iptal edilir. Kullanıcı **yeniden dene**' ye tıkladığında, hata ayıklayıcı çağrılır ve tam ZAMANıNDA (JIT) hata ayıklama etkinse Kullanıcı programda hata ayıklayabilirler. Kullanıcı **Yoksay**' ı tıklarsa, program normal yürütmeye devam eder. Hata koşulu varken **Yoksay** ' a tıklamak, çağıran kodun önkoşulları karşılanmadığından tanımsız davranışa neden olabilir.

Uygulama türünden bağımsız olarak varsayılan çıkış davranışını geçersiz kılmak için, çıkış- [`_set_error_mode`](set-error-mode.md) ---------------iletişim kutusu davranışı arasında seçim yapın.

İletisi görüntülendikten sonra, `assert` Bu, [`abort`](abort.md)  **iptal**, **yeniden dene**ve **yoksayma** düğmeleriyle bir iletişim kutusu görüntüleyen çağırır. [`abort`](abort.md) Programdan çıkar, bu nedenle **yeniden dene** ve **Yoksay** düğmesi çağrıdan sonra program yürütmeyi sürdürmez `assert` . `assert`İletişim kutusu görüntülenirse [`abort`](abort.md) iletişim kutusu gösterilmez. [`abort`](abort.md)İletişim kutusu her gösterildiği zaman, `assert` çıktısını stderr 'e gönderir.

Yukarıdaki davranışın bir sonucu olarak, hata ayıklama modundaki bir çağrının sonrasında bir iletişim kutusu görüntülenir `assert` . Her düğmenin davranışı aşağıdaki tabloda yakalanır.

|Hata modu|Stderr 'e çıkış (konsol/_OUT_TO_STDERR)|Görüntüleme Iletişim kutusu (Windows/_OUT_TO_MSGBOX)|
|----------|----------------|------------------|
|Durdurma|Çıkış kodu 3 ile hemen çık|Çıkış kodu 3 ile hemen çık|
|Yeniden Dene|Sırasında hata ayıklayıcıya Böl `abort`|Sırasında hata ayıklayıcıya Böl `assert`|
|Yoksayma|İle çıkış bitiş `abort`|Onaylama işlemi tetiklenmese de programa devam et (çağıran kodun önkoşulları karşılanmadığından tanımsız davranışlara neden olabilir)|

CRT hata ayıklama hakkında daha fazla bilgi için bkz. [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

`_assert`Ve `_wassert` işlevleri, iç CRT işlevlerdir. Bunlar, onayları desteklemek için nesne dosyalarınızda gereken kodu en aza indirmenize yardımcı olur. Bu işlevleri doğrudan çağırmanız önerilmez.

`assert`Makro, **ndebug** tanımlanmadığında C çalışma zamanı kitaplıklarının hem yayın hem de hata ayıklama sürümlerinde etkinleştirilir. **Ndebug** tanımlandığında, makro kullanılabilir ancak bağımsız değişkenini değerlendirmez ve herhangi bir etkiye sahip değildir. Etkinleştirildiğinde `assert` makro, `_wassert` uygulamasını çağırır. Diğer onaylama makroları, [_assert](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md) ve [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md)da kullanılabilir, ancak yalnızca [_DEBUG](../../c-runtime-library/debug.md) makrosu tanımlandığında ve C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı kodlarda olduklarında, bunlara geçirilen ifadeleri değerlendirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`assert`, `_wassert`|\<assert.h>|

`_assert`İşlevin imzası bir üstbilgi dosyasında kullanılamaz. `_wassert`İşlevin imzası yalnızca **ndebug** makrosu tanımlı olmadığında kullanılabilir.

## <a name="example"></a>Örnek

Bu programda **analyze_string** işlevi, `assert` dize ve uzunlukla ilgili çeşitli koşulları test etmek için makroyu kullanır. Koşullardan herhangi biri başarısız olursa, program hatanın nedenini belirten bir ileti yazdırır.

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

Onaylama hatasından sonra, işletim sistemi ve çalışma zamanı kitaplığının sürümüne bağlı olarak şuna benzer bir ileti kutusu görebilirsiniz:

```Output
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.
```

Bir hata ayıklayıcı yüklüyse, hata ayıklayıcıyı başlatmak için **Hata Ayıkla** düğmesini seçin veya çıkmak Için **programı kapatın** .

## <a name="see-also"></a>Ayrıca bkz.

[Hata Işleme](../../c-runtime-library/error-handling-crt.md)<br/>
[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[durdurulmaya](abort.md)<br/>
[yükseltmek](raise.md)<br/>
[sinyal](signal.md)<br/>
[_ASSERT, _ASSERTE _ASSERT_EXPR makrolar](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
