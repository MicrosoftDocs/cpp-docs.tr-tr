---
title: _putenv, _wputenv
ms.date: 4/2/2020
api_name:
- _putenv
- _wputenv
- _o__putenv
- _o__wputenv
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 3e74959e6c6cdb2e27ce0d68ba40d02d64949904
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333036"
---
# <a name="_putenv-_wputenv"></a>_putenv, _wputenv

Ortam değişkenleri oluşturur, değiştirir veya kaldırır. Bu işlevlerin daha güvenli sürümleri mevcuttur; [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md)bakın.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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
Çevre dize tanımı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı ysa 0 döndürün veya hata durumunda -1.

## <a name="remarks"></a>Açıklamalar

**_putenv** işlevi yeni ortam değişkenleri ekler veya varolan ortam değişkenlerinin değerlerini değiştirir. Ortam değişkenleri, bir işlemin yürütüldettiği ortamı tanımlar (örneğin, kitaplıkların bir programa bağlanması için varsayılan arama yolu). **_wputenv** **_putenv**geniş karakterli bir versiyonudur; **_wputenv** için *envstring* bağımsız değişken geniş karakterli bir dizedir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

*Envstring* bağımsız değişkenform *varname*=*value_string*bir dize için bir işaretçi olmalıdır , *varname* eklenecek veya değiştirilecek ortam değişkeninin adı ve *value_string* değişkenin değeridir. *Varname* zaten ortamın bir parçasıysa, değeri *value_string*ile değiştirilir; aksi takdirde, yeni *varname* değişkeni ve *value_string* değeri ortama eklenir. Boş bir *value_string*belirterek veya başka bir deyişle, yalnızca *varname*=' belirterek bir değişkeni ortamdan kaldırabilirsiniz.

**_putenv** ve **_wputenv** yalnızca geçerli sürecin yerel ortamını etkiler; komut düzeyi ortamını değiştirmek için kullanamazsınız. Diğer bir tarihte, bu işlevler yalnızca çalışma zamanı kitaplığı için erişilebilen veri yapılarında çalışır, işletim sistemi tarafından bir işlem için oluşturulan ortam segmentinde değil. Geçerli işlem sona erdiğinde, ortam arama işleminin düzeyine (çoğu durumda işletim sistemi düzeyi) geri döner. Ancak, değiştirilen ortam **_spawn**tarafından oluşturulan herhangi bir yeni süreçlere geçirilebilir , **_exec**, veya **sistem**, ve bu yeni süreçler **_putenv** ve **_wputenv**tarafından eklenen herhangi bir yeni öğeler olsun.

Bir ortam girişini doğrudan değiştirmeyin: bunun yerine, değiştirmek için **_putenv** veya **_wputenv** kullanın. Özellikle, **_environ[]** genel dizinin doğrudan serbest öğeleri geçersiz belleğin ele alınmasına neden olabilir.

**getenv** ve **_putenv** çevre tablosuna erişmek için küresel değişken **_environ** kullanırlar; **_wgetenv** ve **_wputenv** **_wenviron**kullanın. **_putenv** ve **_wputenv** **_environ** ve **_wenviron**değerini değiştirebilir, böylece **_envp** bağımsız değişkeni **ana** ve **_wenvp** bağımsız **değişkenwmain**geçersiz . Bu nedenle, ortam bilgilerine erişmek için **_environ** veya **_wenviron** kullanmak daha güvenlidir. **_putenv** ve **_wputenv** küresel değişkenlerle ilişkisi hakkında daha fazla bilgi için bkz. [_environ, _wenviron.](../../c-runtime-library/environ-wenviron.md)

> [!NOTE]
> Fonksiyonların **_putenv** ve **_getenv** aileleri iş parçacığı açısından güvenli değildir. **_getenv,** **_putenv** dizeyi değiştirerek rasgele hatalara neden olurken bir dize işaretçisi döndürebilir. Bu işlevlere yapılan çağrıların eşitlendirildiğinden emin olun.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_putenv**|\<stdlib.h>|
|**_wputenv**|\<stdlib.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

**_putenv**nasıl kullanılacağına bir örnek için [getenv, _wgetenv.](getenv-wgetenv.md)

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
