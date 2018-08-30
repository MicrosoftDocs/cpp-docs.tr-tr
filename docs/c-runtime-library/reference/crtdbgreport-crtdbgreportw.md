---
title: _CrtDbgReport, _CrtDbgReportW | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtDbgReport
- _CrtDbgReportW
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
- CrtDbgReport
- CrtDbgReportW
- _CrtDbgReportW
- _CrtDbgReport
dev_langs:
- C++
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5aa7efb7881b00933afab92a7157c09e0f769605
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204429"
---
# <a name="crtdbgreport-crtdbgreportw"></a>_CrtDbgReport, _CrtDbgReportW

Hata ayıklama iletisi içeren bir rapor oluşturur ve raporu üç olası hedefe (yalnızca hata ayıklama sürümü) gönderir.

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
Rapor türü: **_CRT_WARN**, **_CRT_ERROR**, ve **_CRT_ASSERT**.

*Dosya adı*<br/>
Onaylama/raporlama gerçekleşen kaynak dosyasının adı işaretçi veya **NULL**.

*LineNumber*<br/>
Satır numarası onaylama/raporlama gerçekleşen kaynak dosyasında veya **NULL**.

*Modül adı*<br/>
İşaretçi (.exe veya .dll) modülünün adı burada assert veya rapor oluştu.

*Biçim*<br/>
Kullanıcı iletisini oluşturmak için kullanılan biçim denetimli dizeye yönelik işaretçi.

*Bağımsız değişken*<br/>
Tarafından kullanılan isteğe bağlı değiştirme bağımsız değişkenleri *biçimi*.

## <a name="return-value"></a>Dönüş Değeri

Tüm rapor hedefleri için **_CrtDbgReport** ve **_CrtDbgReportW** herhangi bir hatayla hata oluşması durumunda -1 ve 0 döndürür. Ancak, rapor hedefi bir hata ayıklama ileti penceresiyle ve kullanıcı olduğunda tıkladığında **yeniden** düğmesi, bu işlevler 1 döndürür. Kullanıcı tıklarsa **iptal** düğmesi hata ayıklama iletisi penceresinde bu işlevler hemen durdurmak ve bir değer döndürmüyor.

[_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) hata ayıklama makroları çağrı **_CrtDbgReport** raporları hata ayıklama oluşturmak için. Bu makroların geniş karakter sürümleri ile birlikte [_ASSERT, _ASSERTE](assert-asserte-assert-expr-macros.md), [_RPTW](rpt-rptf-rptw-rptfw-macros.md) ve [_RPTFW](rpt-rptf-rptw-rptfw-macros.md), kullanın **_CrtDbgReportW** için hata ayıklama raporlarının oluşturur. Zaman **_CrtDbgReport** veya **_CrtDbgReportW** dönüş 1, just-in-time (JIT) hata ayıklama etkin olması koşuluyla Bu makrolar hata ayıklayıcısını başlatır.

## <a name="remarks"></a>Açıklamalar

**_CrtDbgReport** ve **_CrtDbgReportW** hata ayıklama raporunu üç farklı hedefe gönderebilir: hata ayıklama raporu dosyasına, hata ayıklama monitörüne (Visual Studio hata ayıklayıcı) veya hata ayıklama ileti penceresine. İki yapılandırma işlevi, [_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md), hedef veya hedefleri için her bir rapor türü belirtmek için kullanılır. Bu işlevler, raporlama hedefinin veya hedeflerinin ayrı kontrol edilmesini her bir rapor türü için izin verir. Örneğin belirtmek olası bir *reportType* , **_CRT_WARN** yalnızca hata ayıklama monitörüne gönderilirken, bir *reportType* , **_CRT_ASSERT** hata ayıklama ileti penceresine ve kullanıcı tanımlı bir rapor dosyası gönderilmesini.

**_CrtDbgReportW** öğesinin geniş karakterli sürümüdür **_CrtDbgReport**. Tüm çıkış ve dize parametreleri geniş karakterli dizeler şeklindedir; Aksi takdirde tek baytlı karakter sürümü ile aynıdır.

**_CrtDbgReport** ve **_CrtDbgReportW** değiştirerek hata ayıklama raporuna ilişkin kullanıcı iletisini oluşturmak *bağımsız değişken*[**n**] bağımsızdeğişkenler*biçimi* tarafından tanımlanan aynı kuralları kullanarak, dize **printf** veya **wprintf** işlevleri. Bu işlevler ardından hata ayıklama raporunu oluşturur ve hedefi veya hedefleri, geçerli rapor modlarına göre belirlenir ve için tanımlanan dosyaya *reportType*. Raporu bir hata ayıklama ileti penceresine gönderildiğinde *filename*, **lineNumber**, ve *moduleName* penceresinde görüntülenen bilgileri eklenir.

Aşağıdaki tablo rapor modu veya modları, dosya ve sonuçta elde edilen davranışı için kullanılabilen seçenekleri listeler **_CrtDbgReport** ve **_CrtDbgReportW**. Bu seçenekler bit bayrakları olarak tanımlanır \<crtdbg.h >.

|Rapor modu|Rapor dosyası|**_CrtDbgReport**, **_CrtDbgReportW** davranışı|
|-----------------|-----------------|------------------------------------------------|
|**_CRTDBG_MODE_DEBUG**|Geçerli değil|Windows kullanarak ileti yazar [OutputDebugString](https://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API.|
|**_CRTDBG_MODE_WNDW**|Geçerli değil|Windows çağırır [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) beraber iletiyi görüntülemek için ileti kutusu oluşturmak için API **iptal**, **yeniden**, ve **Yoksay** düğmeleri. Bir kullanıcı tıklarsa **iptal**, **_CrtDbgReport** veya **_CrtDbgReport** hemen durdurur. Bir kullanıcı tıklarsa **yeniden**, 1 döndürür. Bir kullanıcı tıklarsa **Yoksay**, yürütme devam eder ve **_CrtDbgReport** ve **_CrtDbgReportW** 0 değerini döndürür. Sonuçlandığını unutmayın **Yoksay** ne zaman bir hata koşulu tıklatılmasının "tanımsız davranış."|
|**_CRTDBG_MODE_FILE**|**__HFILE**|Kullanıcı tarafından sağlanan ileti yazar **İŞLEMEK**, Windows kullanarak [WriteFile](/windows/desktop/api/fileapi/nf-fileapi-writefile) API ve mu Dosya tanıtıcısının geçerliliğini doğrulamaz; uygulama rapor dosyasını açmaktan ve geçerli bir dosya geçirme sorumludur tanıtıcı.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDERR**|İleti yazar **stderr**.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDOUT**|İleti yazar **stdout**.|

Rapor bir, iki veya üç hedefe veya hiç bir hedefe hiç gönderilebilir. Rapor modunu veya modlarını ve rapor dosyasını belirtme hakkında daha fazla bilgi için bkz. [_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevleri. Hata ayıklama makrolarını kullanma ve işlevleri raporlama hakkında daha fazla bilgi için bkz. [raporlama için makroları](/visualstudio/debugger/macros-for-reporting).

Uygulamanız tarafından verilenden daha fazla esneklik gerekip gerekmediğini **_CrtDbgReport** ve **_CrtDbgReportW**, kendi raporlama işlevi yazma ve C çalışma zamanı kitaplığı raporlama uygulamasına bağlama mekanizması kullanarak [_CrtSetReportHook](crtsetreporthook.md) işlevi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDbgReport**|\<crtdbg.h >|
|**_CrtDbgReportW**|\<crtdbg.h >|

**_CrtDbgReport** ve **_CrtDbgReportW** Microsoft uzantılarıdır. Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

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

Bkz: [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2) nasıl rapor işlevini değiştirmenin bir örneği.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportMode](crtsetreportmode.md)<br/>
[_CrtSetReportFile](crtsetreportfile.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
