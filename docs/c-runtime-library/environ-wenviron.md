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
ms.openlocfilehash: 8d67947c93d1387bfdc38c3bae5b3f978024a725
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349373"
---
# <a name="_environ-_wenviron"></a>_environ, _wenviron

Değişken, `_environ` işlem ortamını oluşturan çok bayt karakterli dizeleri işaretçi bir dizi işaretçidir. Bu küresel değişken, küresel değişkenin yerine kullanılması gereken [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md) ve [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)daha güvenli işlevsel versiyonları için amortismana hazırlanmıştır. `_environ`Stdlib.h ilan edilir.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```
extern char **_environ;
```

## <a name="remarks"></a>Açıklamalar

`main` İşlevkullanan bir programda, `_environ` işletim sistemi ortamından alınan ayarlara göre program başlatmada başharfe alınır. Ortam, formun bir veya daha fazla girişinden oluşur

`ENVVARNAME` `=string`

`getenv_s`ve `putenv_s` ortam `_environ` tablosuna erişmek ve değiştirmek için değişkeni kullanın. Ortam `_putenv` ayarları eklemek veya silmek için çağrıldığında, ortam tablosu boyutunu değiştirir. Bellekteki konumu, programın bellek gereksinimlerine bağlı olarak da değişebilir. Değeri `_environ` buna göre otomatik olarak ayarlanır.

`_wenviron` Stdlib.h'de bildirilen değişken:

```
extern wchar_t **_wenviron;
```

'nin `_environ`geniş karakterli bir versiyonudur. `wmain` İşlevkullanan bir programda, `_wenviron` işletim sistemi ortamından alınan ayarlara göre program başlatmada başharfe alınır.

Kullanan bir `main`programda, `_wenviron` ortam çok bayt karakterli dizelerden oluştuğu için başlangıçta **NULL'dur.** İlk çağrıda `_wgetenv` veya `_wputenv`, karşılık gelen geniş karakterli dize ortamı `_wenviron`oluşturulur ve tarafından işaret edilir.

Benzer şekilde, kullanan `wmain`bir `_environ` programda, ortam geniş karakterli dizeleri oluşur, çünkü başlangıçta **NULL'** dur. İlk çağrıda `_getenv` veya `_putenv`, karşılık gelen bir multibayt karakterli dize `_environ`ortamı oluşturulur ve tarafından işaret edilir.

Bir programda ortamın iki kopyası (MBCS ve Unicode) aynı anda varsa, çalışma zamanı sisteminin her iki kopyayı da tutması gerekir ve bu da yürütme süresinin daha yavaş olması gerekir. Örneğin, her aradiğinizde, `_putenv`iki `_wputenv` ortam dizelerinin karşılık gelecek şekilde bir çağrı da otomatik olarak yürütülür.

> [!CAUTION]
> Çalışma zamanı sistemi hem Unicode sürümünü hem de ortamın çok bayt sürümünü korurken, bu iki ortam sürümü tam olarak karşılık sızmayabilir. Bunun nedeni, benzersiz bir çok bayt karakterli dize yle eşlemesine rağmen, benzersiz bir Unicode dizesinden çok bayt karakterli bir dize eşlemenin mutlaka benzersiz olmamasıdır. Bu nedenle, iki farklı Unicode dizeleri aynı çok bayt dize eşleyebilir.

`_environ` [/MD](../build/reference/md-mt-ld-use-run-time-library.md) veya `/MDd` bağlantı kullanıldığında Unicode bağlamında yoklama anlamsızdır. CRT DLL için programın türü (geniş veya çok bayt) bilinmemektedir. Bu en olası senaryo olduğundan yalnızca çok bayt türü oluşturulur.

Aşağıdaki sözde kod bunun nasıl olabileceğini göstermektedir.

```
int i, j;
i = _wputenv( "env_var_x=string1" );  // results in the implicit call:
                                      // putenv ("env_var_z=string1")
j = _wputenv( "env_var_y=string2" );  // also results in implicit call:
                                      // putenv("env_var_z=string2")
```

Bu örnek için kullanılan gösterimde, karakter dizeleri C dizeli literals değildir; bunun yerine, `_wputenv` çağrıdaki Unicode ortamı dizelerini ve `putenv` çağrıdaki çok bayt ortam dizelerini temsil eden yer tutuculardır. İki farklı Unicode ortamı dizelerinde ' '`x`ve ' ' '`y`karakter yer tutucuları, geçerli MBCS'deki karakterlerle benzersiz olarak eşleşmez. Bunun yerine, her iki eş`z`bazı MBCS karakteri ' ' dizeleri dönüştürme girişiminin varsayılan sonucudur.

Böylece, çok bayt lı ortamda ,`env_var_z`" " değeri `putenv` ilk örtülü`string1`çağrıdan sonra " " olacaktır, ancak `putenv`bu değer ikinci`env_var_z`örtük çağrıüzerine`string2`" " değeri " olarak ayarlandığında üzerine yazılır. Unicode ortamı (içinde) `_wenviron`ve çok bayt `_environ`lı ortam (in) bu nedenle bu dizi çağrıyı takip ederek farklılık gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)<br/>
[getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)
