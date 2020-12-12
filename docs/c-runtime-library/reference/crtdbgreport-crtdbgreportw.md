---
description: 'Hakkında daha fazla bilgi edinin: _CrtDbgReport _CrtDbgReportW'
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
ms.openlocfilehash: 523dc65f846804b13b83bf08b0499b2459fe22ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319810"
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
Rapor türü: **_CRT_WARN**, **_CRT_ERROR** ve **_CRT_ASSERT**.

*filename*<br/>
Onaylama/rapor gerçekleştiği veya **null** olan kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Onaylama/rapor gerçekleştiği veya **null** olan kaynak dosyadaki satır numarası.

*Ladı*<br/>
Onaylama veya rapor gerçekleştiği modülün (. exe veya. dll) adı işaretçisi.

*formatını*<br/>
Kullanıcı iletisini oluşturmak için kullanılan format-Control dize işaretçisi.

*değişkendir*<br/>
*Biçim* tarafından kullanılan isteğe bağlı değiştirme bağımsız değişkenleri.

## <a name="return-value"></a>Dönüş Değeri

Tüm rapor hedefleri için, **_CrtDbgReport** ve **_CrtDbgReportW** bir hata oluşursa-1 ve herhangi bir hatayla karşılaşılana 0 döndürür. Ancak, rapor hedefi bir hata ayıklama iletisi penceresidir ve Kullanıcı **yeniden dene** düğmesine tıkladığında, bu işlevler 1 döndürür. Kullanıcı hata ayıklama Iletisi penceresindeki **Durdur** düğmesine tıkladığında, bu işlevler hemen durdurulur ve bir değer döndürmez.

_RPT hata ayıklama makroları, hata ayıklama raporlarını oluşturmak için **_CrtDbgReport** çağırır [_RPTF](rpt-rptf-rptw-rptfw-macros.md) . Bu makroların geniş karakterli sürümlerinin yanı sıra [_ASSERT, _ASSERTE](assert-asserte-assert-expr-macros.md), [_rptw](rpt-rptf-rptw-rptfw-macros.md) ve [_rptfw](rpt-rptf-rptw-rptfw-macros.md), hata ayıklama raporlarını oluşturmak için **_CrtDbgReportW** kullanır. **_CrtDbgReport** veya **_CrtDbgReportW** 1 ' i döndürdüğünüzde, tam zamanında (JIT) hata ayıklamanın etkinleştirildiğinden bu makrolar hata ayıklayıcıyı başlatır.

## <a name="remarks"></a>Açıklamalar

**_CrtDbgReport** ve **_CrtDbgReportW** , hata ayıklama raporunu üç farklı hedefe gönderebilir: hata ayıklama rapor dosyası, hata ayıklama İzleyicisi (Visual Studio hata ayıklayıcı) veya hata ayıklama iletisi penceresi. [_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md)iki yapılandırma işlevi, her rapor türü için hedefi veya hedefleri belirtmek için kullanılır. Bu işlevler, her rapor türü için raporlama hedefinin veya hedeflerin ayrı olarak denetlenmesini sağlar. Örneğin, bir **_CRT_WARN** *reportType* 'ın yalnızca hata ayıklama izleyicisine gönderileceğini belirtmek mümkündür. bu, bir tür **_CRT_ASSERT** *reportType* iletisi penceresine ve Kullanıcı tanımlı bir rapor dosyasına gönderilir.

**_CrtDbgReportW** , **_CrtDbgReport** geniş karakter sürümüdür. Tüm çıkış ve dize parametreleri geniş karakterli dizelerdir; Aksi takdirde, tek baytlık karakter sürümü ile aynıdır.

**_CrtDbgReport** ve **_CrtDbgReportW** , [**n** *] bağımsız değişkenlerini* **printf** veya **wprintf** işlevleri tarafından tanımlanan kuralların kullanıldığı *Biçim* dizesine geçirerek hata ayıklama raporu için Kullanıcı iletisini oluşturun. Bu işlevler daha sonra hata ayıklama raporunu oluşturur ve geçerli rapor modlarına ve *reportType* için tanımlanan dosyaya göre hedef veya hedefleri tespit edin. Rapor bir hata ayıklama iletisi penceresine gönderildiğinde, *dosya adı*, **LineNumber** ve *ModuleName* pencerede görüntülenen bilgilere dahil edilir.

Aşağıdaki tabloda, rapor modu veya modlar ve dosya için kullanılabilir seçenekler ve **_CrtDbgReport** ve **_CrtDbgReportW** elde edilen davranış listelenmiştir. Bu seçenekler içinde bit bayrakları olarak tanımlanmıştır \<crtdbg.h> .

|Rapor modu|Rapor dosyası|**_CrtDbgReport**, **_CrtDbgReportW** davranışı|
|-----------------|-----------------|------------------------------------------------|
|**_CRTDBG_MODE_DEBUG**|Geçerli değil|Windows [OutputDebugString](/windows/win32/api/debugapi/nf-debugapi-outputdebugstringw) API kullanarak ileti yazar.|
|**_CRTDBG_MODE_WNDW**|Geçerli değil|İletiyi **iptal** etme, **yeniden deneme** ve **yoksayma** düğmeleriyle birlikte göstermek Için ileti kutusu oluşturmak üzere Windows [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) API 'sini çağırır. Kullanıcı **iptal**' i tıklarsa **_CrtDbgReport** veya **_CrtDbgReport** hemen iptal edilir. Kullanıcı **yeniden dene**' ye tıkladığında 1 döndürür. Kullanıcı **Yoksay**' ı tıklarsa, yürütme devam eder ve **_CrtDbgReport** ve **_CrtDbgReportW** 0 döndürür. Hata durumu var olduğunda **Yoksay** ' a tıkladığınızda genellikle "tanımsız davranış" ile sonuçlanır.|
|**_CRTDBG_MODE_FILE**|**__HFILE**|Windows [WriteFile](/windows/win32/api/fileapi/nf-fileapi-writefile) API 'sini kullanarak Kullanıcı tarafından sağlanan **tanıtıcıya** ileti yazar ve dosya tanıtıcısının geçerliliğini doğrulamaz; uygulama, rapor dosyasını açmaktan ve geçerli bir dosya tanıtıcısını geçirmekten sorumludur.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDERR**|**Stderr**'e ileti yazar.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDOUT**|**Stdout**'a ileti yazar.|

Rapor bir, iki veya üç hedefe veya hiç hedefe gönderilebilir. Rapor modunu veya modlarını ve rapor dosyasını belirtme hakkında daha fazla bilgi için [_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevlerine bakın. Hata ayıklama makroları ve raporlama işlevlerini kullanma hakkında daha fazla bilgi için bkz: [Raporlama makroları](/visualstudio/debugger/macros-for-reporting).

Uygulamanızın **_CrtDbgReport** ve **_CrtDbgReportW** tarafından sağlanmasından daha fazla esneklik gerekiyorsa, kendi raporlama işlevinizi yazabilir ve [_CrtSetReportHook](crtsetreporthook.md) işlevini kullanarak C çalışma zamanı kitaplığı raporlama mekanizmasına bağlayabilirsiniz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDbgReport**|\<crtdbg.h>|
|**_CrtDbgReportW**|\<crtdbg.h>|

**_CrtDbgReport** ve **_CrtDbgReportW** Microsoft uzantılarıdır. Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportMode](crtsetreportmode.md)<br/>
[_CrtSetReportFile](crtsetreportfile.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
