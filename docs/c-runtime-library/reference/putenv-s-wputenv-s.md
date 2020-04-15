---
title: _putenv_s, _wputenv_s
ms.date: 4/2/2020
api_name:
- _wputenv_s
- _putenv_s
- _o__putenv_s
- _o__wputenv_s
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
- putenv_s
- wputenv_s
- _wputenv_s
- _putenv_s
helpviewer_keywords:
- wputenv_s function
- _putenv_s function
- environment variables, deleting
- putenv_s function
- _wputenv_s function
- environment variables, creating
- environment variables, modifying
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
ms.openlocfilehash: f0164feed05b409ba29ca713f11f4f3323dbaac3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338396"
---
# <a name="_putenv_s-_wputenv_s"></a>_putenv_s, _wputenv_s

Ortam değişkenleri oluşturur, değiştirir veya kaldırır. Bunlar _putenv [sürümleri, _wputenv,](putenv-wputenv.md) ancak [CRT Güvenlik Özellikleri](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleri var.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _putenv_s(
   const char *varname,
   const char *value_string
);
errno_t _wputenv_s(
   const wchar_t *varname,
   const wchar_t *value_string
);
```

### <a name="parameters"></a>Parametreler

*Varname*<br/>
Çevre değişken adı.

*value_string*<br/>
Ortam değişkenini ayarlamak için değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 veya hata kodu verir.

### <a name="error-conditions"></a>Hata Koşulları

|*Varname*|*value_string*|Döndürülen değer|
|------------|-------------|------------------|
|**Null**|herhangi bir|**Eınval**|
|herhangi bir|**Null**|**Eınval**|

Hata koşullarından biri oluşursa, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre işleyicisi çağırır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** döndürün ve **EINVAL** **için errno** ayarlayın.

## <a name="remarks"></a>Açıklamalar

**_putenv_s** işlevi yeni ortam değişkenleri ekler veya varolan ortam değişkenlerinin değerlerini değiştirir. Ortam değişkenleri, bir işlemin yürütüldettiği ortamı tanımlar (örneğin, kitaplıkların bir programa bağlanması için varsayılan arama yolu). **_wputenv_s** **_putenv_s**geniş karakterli bir versiyonudur; **_wputenv_s** *için envstring* bağımsız değişken geniş karakterli bir dizedir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tputenv_s**|**_putenv_s**|**_putenv_s**|**_wputenv_s**|

*varname* eklenecek veya değiştirilecek ortam değişkeninin adıdır ve *value_string* değişkenin değeridir. *Varname* zaten ortamın bir parçasıysa, değeri *value_string*ile değiştirilir; aksi takdirde, yeni *varname* değişkeni ve *value_string* ortama eklenir. *value_string*için boş bir dize (yani "") belirterek bir değişkeni ortamdan kaldırabilirsiniz.

**_putenv_s** ve **_wputenv_s** yalnızca geçerli sürecin yerel ortamını etkiler; komut düzeyi ortamını değiştirmek için kullanamazsınız. Bu işlevler, işletim sisteminin bir işlem için oluşturduğu ortam "segmenti" üzerinde değil, yalnızca çalışma zamanı kitaplığı için erişilebilen veri yapılarında çalışır. Geçerli işlem sona erdiğinde, ortam çoğu durumda işletim sistemi düzeyi olan arama işleminin düzeyine geri döner. Ancak, değiştirilen ortam **_spawn**tarafından oluşturulan herhangi bir yeni süreçlere geçirilebilir , **_exec**, veya **sistem**, ve bu yeni süreçler **_putenv_s** ve **_wputenv_s**tarafından eklenen herhangi bir yeni öğeleri olsun.

Ortam girişini doğrudan değiştirmeyin; bunun yerine, değiştirmek için **_putenv_s** veya **_wputenv_s** kullanın. Özellikle, **_environ[]** genel dizinin öğelerini doğrudan serbest çıkarmak geçersiz belleğin ele alınmasına neden olabilir.

**getenv** ve **_putenv_s** çevre tablosuna erişmek için küresel değişken **_environ** kullanırlar; **_wgetenv** ve **_wputenv_s** **_wenviron**kullanın. **_putenv_s** ve **_wputenv_s** **_environ** ve **_wenviron**değerini değiştirebilir ve bu nedenle **ana** ve **wmain** **için _wenvp** bağımsız değişken *envp* bağımsız değişkenini geçersiz kılabilir. Bu nedenle, ortam bilgilerine erişmek için **_environ** veya **_wenviron** kullanmak daha güvenlidir. **_putenv_s** ve **_wputenv_s** küresel değişkenlerle ilişkisi hakkında daha fazla bilgi için [_environ, _wenviron.](../../c-runtime-library/environ-wenviron.md)

> [!NOTE]
> Işlevlerin **_putenv_s** ve **_getenv_s** aileleri iş parçacığı için güvenli değildir. **_putenv_s** dizeyi değiştirirken **_getenv_s** bir dize işaretçisi döndürebilir ve bu nedenle rasgele hatalara neden olabilir. Bu işlevlere yapılan çağrıların eşitlendirildiğinden emin olun.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_putenv_s**|\<stdlib.h>|
|**_wputenv_s**|\<stdlib.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

**_putenv_s**nasıl kullanılacağını gösteren bir örnek için [bkz. getenv_s, _wgetenv_s.](getenv-s-wgetenv-s.md)

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
