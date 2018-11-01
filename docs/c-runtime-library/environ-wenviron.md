---
title: _environ, _wenviron
ms.date: 11/04/2016
f1_keywords:
- environ
- wenviron
- _wenviron
- _environ
helpviewer_keywords:
- environ function
- _environ function
- _wenviron function
- process environment
- wenviron function
ms.assetid: 7e639962-6536-47cd-8095-0cbe44a56e03
ms.openlocfilehash: 5982aa367aa043dbe7a5c41128c3646f520d3b4a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666914"
---
# <a name="environ-wenviron"></a>_environ, _wenviron

`_environ` Değişken bir dizi işlem ortamını oluşturan bir çok baytlı karakter dizelerine işaretçidir. Bu genel değişkeni daha güvenli işlevsel sürümleri için kullanım dışı [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md) ve [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md), hangi kullanılmalıdır genel değişken yerine. `_environ` Stdlıb.h içinde bildirilir.

> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```
extern char **_environ;
```

## <a name="remarks"></a>Açıklamalar

Kullanan bir programda `main` işlevi `_environ` program başlangıcında işletim sistemi ortamından yapılan ayarlara göre başlatılır. Ortamı bir veya daha fazla form girişlerinden oluşur

`ENVVARNAME``=string`

`getenv_s` ve `putenv_s` kullanın `_environ` erişmek ve ortam tablosuna değiştirmek için değişken. Zaman `_putenv` ekleme veya silme ortam ayarları için çağrılan ortam tablosuna boyutunu değiştirir. Bellek konumunda de, programın bellek gereksinimlerine bağlı olarak değişebilir. Değerini `_environ` otomatik olarak uygun şekilde ayarlanır.

`_wenviron` Değişken bildirimi Stdlıb.h içinde:

```
extern wchar_t **_wenviron;
```

geniş karakterli sürümüdür `_environ`. Kullanan bir programda `wmain` işlevi `_wenviron` program başlangıcında işletim sistemi ortamından yapılan ayarlara göre başlatılır.

Kullanan bir programda `main`, `_wenviron` başlangıçta **NULL** çünkü ortam çok baytlı karakter dizeleri kümesinden oluşur. Yapılan ilk çağrıda `_wgetenv` veya `_wputenv`, karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve tarafından işaret edilen `_wenviron`.

Benzer şekilde, kullanan bir programda `wmain`, `_environ` başlangıçta **NULL** çünkü ortam geniş karakter dizeleri kümesinden oluşur. Yapılan ilk çağrıda `_getenv` veya `_putenv`, karşılık gelen bir çok baytlı karakterli dize ortamı oluşturulur ve tarafından işaret edilen `_environ`.

Ortam (MBCS ve Unicode) iki kopyasını aynı anda bir programda varsa, çalışma zamanı sistemi daha yavaş yürütme süresi bunun sonucunda, her iki kopyasında sürdürmeniz gerekir. Örneğin, her çağırmanız `_putenv`, çağrı `_wputenv` böylece iki ortam dizeleri karşılık da otomatik olarak yürütülür.

> [!CAUTION]
>  Çalışma zamanı sistemi, hem Unicode sürümü hem de çok baytlı bir sürüm ortamının muhafaza ederken nadir durumlarda, bu iki ortam sürümleri tam olarak karşılık gelmeyebilir. Benzersiz bir çok baytlı karakterli dize benzersiz bir Unicode dizesini eşleştirir ancak bir çok baytlı karakter dizesi benzersiz bir Unicode dize eşleme mutlaka benzersiz olmadığından budur. Bu nedenle, iki ayrı Unicode dizelerini aynı çoklu bayt dizesini eşleyebilir.

Yoklama `_environ` Unicode olarak ne zaman anlamsız bağlamıdır [/MD](../build/reference/md-mt-ld-use-run-time-library.md) veya `/MDd` bağlantı kullanılır. CRT DLL için program türünü (geniş veya çok baytlı) bilinmiyor. En olası senaryo olduğundan, yalnızca çok baytlı türü oluşturulur.

Aşağıdaki sözde kod nasıl oluşabilir gösterir.

```
int i, j;
i = _wputenv( "env_var_x=string1" );  // results in the implicit call:
                                      // putenv ("env_var_z=string1")
j = _wputenv( "env_var_y=string2" );  // also results in implicit call:
                                      // putenv("env_var_z=string2")
```

Bu örnek için kullanılan gösteriminde oluşturan karakter dizelerine C dize değişmez değerleri değildir; ' deki Unicode ortam dize değişmez değerleri temsil eden yer tutucular yerine, oldukları `_wputenv` dizeleri arama ve çok baytlı bir ortam içinde `putenv` çağırın. Karakter tutucuları`x`'ve'`y`' iki ayrı Unicode olarak Ortam dizeleri benzersiz olarak geçerli MBCS karakter eşlemeyin. Bunun yerine, her ikisi de bazı MBCS karakter eşleyin '`z`' diğer bir deyişle denemesi dizeleri dönüştürmek için varsayılan sonucu.

Bu nedenle, ortamda çok baytlı değerini "`env_var_z`" ilk örtük çağrısından sonra `putenv` olacaktır "`string1`", ancak bu değer, ikinci örtük çağrısında belirttikleri `putenv`, değeri "`env_var_z`" olan ayarlamak "`string2`". Unicode ortam (içinde `_wenviron`) ve çok baytlı ortamı (içinde `_environ`) bu nedenle bu dizi çağrıları izleyerek farklı.

## <a name="see-also"></a>Ayrıca Bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)<br/>
[getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)