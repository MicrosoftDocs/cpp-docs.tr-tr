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
ms.openlocfilehash: 57290d2985036ea3df2863e175d742c819a3fe03
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405071"
---
# <a name="crtdbgreport-crtdbgreportw"></a>_CrtDbgReport, _CrtDbgReportW

Hata ayıklama iletisi ile bir rapor oluşturur ve rapor üç olası hedeflerine (yalnızca hata ayıklama sürümü) gönderir.

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
Assert rapor oluştuğu kaynak dosyasının adı işaretçi veya **NULL**.

*LineNumber*<br/>
Satır numarası assert rapor oluştuğu kaynak dosyasında veya **NULL**.

*Modül adı*<br/>
Modül (.exe veya .dll) adını işaretçisine burada assert veya rapor oluştu.

*Biçimi*<br/>
Kullanıcı iletisi oluşturmak için kullanılan biçim denetimi dize işaretçi.

*Bağımsız değişken*<br/>
Tarafından kullanılan isteğe bağlı değiştirme bağımsız *biçimi*.

## <a name="return-value"></a>Dönüş Değeri

Tüm rapor hedefler için **_CrtDbgReport** ve **_CrtDbgReportW** herhangi bir hatayla bir hata oluşursa, -1 ve 0 döndürür. Ancak, rapor hedef bir hata ayıklama iletisi penceresi ve kullanıcı olduğunda tıklar **yeniden deneme** düğmesi, bu işlevler 1 döndürür. Kullanıcı tıklarsa **Abort** düğmesi hata ayıklama ileti penceresinde bu işlevler hemen iptal etmek için ve bir değer döndürmüyor.

[_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) debug makroları çağrısı **_CrtDbgReport** raporları kendi hata ayıklama oluşturmak için. Bu makroları joker karakter sürümlerinin yanı [_ASSERT, _ASSERTE](assert-asserte-assert-expr-macros.md), [_RPTW](rpt-rptf-rptw-rptfw-macros.md) ve [_RPTFW](rpt-rptf-rptw-rptfw-macros.md), kullanın **_CrtDbgReportW** için hata ayıklama raporlarının oluşturur. Zaman **_CrtDbgReport** veya **_CrtDbgReportW** 1, dönüş tam zamanında (JIT) hata ayıklama etkin olması koşuluyla bu makroları hata ayıklayıcısını başlatın.

## <a name="remarks"></a>Açıklamalar

**_CrtDbgReport** ve **_CrtDbgReportW** hata ayıklama rapor üç farklı hedeflere gönderebilirsiniz: hata ayıklama rapor dosyası, hata ayıklama İzleyicisi (Visual Studio hata ayıklayıcısı) veya bir hata ayıklama iletisi penceresi. İki yapılandırma İşlevler, [_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md), her rapor türü için hedefleri ve hedef belirtmek için kullanılır. Bu işlevler raporlama hedef veya ayrı olarak denetlenmesini her rapor türü için hedefleri izin verir. Örneğin, belirtmek olası bir *reportType* , **_CRT_WARN** yalnızca hata ayıklama İzleyicisi gönderildi, ancak bir *reportType* , **_CRT_ASSERT** bir hata ayıklama iletisi penceresi ve kullanıcı tanımlı rapor dosyası gönderilmeyecek.

**_CrtDbgReportW** geniş karakter sürümü **_CrtDbgReport**. Tüm çıktı ve dize parametreleri joker karakter dizelerini olan; Aksi durumda tek baytlı karakter sürüme aynıdır.

**_CrtDbgReport** ve **_CrtDbgReportW** getirilmesiyle hata ayıklama rapor için kullanıcı iletisi oluşturmak *bağımsız değişkeni*[**n**] bağımsızdeğişkenler*biçimi* tarafından tanımlanan aynı kurallarını kullanarak, dize **printf** veya **wprintf** işlevleri. Bu işlevler sonra hata ayıklama raporu oluşturmak ve geçerli rapor modlarını temel hedeflerini, veya hedef belirleme ve dosya için tanımlanmış *reportType*. Rapor bir hata ayıklama iletisi penceresine gönderildiğinde *filename*, **lineNumber**, ve *moduleName* penceresinde görüntülenen bilgiler eklenir.

Rapor modu veya modları, dosya ve sonuçta elde edilen davranışını için kullanılabilir seçenekleri aşağıdaki tabloda listelenmektedir **_CrtDbgReport** ve **_CrtDbgReportW**. Bu seçenekler bit FLAGS içinde bayrak olarak tanımlanan \<crtdbg.h >.

|Rapor modu|Rapor dosyası|**_CrtDbgReport**, **_CrtDbgReportW** davranışı|
|-----------------|-----------------|------------------------------------------------|
|**_CRTDBG_MODE_DEBUG**|Geçerli değil|Windows kullanarak iletisi Yazar [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API.|
|**_CRTDBG_MODE_WNDW**|Geçerli değil|Windows çağırır [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) iletiyle boyunca görüntülenecek ileti kutusu oluşturmak için API **Abort**, **yeniden deneme**, ve **Yoksay** düğmeler. Bir kullanıcı tıklarsa **Abort**, **_CrtDbgReport** veya **_CrtDbgReport** hemen durdurur. Bir kullanıcı tıklarsa **yeniden**, 1 döndürür. Bir kullanıcı tıklarsa **Yoksay**, yürütme devam eder ve **_CrtDbgReport** ve **_CrtDbgReportW** 0 döndürür. Bu tıklatarak Not **Yoksay** ne zaman bir hata koşulu var. genellikle sonuçları "tanımsız davranış."|
|**_CRTDBG_MODE_FILE**|**__HFILE**|Kullanıcı tarafından sağlanan yazma iletiye **İŞLEMEK**, Windows kullanarak [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) API ve mu dosya tanıtıcısı geçerliliğini değil; uygulama rapor dosyasını açma ve geçerli bir dosya geçirme sorumludur işler.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDERR**|Yazma iletiye **stderr**.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDOUT**|Yazma iletiye **stdout**.|

Rapor bir, iki veya üç hedefler ya da herhangi bir hedef hiç gönderilebilir. Rapor modu veya modları ve rapor dosyası belirtme hakkında daha fazla bilgi için bkz: [_CrtSetReportMode](crtsetreportmode.md) ve [_CrtSetReportFile](crtsetreportfile.md) işlevleri. Hata ayıklama makroları kullanma ve raporlama işlevleri hakkında daha fazla bilgi için bkz: [raporlama makroları](/visualstudio/debugger/macros-for-reporting).

Uygulamanız tarafından sağlanan daha fazla esneklik gerekip gerekmediğini **_CrtDbgReport** ve **_CrtDbgReportW**, kendi raporlama işlevi yazma ve C çalışma zamanı kitaplığı raporlamasına bağlayın kullanarak mekanizması [_CrtSetReportHook](crtsetreporthook.md) işlevi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDbgReport**|\<crtdbg.h >|
|**_CrtDbgReportW**|\<crtdbg.h >|

**_CrtDbgReport** ve **_CrtDbgReportW** Microsoft uzantıları. Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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

Bkz: [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2) rapor işlevi değiştirme örneği.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportMode](crtsetreportmode.md)<br/>
[_CrtSetReportFile](crtsetreportfile.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
