---
title: _CrtDbgReport, _CrtDbgReportW
ms.date: 11/04/2016
api_name:
- _CrtDbgReport
- _CrtDbgReportW
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
- CrtDbgReport
- CrtDbgReportW
- _CrtDbgReportW
- _CrtDbgReport
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
ms.openlocfilehash: 986777f755a749e858f7e51b5aa19f10090db13a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938834"
---
# <a name="_crtdbgreport-_crtdbgreportw"></a>_CrtDbgReport, _CrtDbgReportW

Hata ayıklama iletisi içeren bir rapor oluşturur ve raporu üç olası hedefe gönderir (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
int _CrtDbgReport(
   int reportType,
   const char *filename,
   int linenumber,
   const char *moduleName,
   const char *format [,
   argument] ...
);
int _CrtDbgReportW(
   int reportType,
   const wchar_t *filename,
   int linenumber,
   const wchar_t *moduleName,
   const wchar_t *format [,
   argument] ...
);
```

### <a name="parameters"></a>Parametreler

*reportType*<br/>
Rapor türü: **_CRT_WARN**, **_CRT_ERROR**ve **_CRT_ASSERT**.

*kısaltın*<br/>
Onaylama/rapor gerçekleştiği veya **null**olan kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Onaylama/rapor gerçekleştiği veya **null**olan kaynak dosyadaki satır numarası.

*Ladı*<br/>
Onaylama veya rapor gerçekleştiği modülün (. exe veya. dll) adı işaretçisi.

*format*<br/>
Kullanıcı iletisini oluşturmak için kullanılan format-Control dize işaretçisi.

*değişkendir*<br/>
*Biçim*tarafından kullanılan isteğe bağlı değiştirme bağımsız değişkenleri.

## <a name="return-value"></a>Dönüş Değeri

Tüm rapor hedefleri için, **_Crtdbgreport** ve **_Crtdbgreportw** bir hata oluşursa-1 ve herhangi bir hatayla karşılaşılması durumunda 0 döndürür. Ancak, rapor hedefi bir hata ayıklama iletisi penceresidir ve Kullanıcı **yeniden dene** düğmesine tıkladığında, bu işlevler 1 döndürür. Kullanıcı hata ayıklama Iletisi penceresindeki **Durdur** düğmesine tıkladığında, bu işlevler hemen durdurulur ve bir değer döndürmez.

[_Rpt, _RPTF](rpt-rptf-rptw-rptfw-macros.md) hata ayıklama makroları, hata ayıklama raporlarını oluşturmak Için **_Crtdbgreport** öğesini çağırır. Bu makroların geniş karakterli sürümlerinin yanı sıra [_Onaylama, _ASSERTE](assert-asserte-assert-expr-macros.md), [_rptw](rpt-rptf-rptw-rptfw-macros.md) ve [_rptfw](rpt-rptf-rptw-rptfw-macros.md), hata ayıklama raporlarını oluşturmak Için **_CrtDbgReportW** kullanın. **_CrtDbgReport** veya **_Crtdbgreportw** 1 değerini döndürdüğünüzde, tam zamanında (JIT) hata ayıklamanın etkin olması şartıyla bu makrolar hata ayıklayıcıyı başlatır.

## <a name="remarks"></a>Açıklamalar

**_Crtdbgreport** ve **_Crtdbgreportw** , hata ayıklama raporunu üç farklı hedefe gönderebilir: hata ayıklama rapor dosyası, hata ayıklama İzleyicisi (Visual Studio hata ayıklayıcı) veya hata ayıklama iletisi penceresi. Her rapor türü için hedefi veya hedefleri belirtmek için, [_CrtSetReportMode](crtsetreportmode.md) ve [_Crtsetreportfile](crtsetreportfile.md)olmak üzere iki yapılandırma işlevi kullanılır. Bu işlevler, her rapor türü için raporlama hedefinin veya hedeflerin ayrı olarak denetlenmesini sağlar. Örneğin, bir **_CRT_WARN** reportType *'ın yalnızca* hata ayıklama Izleyicisine gönderileceğini, bir **_CRT_ASSERT** *reportType* , bir hata ayıklama iletisi penceresine ve Kullanıcı tanımlı bir rapor dosyasına gönderilmesini belirtmek mümkündür.

**_Crtdbgreportw** , **_Crtdbgreport**öğesinin geniş karakterli sürümüdür. Tüm çıkış ve dize parametreleri geniş karakterli dizelerdir; Aksi takdirde, tek baytlık karakter sürümü ile aynıdır.

**_Crtdbgreport** ve **_Crtdbgreportw** [**n** *] bağımsız değişkenlerini*, **printf** ya **da tarafından tanımlanan aynı kuralları kullanarak biçim dizesinde değiştirerek hata ayıklama raporu için Kullanıcı iletisini oluşturun wprintf** işlevleri. Bu işlevler daha sonra hata ayıklama raporunu oluşturur ve geçerli rapor modlarına ve *reportType*için tanımlanan dosyaya göre hedef veya hedefleri tespit edin. Rapor bir hata ayıklama iletisi penceresine gönderildiğinde, *dosya adı*, **LineNumber**ve *ModuleName* pencerede görüntülenen bilgilere dahil edilir.

Aşağıdaki tabloda, rapor modu veya modlar ve dosya için kullanılabilen seçimler ve **_Crtdbgreport** ve **_Crtdbgreportw**için ortaya çıkan davranış listelenmektedir. Bu seçenekler, \<Crtdbg. h > bit bayrakları olarak tanımlanmıştır.

|Rapor modu|Rapor dosyası|**_CrtDbgReport**, **_CrtDbgReportW** davranışı|
|-----------------|-----------------|------------------------------------------------|
|**_CRTDBG_MODE_DEBUG**|Geçerli değil|Windows [OutputDebugString](/windows/win32/api/debugapi/nf-debugapi-outputdebugstringw) API kullanarak ileti yazar.|
|**_CRTDBG_MODE_WNDW**|Geçerli değil|İletiyi **iptal**etme, **yeniden deneme**ve **yoksayma** düğmeleriyle birlikte göstermek Için ileti kutusu oluşturmak üzere Windows [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) API 'sini çağırır. Kullanıcı **Durdur**' a tıkladığında **_CrtDbgReport** veya **_CrtDbgReport** hemen iptal edilir. Kullanıcı **yeniden dene**' ye tıkladığında 1 döndürür. Kullanıcı **Yoksay**' ı tıklarsa, yürütme devam eder ve **_CrtDbgReport** ve **_Crtdbgreportw** 0 döndürür. Hata durumu var olduğunda **Yoksay** ' a tıkladığınızda genellikle "tanımsız davranış" ile sonuçlanır.|
|**_CRTDBG_MODE_FILE**|**__HFILE**|Windows [WriteFile](/windows/win32/api/fileapi/nf-fileapi-writefile) API 'sini kullanarak Kullanıcı tarafından sağlanan **tanıtıcıya**ileti yazar ve dosya tanıtıcısının geçerliliğini doğrulamaz; uygulama, rapor dosyasını açmaktan ve geçerli bir dosya tanıtıcısını geçirmekten sorumludur.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDERR**|**Stderr**'e ileti yazar.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDOUT**|**Stdout**'a ileti yazar.|

Rapor bir, iki veya üç hedefe veya hiç hedefe gönderilebilir. Rapor modunu veya modlarını ve rapor dosyasını belirtme hakkında daha fazla bilgi için, bkz. [_Crtsetreportmode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevleri. Hata ayıklama makroları ve raporlama işlevlerini kullanma hakkında daha fazla bilgi için bkz: [Raporlama makroları](/visualstudio/debugger/macros-for-reporting).

Uygulamanızın **_Crtdbgreport** ve **_Crtdbgreportw**tarafından sağlanmasından daha fazla esneklik ihtiyacı varsa, kendi raporlama Işlevinizi yazabilir ve [_Crtsetreporthook](crtsetreporthook.md) kullanarak C çalışma zamanı kitaplığı raporlama mekanizmasına bağlayabilirsiniz. çalışmayacaktır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDbgReport**|\<Crtdbg. h >|
|**_CrtDbgReportW**|\<Crtdbg. h >|

**_Crtdbgreport** ve **_Crtdbgreportw** , Microsoft uzantılarıdır. Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

```C
// crt_crtdbgreport.c
#include <crtdbg.h>

int main(int argc, char *argv[]) {
#ifdef _DEBUG
   _CrtDbgReport(_CRT_ASSERT, __FILE__, __LINE__, argv[0], NULL);
#endif
}
```

Rapor işlevinin nasıl değiştirileceği hakkında bir örnek için bkz. [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2) .

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportMode](crtsetreportmode.md)<br/>
[_CrtSetReportFile](crtsetreportfile.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
