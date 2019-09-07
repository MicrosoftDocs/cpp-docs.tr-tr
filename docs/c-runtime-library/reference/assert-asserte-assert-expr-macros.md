---
title: _ONAYLAMA, _ASSERTE, _ASSERT_EXPR makroları
ms.date: 11/04/2016
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
- _ASSERTE
- ASSERTE
- _ASSERT
- _ASSERT_EXPR
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
ms.openlocfilehash: d2d83c3afa8e22c1f75480fe2afefa8bf68be858
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740020"
---
# <a name="_assert-_asserte-_assert_expr-macros"></a>_ONAYLAMA, _ASSERTE, _ASSERT_EXPR makroları

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

**_ASSERT_EXPR**, **_Onaylama** ve **_ASSERTE** makroları, hata ayıklama işlemi sırasında varsayımları denetlemek için temiz ve basit bir mekanizmaya sahip bir uygulama sağlar. Bu uygulamalar, bir uygulamanın perakende derlemesinde çağrılmasına engel olmak için `#ifdef` deyimlerini kapsamaları gerektiğinden çok esnektir. Bu esneklik, [_Debug](../../c-runtime-library/debug.md) makrosu kullanılarak elde edilir. **_ASSERT_EXPR**, **_Onaylama** ve **_Asserte** yalnızca derleme zamanında **_DEBUG** tanımlandığında kullanılabilir. **_Hata ayıklama** tanımlanmadığında, bu makrolara yapılan çağrılar ön işleme sırasında kaldırılır.

**_ASSERT_EXPR**, **_Onaylama** ve **_ASSERTE** , *Boolean* bağımsız değişkenini değerlendirir ve sonuç **yanlış** (0) olduğunda bir tanılama Iletisi yazdırır ve hata ayıklama raporu oluşturmak için [_CrtDbgReportW](crtdbgreport-crtdbgreportw.md) öğesini çağırır. **_Onaylama** makrosu basit bir tanılama iletisi yazdırır, **_ASSERTE** ileti içinde başarısız olan ifadenin dize gösterimini içerir ve **_ASSERT_EXPR** , tanılama iletisindeki *ileti* dizesini içerir. Bu makrolar, *Boolean* sıfır olarak değerlendirildiğinde hiçbir şey yapmaz.

**_ASSERT_EXPR**, **_Onaylama** ve **_Asserte** Invoke **_CrtDbgReportW**, bu, tüm çıktının geniş karakterlerle olmasına neden olur. **_Asserte** , *Boolean* 'ta Unicode karakterlerini doğru bir şekilde yazdırır ve **_ASSERT_EXPR** Unicode karakterleri *iletiye*yazdırır.

**_Asserte** makrosu başarısız ifadeyi belirttiğinden ve **_ASSERT_EXPR** oluşturulan raporda bir ileti belirtmenizi sağladığından, kullanıcıların sorunu uygulama kaynak koduna bildirmeden belirlemesine olanak sağlar. Ancak, **_ASSERT_EXPR** tarafından yazdırılan her *iletinin* bir dezavantajı ve **_ASSERTE** tarafından değerlendirilen her bir ifade, uygulamanızın çıkış (hata ayıklama sürümü) dosyasına bir dize sabiti olarak dahildir. Bu nedenle, **_ASSERT_EXPR** veya **_ASSERTE**için çok sayıda çağrı yapılırsa, bu ifadeler çıkış dosyanızın boyutunu büyük ölçüde artırabilir.

Aksini, [_Crtsetreportmode](crtsetreportmode.md) ve [_Crtsetreportfile](crtsetreportfile.md) işlevleriyle belirtmediğiniz müddetçe, iletiler ayarlamaya eşdeğer bir açılan iletişim kutusunda görüntülenir:

```C
_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);
````

**_Crtdbgreportw** hata ayıklama raporunu oluşturur ve geçerli rapor modu ya da **_CRT_ASSERT** rapor türü için tanımlanan modları ve dosya temelinde hedef veya hedeflerini belirler. Varsayılan olarak, onaylama hataları ve hataları bir hata ayıklama iletisi penceresine yönlendirilir. [_Crtsetreportmode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevleri, her rapor türü için hedefleri tanımlamak üzere kullanılır.

Hedef bir hata ayıklama iletisi penceresince ve Kullanıcı **yeniden dene** düğmesine tıkladığında, **_Crtdbgreportw** 1 değerini döndürür, **_ASSERT_EXPR**, **_onaylama** ve **_ASSERTE** makrolarının hata ayıklayıcıyı başlatması tam zamanında (JıT) hata ayıklama etkindir.

Raporlama işlemi hakkında daha fazla bilgi için bkz. [_Crtdbgreport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) işlevi. Onaylama hatalarının çözümlenmesi ve bu makroların hata ayıklama hatası işleme mekanizması olarak kullanılması hakkında daha fazla bilgi için bkz. [doğrulama ve raporlama Için makroları kullanma](/visualstudio/debugger/macros-for-reporting).

**_Onaylama** makrolarına ek olarak, [onay makrosu program](assert-macro-assert-wassert.md) mantığını doğrulamak için de kullanılabilir. Bu makro, kitaplıkların hata ayıklama ve yayın sürümlerinde bulunur. [_Rpt, _RPTF](rpt-rptf-rptw-rptfw-macros.md) hata ayıklama makroları bir hata ayıklama raporu oluşturmak için de kullanılabilir, ancak bir ifadeyi değerlendirmez. **_Rpt** makroları basit bir rapor oluşturur. **_Rptf** makroları, rapor makrosunun oluşturulan raporda çağrıldığı kaynak dosyayı ve satır numarasını içerir. Bu makroların geniş karakter sürümleri mevcuttur ( **_Rptw**, **_rptfw**). Geniş karakter sürümleri, tüm dize parametreleri ve çıktısı için kullanılan geniş karakter dizeleri hariç dar karakter sürümleriyle aynıdır.

**_ASSERT_EXPR**, **_onaylama** ve **_ASSERTE** makrolar ve Crtdbg. h > \<dahil tarafından kullanılabilir olsa da, **_hata ayıklama** tanımlandığında uygulamanın C çalışma zamanı kitaplığının hata ayıklama sürümüyle bağlanması gerekir, çünkü Bu makrolar diğer çalışma zamanı işlevlerini çağırır.

## <a name="requirements"></a>Gereksinimler

|Makrosu|Gerekli başlık|
|-----------|---------------------|
|**_ASSERT_EXPR**, **_ONAYLAMA**, **_ASSERTE**|\<Crtdbg. h >|

## <a name="example"></a>Örnek

Bu programda, koşulu `string1 == string2`test etmek için **_Onaylama** ve **_ASSERTE** makrolarında çağrılar yapılır. Durum başarısız olursa, bu makrolar bir tanılama iletisi yazdırır. **_Rpt** ve **_RPTF** grubu, bu programda **printf** işlevine alternatif olarak de geçerli olur.

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
