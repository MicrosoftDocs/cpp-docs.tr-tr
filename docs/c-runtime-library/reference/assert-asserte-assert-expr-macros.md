---
title: _ASSERT, _ASSERTE _ASSERT_EXPR makrolar
ms.date: 11/04/2016
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ASSERTE
- ASSERTE
- _ASSERT_EXPR
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
ms.openlocfilehash: 26a1439e4de8824edd11af1afd455d2b2c31c088
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443081"
---
# <a name="_assert-_asserte-_assert_expr-macros"></a>_ASSERT, _ASSERTE _ASSERT_EXPR makrolar

Bir ifadeyi değerlendirin ve sonuç **false** olduğunda bir hata ayıklama raporu oluşturun (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
// Typical usage:
_ASSERT_EXPR( booleanExpression, message );
_ASSERT( booleanExpression );
_ASSERTE( booleanExpression );
```

### <a name="parameters"></a>Parametreler

*Boolean*<br/>
Sıfır (true) veya 0 (false) olarak değerlendirilen skaler bir ifade (işaretçi ifadeleri dahil).

*message*<br/>
Raporun parçası olarak görüntülenecek geniş bir dize.

## <a name="remarks"></a>Açıklamalar

**_ASSERT_EXPR**, **_assert** ve **_ASSERTE** makroları, hata ayıklama işlemi sırasında varsayımları denetlemek için temiz ve basit bir mekanizmaya sahip bir uygulama sağlar. Bunlar, bir uygulamanın perakende derlemesinde çağrılmalarını engellemek için `#ifdef` deyimlerine alınmaları gerektiğinden çok esnektir. Bu esneklik [_DEBUG](../../c-runtime-library/debug.md) makro kullanılarak elde edilir. **_ASSERT_EXPR**, **_assert** ve **_ASSERTE** yalnızca derleme zamanında **_DEBUG** tanımlandığında kullanılabilir. **_DEBUG** tanımlanmadığında, bu makrolara yapılan çağrılar ön işleme sırasında kaldırılır.

**_ASSERT_EXPR**, **_assert** ve **_ASSERTE** *Boolean* bağımsız değişkenini değerlendirin ve sonuç **yanlış** (0) olduğunda bir hata ayıklama raporu oluşturmak için bir tanılama iletisi yazdırır ve [_CrtDbgReportW](crtdbgreport-crtdbgreportw.md) çağırır. **_Assert** makrosu basit bir tanılama iletisi yazdırır, **_ASSERTE** iletide başarısız olan ifadenin bir dize gösterimini içerir ve **_ASSERT_EXPR** , tanılama iletisinde *ileti* dizesini içerir. Bu makrolar, *Boolean* sıfır olarak değerlendirildiğinde hiçbir şey yapmaz.

**_ASSERT_EXPR**, **_ASSERT** ve **_ASSERTE** **_CrtDbgReportW**çağırın, bu da tüm çıktının geniş karakterlerle olmasına neden olur. **_ASSERTE** , *Boolean* 'ta Unicode karakterlerini doğru bir şekilde yazdırır ve **_ASSERT_EXPR** Unicode karakterleri *iletiye*yazdırır.

**_ASSERTE** makro başarısız ifadeyi belirttiğinden ve **_ASSERT_EXPR** oluşturulan raporda bir ileti belirtmenizi sağladığından, kullanıcıların sorunu uygulama kaynak koduna girmeden belirlemesine olanak sağlar. Ancak, **_ASSERT_EXPR** tarafından yazdırılan her bir *iletinin* ve **_ASSERTE** tarafından değerlendirilen her ifadenin, bir dize sabiti olarak uygulamanızın çıkış (hata ayıklama sürümü) dosyasına dahil olduğu bir dezavantajı vardır. Bu nedenle, **_ASSERT_EXPR** veya **_ASSERTE**için çok sayıda çağrı yapılırsa, bu ifadeler çıkış dosyanızın boyutunu büyük ölçüde artırabilir.

[_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevleriyle aksi belirtilmedikçe iletiler, ayarlamaya eşdeğer bir açılan iletişim kutusunda görünür:

```C
_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);
````

**_CrtDbgReportW** , hata ayıklama raporunu oluşturur ve geçerli rapor modu ya da **_CRT_ASSERT** rapor türü için tanımlanan modları ve dosyaları temel alarak hedefini veya hedeflerini belirler. Varsayılan olarak, onaylama hataları ve hataları bir hata ayıklama iletisi penceresine yönlendirilir. [_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevleri, her rapor türü için hedefleri tanımlamak üzere kullanılır.

Hedef bir hata ayıklama iletisi penceresi olduğunda ve Kullanıcı **yeniden dene** düğmesine tıkladığında, **_CrtDbgReportW** 1 değerini döndürür, **_ASSERT_EXPR**, **_assert** ve **_ASSERTE** makroları, Just-In-Time (JIT) hata ayıklamanın etkin olduğu belirtilen hata ayıklayıcıyı başlatmaya neden olur.

Raporlama işlemi hakkında daha fazla bilgi için [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) işlevine bakın. Onaylama hatalarının çözümlenmesi ve bu makroların hata ayıklama hatası işleme mekanizması olarak kullanılması hakkında daha fazla bilgi için bkz. [doğrulama ve raporlama Için makroları kullanma](/visualstudio/debugger/macros-for-reporting).

**_Assert** makrolarına ek olarak, [onay makrosu program](assert-macro-assert-wassert.md) mantığını doğrulamak için de kullanılabilir. Bu makro, kitaplıkların hata ayıklama ve yayın sürümlerinde bulunur. [_Rpt, _rptf](rpt-rptf-rptw-rptfw-macros.md) hata ayıklama makroları bir hata ayıklama raporu oluşturmak için de kullanılabilir, ancak bir ifadeyi değerlendirmez. **_RPT** makroları basit bir rapor oluşturur. **_RPTF** makrolar, rapor makrosunun oluşturulan raporda çağrıldığı kaynak dosya ve satır numarasını içerir. Bu makroların geniş karakter sürümleri mevcuttur ( **_rptw**, **_rptfw**). Geniş karakter sürümleri, tüm dize parametreleri ve çıktısı için kullanılan geniş karakter dizeleri hariç dar karakter sürümleriyle aynıdır.

**_ASSERT_EXPR**, **_assert** ve **_ASSERTE** makrolar olsa da \<Crtdbg. h > dahil edildiğinde, bu makrolar diğer çalışma zamanı işlevlerini çağırdığından, uygulamanın, **_DEBUG** tanımlandığında C çalışma zamanı kitaplığının hata ayıklama sürümüyle bağlanması gerekir.

## <a name="requirements"></a>Gereksinimler

|Makrosu|Gerekli başlık|
|-----------|---------------------|
|**_ASSERT_EXPR**, **_assert**, **_ASSERTE**|\<Crtdbg. h >|

## <a name="example"></a>Örnek

Bu programda, koşul `string1 == string2`test etmek için **_assert** ve **_ASSERTE** makrolarında çağrılar yapılır. Durum başarısız olursa, bu makrolar bir tanılama iletisi yazdırır. Makroların **_RPT** ve **_RPTF** grubu, **printf** işlevine alternatif olarak bu programda de çalışır.

```C
// crt_ASSERT_macro.c
// compile with: /D_DEBUG /MTd /Od /Zi /link /verbose:lib /debug
//
// This program uses the _ASSERT and _ASSERTE debugging macros.
//

#include <stdio.h>
#include <string.h>
#include <malloc.h>
#include <crtdbg.h>

int main()
{
   char *p1, *p2;

   // The Reporting Mode and File must be specified
   // before generating a debug report via an assert
   // or report macro.
   // This program sends all report types to STDOUT.
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ASSERT, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ASSERT, _CRTDBG_FILE_STDOUT);

   // Allocate and assign the pointer variables.
   p1 = (char *)malloc(10);
   strcpy_s(p1, 10, "I am p1");
   p2 = (char *)malloc(10);
   strcpy_s(p2, 10, "I am p2");

   // Use the report macros as a debugging
   // warning mechanism, similar to printf.
   // Use the assert macros to check if the
   // p1 and p2 variables are equivalent.
   // If the expression fails, _ASSERTE will
   // include a string representation of the
   // failed expression in the report.
   // _ASSERT does not include the
   // expression in the generated report.
   _RPT0(_CRT_WARN,
       "Use the assert macros to evaluate the expression p1 == p2.\n");
   _RPTF2(_CRT_WARN, "\n Will _ASSERT find '%s' == '%s' ?\n", p1, p2);
   _ASSERT(p1 == p2);

   _RPTF2(_CRT_WARN, "\n\n Will _ASSERTE find '%s' == '%s' ?\n",
          p1, p2);
   _ASSERTE(p1 == p2);

   _RPT2(_CRT_ERROR, "'%s' != '%s'\n", p1, p2);

   free(p2);
   free(p1);

   return 0;
}
```

```Output
Use the assert macros to evaluate the expression p1 == p2.
crt_ASSERT_macro.c(54) :
Will _ASSERT find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(55) : Assertion failed!
crt_ASSERT_macro.c(58) :

Will _ASSERTE find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(59) : Assertion failed: p1 == p2
'I am p1' != 'I am p2'
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[assert Makrosu, _assert, _wassert](assert-macro-assert-wassert.md)<br/>
[_RPT, _RPTF, _RPTW, _RPTFW Makroları](rpt-rptf-rptw-rptfw-macros.md)<br/>
