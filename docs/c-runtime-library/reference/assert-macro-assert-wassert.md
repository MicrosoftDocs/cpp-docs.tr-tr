---
title: onaylama makrosu, _Onay, _TatLı
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
ms.openlocfilehash: a2cc780fbc93aa66bd7fd613c3e155cda27eb7f9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500332"
---
# <a name="assert-macro-_assert-_wassert"></a>onaylama makrosu, _Onay, _TatLı

Bir ifadeyi değerlendirir ve sonuç **yanlış**olduğunda bir tanılama iletisi yazdırır ve programı iptal eder.

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

*ifadesini*<br/>
Sıfır (**true**) veya 0 (**false**) olarak değerlendirilen skaler bir ifade (işaretçi ifadeleri dahil).

*message*<br/>
Görüntülenecek ileti.

*kısaltın*<br/>
Onaylama işlemi başarısız kaynak dosyanın adı.

*satırı*<br/>
Başarısız onaylama kaynak dosyasındaki satır numarası.

## <a name="remarks"></a>Açıklamalar

**Onaylama** makrosu genellikle program geliştirme sırasında mantık hatalarını belirlemek için kullanılır. Yalnızca program yanlış çalıştığında **yanlış** olarak değerlendirmek için *ifade* bağımsız değişkenini uygulayarak beklenmeyen durumlar meydana geldiğinde program yürütmesini durdurmak için bunu kullanın. Onaylama denetimleri, **ndebug**makrosunu tanımlayarak derleme zamanında kapatılabilir. Bir **/Dndebug** komut satırı seçeneğini kullanarak kaynak dosyalarınızı değiştirmeden **onaylama** makrosunu kapatabilirsiniz. Onay. h > dahil etmeden önce `#define NDEBUG` \<bir yönerge kullanarak kaynak kodunuzda onay makrosunu devre dışı bırakabilirsiniz.

**Onaylama** makrosu, *ifade* **yanlış** (0) olarak değerlendirildiğinde ve program yürütmeyi sonlandırmak için [iptal](abort.md) 'i çağırdığında bir tanılama iletisi yazdırır. *İfade* **true** ise (sıfır dışında) hiçbir eylem yapılmaz. Tanılama iletisi başarısız ifadeyi, kaynak dosyanın adını ve onaylama işlemi başarısız olan satır numarasını içerir.

Tanılama iletisi geniş karakterlerle yazdırılır. Bu nedenle, ifadede Unicode karakterler olsa bile beklendiği gibi çalışacaktır.

Tanı iletisinin hedefi, yordamı çağıran uygulamanın türüne bağlıdır. Konsol uygulamaları her zaman **stderr**aracılığıyla iletiyi alır. Windows tabanlı bir uygulamada, **onaylama** , Iletiyi bir **Tamam** düğmesiyle birlikte göstermek üzere bir Ileti kutusu oluşturmak için Windows [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) işlevini çağırır. Kullanıcı **Tamam**' a tıkladığında program hemen iptal edilir.

Uygulama, çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, onay üç düğme içeren bir ileti kutusu oluşturur: **Durdur**, **yeniden dene**ve **Yoksay**. Kullanıcı **Durdur**' a tıkladığında program hemen iptal edilir. Kullanıcı **yeniden dene**' ye tıkladığında, hata ayıklayıcı çağrılır ve tam ZAMANıNDA (JIT) hata ayıklama etkinse Kullanıcı programda hata ayıklayabilirler. Kullanıcı **Yoksay**' ı tıklarsa, **onaylama** normal yürütmeye devam eder: **Tamam** düğmesi ile ileti kutusunu oluşturma. Bir hata koşulu varken **Yoksay** ' a tıklamak tanımsız davranışa neden olabilir.

CRT hata ayıklama hakkında daha fazla bilgi için bkz. [CRT hata ayıklama teknikleri](/visualstudio/debugger/crt-debugging-techniques).

**_Onaylama** ve **_TatLı** işlevleri iç CRT işlevlerdir. Bunlar, onayları desteklemek için nesne dosyalarınızda gereken kodu en aza indirmenize yardımcı olur. Bu işlevleri doğrudan çağırmanız önerilmez.

Onay makrosu, **ndebug** tanımlanmadığında C çalışma zamanı kitaplıklarının hem yayın hem de hata ayıklama sürümlerinde etkinleştirilir. **Ndebug** tanımlandığında, makro kullanılabilir ancak bağımsız değişkenini değerlendirmez ve herhangi bir etkiye sahip değildir. Etkin olduğunda, **onaylama** makrosu kendi uygulamasına göre **_ıtlı** çağırır. Diğer onaylama makroları, [_Onaylama](assert-asserte-assert-expr-macros.md), [_Asserte](assert-asserte-assert-expr-macros.md) ve [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md)de mevcuttur, ancak yalnızca [_DEBUG](../../c-runtime-library/debug.md) makrosu tanımlandığında ve hata ayıklama ile bağlantılı kodlarlarsa bunlara geçirilen ifadeleri değerlendirir C çalışma zamanı kitaplıklarının sürümü.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**onaylama**, **_TatLı**|\<onaylama. h >|

**_Onaylama** işlevinin imzası bir üstbilgi dosyasında kullanılamaz. **_İlesert** işlevinin Imzası yalnızca **ndebug** makrosu tanımlanmadığı zaman kullanılabilir.

## <a name="example"></a>Örnek

Bu programda, **analyze_string** işlevi dize ve uzunlukla ilgili çeşitli koşulları test etmek için onay makrosunu kullanır. Koşullardan herhangi biri başarısız olursa, program hatanın nedenini belirten bir ileti yazdırır.

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

[Hata İşleme](../../c-runtime-library/error-handling-crt.md)<br/>
[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[raise](raise.md)<br/>
[signal](signal.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR Makroları](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
