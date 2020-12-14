---
description: 'Hakkında daha fazla bilgi edinin: _putenv _wputenv'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 117250553eba7b2c8c1249140b610dc064e6b1fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258609"
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

**_Putenv** işlevi yeni ortam değişkenleri ekler veya var olan ortam değişkenlerinin değerlerini değiştirir. Ortam değişkenleri bir işlemin yürütüldüğü ortamı tanımlar (örneğin, kitaplıklar için varsayılan arama yolu, bir program ile bağlantılandırılır). **_wputenv** , **_putenv** geniş karakterli bir sürümüdür; **_wputenv** için *envstring* bağımsız değişkeni, geniş karakterli bir dizedir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

*Envstring* bağımsız değişkeni, *varname* value_string biçimindeki bir dizenin işaretçisi olmalıdır = ; burada *varname* eklenecek veya değiştirilecek ortam değişkeninin adıdır ve değişkenin değeri *value_string* . *Varname* zaten ortamın parçasıysa, değeri *value_string* ile değiştirilmiştir; Aksi takdirde, yeni *varname* değişkeni ve *value_string* değeri ortama eklenir. Yalnızca *varname*= belirterek boş bir *value_string* veya başka bir deyişle, ortamdan bir değişkeni kaldırabilirsiniz.

**_putenv** ve **_wputenv** yalnızca geçerli işlem için yerel olan ortamı etkiler; komut düzeyi ortamı değiştirmek için bunları kullanamazsınız. Diğer bir deyişle, bu işlevler yalnızca çalışma zamanı kitaplığı için erişilebilir olan ve işletim sistemi tarafından bir işlem için oluşturulan ortam segmentinde olmayan veri yapıları üzerinde çalışır. Geçerli işlem sonlandırıldığında ortam, çağıran işlemin düzeyine döner (çoğu durumda, işletim sistemi düzeyi). Ancak, değiştirilen ortam **_spawn**, **_exec** veya **sistem** tarafından oluşturulan yeni işlemlere geçirilebilir ve bu yeni süreçler **_putenv** ve **_wputenv** tarafından eklenen yeni öğeleri alır.

Doğrudan bir ortam girdisini değiştirmeyin: bunun yerine **_putenv** veya **_wputenv** kullanın. Özellikle, **_environ []** genel dizisinin doğrudan serbest bırakılmakta olan öğeleri, belirtilen hatalı belleğe yol açabilir.

 {1 & gt; **_putenv** & **_environ** lt; 1}. **_wgetenv** ve **_wputenv** **_wenviron** kullanın. **_putenv** ve **_wputenv** **_environ** ve **_wenviron** değerini değiştirebilir, bu nedenle **_envp** bağımsız değişkenini **Main** ve **_wenvp** bağımsız değişkenine geçersiz kılarak **wmain**. Bu nedenle, ortam bilgilerine erişmek için **_environ** veya **_wenviron** kullanmak daha güvenlidir. **_Putenv** ilişkisi ve genel değişkenlere **_wputenv** hakkında daha fazla bilgi için bkz. [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> İşlevlerin **_putenv** ve **_getenv** aileleri iş parçacığı açısından güvenli değildir. **_getenv** , **_putenv** dizeyi değiştirirken rastgele hatalara neden olan bir dize işaretçisi döndürebilir. Bu işlevlere yapılan çağrıların eşitlendiğinden emin olun.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_putenv**|\<stdlib.h>|
|**_wputenv**|\<stdlib.h> veya \<wchar.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

**_Putenv** kullanmanın bir örneği için bkz. [getenv, _wgetenv](getenv-wgetenv.md).

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
