---
title: _putenv_s, _wputenv_s
ms.date: 11/04/2016
api_name:
- _wputenv_s
- _putenv_s
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
ms.openlocfilehash: b2de609314a12f626a21680b470bc8831eada2cb
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949898"
---
# <a name="_putenv_s-_wputenv_s"></a>_putenv_s, _wputenv_s

Ortam değişkenlerini oluşturur, değiştirir veya kaldırır. Bunlar, [_putenv, _wputenv](putenv-wputenv.md) 'nin SÜRÜMLERIDIR ancak [CRT içindeki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri içerir.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*varname*<br/>
Ortam değişkeni adı.

*value_string*<br/>
Ortam değişkenini ayarlanacak değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa 0 veya bir hata kodu döndürür.

### <a name="error-conditions"></a>Hata koşulları

|*varname*|*value_string*|Dönüş değeri|
|------------|-------------|------------------|
|**DEĞER**|Kaydedilmemiş|**EINVAL**|
|Kaydedilmemiş|**DEĞER**|**EINVAL**|

Hata koşullarından biri oluşursa, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **EINVAL** döndürür ve **errno** , **EINVAL**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**_Putenv_s** işlevi yeni ortam değişkenleri ekler veya var olan ortam değişkenlerinin değerlerini değiştirir. Ortam değişkenleri bir işlemin yürütüldüğü ortamı tanımlar (örneğin, kitaplıklar için varsayılan arama yolu, bir program ile bağlantılandırılır). **_wputenv_s** , **_putenv_s**öğesinin geniş karakterli bir sürümüdür; **_wputenv_s** için *envstring* bağımsız değişkeni geniş karakterli bir dizedir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tputenv_s**|**_putenv_s**|**_putenv_s**|**_wputenv_s**|

*varname* , eklenecek veya değiştirilecek ortam değişkeninin adıdır ve *value_string* değişkenin değeridir. *Varname* zaten ortamın parçasıysa, değeri *value_string*ile değiştirilmiştir; Aksi halde, yeni *varname* değişkeni ve onun *value_string* ortama eklenir. *Value_string*için boş bir dize ("") belirterek ortamdan bir değişkeni kaldırabilirsiniz.

**_putenv_s** ve **_wputenv_s** yalnızca geçerli işlem için yerel olan ortamı etkiler; komut düzeyi ortamı değiştirmek için bunları kullanamazsınız. Bu işlevler, işletim sisteminin bir işlem için oluşturduğu "segment" ortamında değil, yalnızca çalışma zamanı kitaplığı için erişilebilen veri yapıları üzerinde çalışır. Geçerli işlem sonlandırıldığında, ortam çağrı işlemi düzeyine döner, bu da çoğu durumda işletim sistemi düzeyidir. Ancak, değiştirilen ortam **_üretilemedi**, **_exec**veya **System**tarafından oluşturulan yeni işlemlere geçirilebilir ve bu yeni süreçler **_putenv_s** ve **_wputenv_s**tarafından eklenen yeni öğeleri alır.

Ortam girişini doğrudan değiştirmeyin; Bunun yerine, bunu değiştirmek için **_putenv_s** veya **_wputenv_s** kullanın. Özellikle, **_environ []** genel dizisinin öğeleri doğrudan boşaltılırken geçersiz belleğin giderilmesi neden olabilir.

**getenv** ve **_putenv_s** , ortam tablosuna erişmek için **_environ** genel değişkenini kullanır; **_wgetenv** ve **_wputenv_s** Use **_wenviron**. **_putenv_s** ve **_wputenv_s** , **_environ** ve **_wenviron**değerini değiştirebilir ve bu nedenle, **ana** ve **_wenvp** bağımsız değişkenine **wmain**için *envp* bağımsız değişkenini geçersiz kılar. Bu nedenle, ortam bilgilerine erişmek için **_environ** veya **_wenviron** kullanmak daha güvenlidir. **_Putenv_s** ve **_wputenv_s** ile genel değişkenlere arasındaki ilişki hakkında daha fazla bilgi için bkz. [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv_s** ve **_getenv_s** aileleri işlevleri iş parçacığı açısından güvenli değildir. **_getenv_s** , **_putenv_s** dizeyi değiştirirken bir dize işaretçisi döndürebilir ve bu nedenle rastgele hatalara neden olur. Bu işlevlere yapılan çağrıların eşitlendiğinden emin olun.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_putenv_s**|\<Stdlib. h >|
|**_wputenv_s**|\<Stdlib. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

**_Putenv_s**'in nasıl kullanılacağını gösteren bir örnek için bkz. [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
