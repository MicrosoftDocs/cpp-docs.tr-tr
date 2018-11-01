---
title: _ASSERT, _ASSERTE, _ASSERT_EXPR makroları
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
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598464"
---
# <a name="assert-asserte-assertexpr-macros"></a>_ASSERT, _ASSERTE, _ASSERT_EXPR makroları

Bir ifadeyi değerlendirir ve sonucu olduğunda bir hata ayıklama raporunu oluşturur **False** (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
// Typical usage:
_ASSERT_EXPR( booleanExpression, message );
_ASSERT( booleanExpression );
_ASSERTE( booleanExpression );
```

### <a name="parameters"></a>Parametreler

*booleanDeyimi*<br/>
Skaler bir ifade (işaretçi ifadeleri dahil), sıfır olmayan (true) veya 0 (false) için değerlendirir.

*message*<br/>
Raporun parçası görüntülenecek bir geniş dize.

## <a name="remarks"></a>Açıklamalar

**_ASSERT_EXPR**, **_ASSERT** ve **_ASSERTE** makroları bir uygulama hata ayıklama işlemi sırasında varsayımlar denetimi temiz ve basit bir mekanizma sağlar. İçinde içine alınması gerekmez çünkü bunlar çok esnek `#ifdef` olmasını engellemek için ifadeleri adlı bir uygulama bir perakende yapı içinde. Bu esnekliğin kullanılarak elde edilir [_DEBUG](../../c-runtime-library/debug.md) makrosu. **_ASSERT_EXPR**, **_ASSERT** ve **_ASSERTE** yalnızca ne zaman kullanılabilir **_DEBUG** derleme zamanında tanımlanır. Zaman **_DEBUG** olduğu tanımlı değilse, bu makroları için çağrılar ön işleme sırasında kaldırılır.

**_ASSERT_EXPR**, **_ASSERT** ve **_ASSERTE** değerlendirmek, *booleanDeyimi* bağımsız değişkeni ve sonucu olduğunda **false**(0), bir tanılama iletisi ve çağrı yazdırma [_CrtDbgReportW](crtdbgreport-crtdbgreportw.md) hata ayıklama raporu oluşturmak için. **_ASSERT** makrosu basit bir tanılama iletisi yazdırır **_ASSERTE** iletide başarısız ifadesi bir dize gösterimini içerir ve **_ASSERT_EXPR** içerir *ileti* tanılama iletisi dizesi. Bu makrolar hiçbir şey yapma, *booleanDeyimi* için sıfır olmayan değerlendirir.

**_ASSERT_EXPR**, **_ASSERT** ve **_ASSERTE** çağırma **_CrtDbgReportW**, geniş karakter olacak şekilde tüm çıktı neden olur. **_ASSERTE** Unicode karakterler düzgün yazdırır *booleanDeyimi* ve **_ASSERT_EXPR** Unicode karakter yazdırır *ileti*.

Çünkü **_ASSERTE** makrosu, başarısız bir ifade belirtir ve **_ASSERT_EXPR** sağlar oluşturulan raporda bir ileti belirtin, bunlar başvuru olmadan sorunu tanımlamak kullanıcıları etkinleştirin Uygulama kaynak kodu. Ancak, bir dezavantajı, her var. *ileti* tarafından yazdırılan **_ASSERT_EXPR** ve her bir ifade tarafından değerlendirilen **_ASSERTE** çıkış (hata ayıklama sürümü) dahildir Dosya, uygulamanızın bir dize sabiti olarak. Bu nedenle, çok sayıda varsa çağrıları yapılan **_ASSERT_EXPR** veya **_ASSERTE**, bu ifadeler, çıktı dosyanızın boyutunu önemli ölçüde artırabilirsiniz.

İle aksini belirtmediğiniz sürece [_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevleri, iletileri ayarına eşdeğer bir açılır iletişim kutusu görüntülenir:

```C
_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);
````

**_CrtDbgReportW** hata ayıklama raporunu oluşturur ve kendi hedef veya hedefleri, geçerli rapor modunu veya modlarını ve dosya için tanımlı temel belirler **_CRT_ASSERT** rapor türü. Varsayılan olarak, onaylama hatalarını ve hata için bir hata ayıklama ileti penceresine yönlendirilirsiniz. [_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevler her rapor türü için hedeflerini tanımlamak için kullanılır.

Hedef bir hata ayıklama ileti penceresiyle ve kullanıcı olduğunda tıkladığında **yeniden** düğmesi **_CrtDbgReportW** 1 döndürür neden **_ASSERT_EXPR**, **_ ASSERT** ve **_ASSERTE** makroların just-in-time (JIT) hata ayıklama etkin olması koşuluyla, hata ayıklayıcıyı başlatın.

Raporlama işlemi hakkında daha fazla bilgi için bkz: [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) işlevi. Onaylama işlemi hataları çözme ve bu makrolar hata ayıklama bir hata işleme mekanizması olarak kullanma hakkında daha fazla bilgi için bkz. [doğrulama ve raporlama için makroları kullanma](/visualstudio/debugger/macros-for-reporting).

Ek olarak **_ASSERT** makroları [assert](assert-macro-assert-wassert.md) makrosu, program mantığı doğrulamak için kullanılabilir. Bu makro, hem hata ayıklama ve yayın sürümlerinde kitaplıkları kullanılabilir. [_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) hata ayıklama makroları hata ayıklama raporunu oluşturmak için kullanılabilen aynı zamanda, ancak bir ifadeyi değerlendirmez. **_RPT** makroları, basit bir rapor oluşturur. **_RPTF** makroları, oluşturulan raporda rapor makroyu burada çağrıldı kaynak dosya ve satır numarası içerir. Bu makroların geniş karakter sürümleri kullanılabilir (**_RPTW**, **_RPTFW**). Geniş karakter sürümleri, geniş karakter dizeleri, tüm dize parametreleri ve çıkış için kullanılan dışında dar karakter sürümleri için aynıdır.

Ancak **_ASSERT_EXPR**, **_ASSERT** ve **_ASSERTE** makrolar ve ekleyerek kullanılabilir \<crtdbg.h >, uygulama ile hata ayıklama bağlamanız gerekir C çalışma zamanı kitaplık sürümünü olduğunda **_DEBUG** Bu makrolar diğer çalışma zamanı işlevleri çağırmak için tanımlanır.

## <a name="requirements"></a>Gereksinimler

|Makrosu|Gerekli başlık|
|-----------|---------------------|
|**_ASSERT_EXPR**, **_ASSERT**, **_ASSERTE**|\<crtdbg.h >|

## <a name="example"></a>Örnek

Bu programda çağrıları yapılan **_ASSERT** ve **_ASSERTE** koşulunu test etmek için makroları `string1 == string2`. Koşul başarısız olursa, bu makrolar bir tanılama iletisi yazdırın. **_RPT** ve **_RPTF** makroları grup da kullandı bu programda, alternatif olarak **printf** işlevi.

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
