---
title: _putenv, _wputenv
ms.date: 11/04/2016
api_name:
- _putenv
- _wputenv
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
- api-ms-win-crt-environment-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
helpviewer_keywords:
- _putenv function
- environment variables, deleting
- putenv function
- tputenv function
- environment variables, creating
- wputenv function
- _wputenv function
- _tputenv function
- environment variables, modifying
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
ms.openlocfilehash: 8fe699a476ea1dd09a6ce9922294bce398df16b2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949889"
---
# <a name="_putenv-_wputenv"></a>_putenv, _wputenv

Ortam değişkenlerini oluşturur, değiştirir veya kaldırır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md).

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _putenv(
   const char *envstring
);
int _wputenv(
   const wchar_t *envstring
);
```

### <a name="parameters"></a>Parametreler

*envstring*<br/>
Ortam-dize tanımı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa 0 veya hata durumunda-1 döndürün.

## <a name="remarks"></a>Açıklamalar

**_Putenv** işlevi yeni ortam değişkenleri ekler veya var olan ortam değişkenlerinin değerlerini değiştirir. Ortam değişkenleri bir işlemin yürütüldüğü ortamı tanımlar (örneğin, kitaplıklar için varsayılan arama yolu, bir program ile bağlantılandırılır). **_wputenv** , **_putenv**; öğesinin geniş karakterli bir sürümüdür. **_wputenv** için *envstring* bağımsız değişkeni geniş karakterli bir dizedir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

*Envstring* bağımsız değişkeni, *varname*=*value_string*biçimindeki bir dizenin işaretçisi olmalıdır; burada *varname* eklenecek veya değiştirilecek ortam değişkeninin adı, *value_string* değişkenin deeri. *Varname* zaten ortamın parçasıysa, değeri *value_string*ile değiştirilmiştir; Aksi takdirde, yeni *varname* değişkeni ve *value_string* değeri ortama eklenir. Boş bir *value_string*belirterek ya da başka bir deyişle, yalnızca *varname*= belirterek bir değişkeni ortamdan kaldırabilirsiniz.

**_putenv** ve **_wputenv** yalnızca geçerli işlem için yerel olan ortamı etkiler; komut düzeyi ortamı değiştirmek için bunları kullanamazsınız. Diğer bir deyişle, bu işlevler yalnızca çalışma zamanı kitaplığı için erişilebilir olan ve işletim sistemi tarafından bir işlem için oluşturulan ortam segmentinde olmayan veri yapıları üzerinde çalışır. Geçerli işlem sonlandırıldığında ortam, çağıran işlemin düzeyine döner (çoğu durumda, işletim sistemi düzeyi). Ancak, değiştirilen ortam **_üretilemedi**, **_exec**veya **System**tarafından oluşturulan yeni işlemlere geçirilebilir ve bu yeni süreçler **_putenv** ve **_wputenv**tarafından eklenen yeni öğeleri alır.

Doğrudan bir ortam girişi değiştirmeyin: bunun yerine, bunu değiştirmek için **_putenv** veya **_wputenv** kullanın. Özellikle, **_environ []** genel dizisinin doğrudan serbest bırakılmakta olan öğeleri, belirtilen hatalı belleğe yol açabilir.

**getenv** ve **_putenv** ortam tablosuna erişmek için **_environ** genel değişkenini kullanır; **_wgetenv** ve **_wputenv** Use **_wenviron**. **_putenv** ve **_wputenv** , **_environ** ve **_wenviron**değerini değiştirebilir, bu nedenle **_envp** bağımsız değişkenini **Main** ve **_wenvp** bağımsız değişkenini **wmain**olarak geçersiz duruma alabilir. Bu nedenle, ortam bilgilerine erişmek için **_environ** veya **_wenviron** kullanmak daha güvenlidir. **_Putenv** ve **_wputenv** ile genel değişkenlerin ilişkisi hakkında daha fazla bilgi için bkz. [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv** ve **_getenv** işlevleri iş parçacığı açısından güvenli değildir. **_putenv** dizeyi değiştirirken **_getenv** bir dize işaretçisi döndürebilir, rastgele hatalara neden olur. Bu işlevlere yapılan çağrıların eşitlendiğinden emin olun.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_putenv**|\<Stdlib. h >|
|**_wputenv**|\<Stdlib. h > veya \<wchar. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

**_Putenv**'nin nasıl kullanılacağına ilişkin bir örnek için bkz. [getenv, _wgetenv](getenv-wgetenv.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
