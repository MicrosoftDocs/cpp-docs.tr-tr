---
title: "_ASSERT, _ASSERTE, _ASSERT_EXPR makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07be60643ad77e1138c3c23a1dd358a1d4177f25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="assert-asserte-assertexpr-macros"></a>_ASSERT, _ASSERTE, _ASSERT_EXPR makroları
Bir ifade değerlendirme ve sonucu olduğunda hata ayıklama rapor oluşturmak `False` (yalnızca hata ayıklama sürümü).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_ASSERT_EXPR(  
   booleanExpression,  
   message  
);  
_ASSERT(   
   booleanExpression   
);  
_ASSERTE(   
   booleanExpression   
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `booleanExpression`  
 (İşaretçi ifadeleri dahil) olan ve sıfır olmayan bir değer (true) veya 0 (false) skaler bir ifade.  
  
 `message`  
 Rapor bir parçası olarak görüntülenecek geniş bir dize.  
  
## <a name="remarks"></a>Açıklamalar  
 `_ASSERT_EXPR`, `_ASSERT` Ve `_ASSERTE` makrolar varsayımlar hata ayıklama işlemi sırasında denetleme temiz ve basit bir mekanizma ile bir uygulama sağlar. İçinde alınmalıdır gerekmediği için çok esnektir `#ifdef` olmasını engellemek için deyimleri adlı bir uygulama bir perakende yapı içinde. Bu esneklik kullanılarak elde edilir [_DEBUG](../../c-runtime-library/debug.md) makrosu. `_ASSERT_EXPR`, `_ASSERT` ve `_ASSERTE` yalnızca ne zaman kullanılabilir `_DEBUG` derleme zamanında tanımlanır. Zaman `_DEBUG` olan tanımlı değilse, bu makroları çağrıları ön işleme sırasında kaldırılır.  
  
 `_ASSERT_EXPR`, `_ASSERT` ve `_ASSERTE` değerlendirmek kendi `booleanExpression` bağımsız değişkeni ve sonuç olduğunda `false` (0), bir tanılama iletisi ve çağrı yazdırma [_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) hata ayıklama rapor oluşturmak için. `_ASSERT` Makrosu yazdırır basit bir tanılama iletisi `_ASSERTE` iletisinde başarısız ifade bir dize gösterimini içeren ve `_ASSERT_EXPR` içeren `message` tanılama iletisi dizesi. Bu makroları hiçbir şey yapma zaman `booleanExpression` için sıfır olmayan değerlendirir.  
  
 `_ASSERT_EXPR`, `_ASSERT` ve `_ASSERTE` çağırma `_CrtDbgReportW`, geniş karakter olması tüm çıktı neden olur. `_ASSERTE`Unicode karakterler düzgün yazdırır `booleanExpression` ve `_ASSERT_EXPR` Unicode karakter yazdırır `message`.  
  
 Çünkü `_ASSERTE` makrosu başarısız ifade belirtir ve `_ASSERT_EXPR` sağlar oluşturulan rapora bir ileti belirtin, uygulamanın kaynak koduna başvuran olmadan sorunu tanımlamak kullanıcıları etkinleştirin. Ancak, bir dezavantajı her bulunduğunu `message` tarafından yazdırılan `_ASSERT_EXPR` ve tarafından değerlendirilen her ifade `_ASSERTE` bir dize sabiti olarak, uygulamanızın çıkış (hata ayıklama sürümü) dosyasına dahil edilir. Bu nedenle, çok sayıda varsa çağrıları yapılan `_ASSERT_EXPR` veya `_ASSERTE`, bu ifadeler, çıktı dosyanızın boyutunu önemli ölçüde artırabilir.  
  
 Aksi takdirde ile belirtilmedikçe [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) ve [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) işlevleri, iletileri ayarına eşdeğer bir açılır iletişim kutusu görüntülenir:  
  
`_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);`  
  
 `_CrtDbgReportW`hata ayıklama raporu oluşturur ve hedef veya geçerli rapor modu veya modları ve dosya için tanımlanan göre hedefler belirler `_CRT_ASSERT` rapor türü. Varsayılan olarak, onaylama işlemi hataları ve hataları bir hata ayıklama iletisi penceresine yönlendirilirsiniz. [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) ve [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) işlevleri, her rapor türü için hedefleri tanımlamak için kullanılır.  
  
 Hedef bir hata ayıklama iletisi penceresi ve kullanıcı olduğunda tıklar **yeniden deneme** düğmesini `_CrtDbgReportW` 1 döndürür neden `_ASSERT_EXPR`, `_ASSERT` ve `_ASSERTE` hata ayıklayıcısını başlatmak üzere makroları sağlanan tam zamanında (JIT) hata ayıklama etkin.  
  
 Raporlama işlemi hakkında daha fazla bilgi için bkz: [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) işlevi. Onaylama işlemi hataları giderme ve hata ayıklama bir hata işleme mekanizması olarak bu makroları kullanma hakkında daha fazla bilgi için bkz: [doğrulama ve raporlama makroları kullanarak](/visualstudio/debugger/macros-for-reporting).  
  
 Ek olarak `_ASSERT` makroları [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu, program mantığı doğrulamak için kullanılabilir. Bu makrosu hem hata ayıklama ve yayın sürümlerini kitaplıkları içinde kullanılabilir. [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) debug makroları de hata ayıklama raporu oluşturmak için kullanılabilir, ancak bu bir ifade değerlendirmez. `_RPT` Makroları basit bir rapor oluşturur. `_RPTF` Makroları oluşturulan rapora burada rapor makrosu çağrıldı kaynak dosyası ve satır numarası içerir. Geniş karakter Bu makroların sürümleri (`_RPTWn`, `_RPTFWn`). Geniş karakter dizeleri tüm dizesi parametreleri ve çıktı için kullanılan dışında geniş karakter sürümleri dar karakter sürümleri için aynıdır.  
  
 Rağmen `_ASSERT_EXPR`, `_ASSERT` ve `_ASSERTE` makrolar ve ekleyerek kullanılabilir \<crtdbg.h >, uygulamanın hata ayıklama sürümü C çalışma zamanı kitaplığı ile bağlantı gerekir zaman `_DEBUG` bu makroları çağırmak için tanımlanan diğer çalışma zamanı işlevleri.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Makrosu|Gerekli başlık|  
|-----------|---------------------|  
|`_ASSERT_EXPR`,                  `_ASSERT`, `_ASSERTE`|\<crtdbg.h >|  
  
## <a name="example"></a>Örnek  
 Bu programda çağrıları yapılan `_ASSERT` ve `_ASSERTE` koşulu test etmek için makroları `string1 == string2`. Koşul başarısız olursa, bu makroları bir tanılama iletisi yazdırın. `_RPTn` Ve `_RPTFn` makroları grup da kullandı bu programda alternatif olarak `printf` işlevi.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [Assert makrosu, _assert, _wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [_RPT, _RPTF, _RPTW, _RPTFW Makroları](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)