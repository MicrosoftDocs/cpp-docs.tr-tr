---
description: 'Hakkında daha fazla bilgi edinin: _environ _wenviron'
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
ms.openlocfilehash: e1a69bec6fa93373c74e1f73de469bc3b93158e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305058"
---
# <a name="_environ-_wenviron"></a>_environ, _wenviron

`_environ`Değişken, işlem ortamını oluşturan çok baytlı karakter dizelerine yönelik işaretçiler dizisinin bir işaretçisidir. Bu genel değişken, genel değişken yerine kullanılması gereken [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md) ve [_putenv_s _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)daha güvenli işlevsel sürümler için kullanımdan kaldırılmıştır. `_environ` , Stdlib. h içinde bildirilmiştir.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```
extern char **_environ;
```

## <a name="remarks"></a>Açıklamalar

İşlevini kullanan bir programda `main` , `_environ` işletim sistemi ortamından alınan ayarlara göre program başlangıcında başlatılır. Ortam, formun bir veya daha fazla girdisini içerir

`ENVVARNAME` `=string`

`getenv_s` ve `putenv_s` `_environ` ortam tablosuna erişmek ve değiştirmek için değişkenini kullanın. `_putenv`Ortam ayarlarını eklemek veya silmek için çağrıldığında, ortam tablosunun boyutu değişir. Programın bellek gereksinimlerine bağlı olarak, bellekteki konumu da değişebilir. Değeri `_environ` otomatik olarak uygun şekilde ayarlanır.

`_wenviron`Değişkeni, Stdlib. h 'de şu şekilde bildirilmiştir:

```
extern wchar_t **_wenviron;
```

, öğesinin geniş karakterli bir sürümüdür `_environ` . İşlevini kullanan bir programda `wmain` , `_wenviron` işletim sistemi ortamından alınan ayarlara göre program başlangıcında başlatılır.

Kullanan bir programda `main` , `_wenviron` ortam çok baytlı karakter dizelerinden oluştuğu Için başlangıçta **null** olur. Veya için yapılan ilk çağrıda `_wgetenv` `_wputenv` , karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve tarafından işaret edilir `_wenviron` .

Benzer şekilde, kullanan bir programda `wmain` , `_environ` ortam geniş karakter dizelerinden oluştuğu Için başlangıçta **null** olur. Veya için yapılan ilk çağrıda `_getenv` `_putenv` , karşılık gelen bir çok baytlı karakter dize ortamı oluşturulur ve tarafından işaret edilir `_environ` .

Ortamın iki kopyası (MBCS ve Unicode) bir programda aynı anda mevcut olduğunda, çalışma zamanı sisteminin her iki kopyayı da koruması gerekir, bu da daha yavaş yürütme süresine neden olur. Örneğin, her çağırdığınızda, `_putenv` `_wputenv` iki ortam dizesinin karşılık gelmesi için bir çağrısı de otomatik olarak yürütülür.

> [!CAUTION]
> Nadir örneklerde, çalışma zamanı sistemi hem Unicode sürümü hem de bir çok baytlı sürümü korunurken, bu iki ortam sürümü tam olarak karşıeşleşmeyebilir. Bunun nedeni, benzersiz bir çok baytlı karakter dizesinin benzersiz bir Unicode dizesine eşlenmesine karşın, benzersiz bir Unicode dizesinden çok baytlı karakter dizesine eşlemenin benzersiz olması gerekir. Bu nedenle, iki ayrı Unicode dizesi aynı çok baytlı dizeyle eşlenir.

`_environ` [/Md](../build/reference/md-mt-ld-use-run-time-library.md) veya bağlantı kullanıldığında, Unicode bağlamdaki yoklama anlamsız olur `/MDd` . CRT DLL için, programın türü (geniş veya çok baytlı) bilinmiyor. En olası senaryo olduğu için yalnızca çok baytlı tür oluşturulur.

Aşağıdaki sözde kod, bunun nasıl meydana gelebileceği gösterilmektedir.

```
int i, j;
i = _wputenv( "env_var_x=string1" );  // results in the implicit call:
                                      // putenv ("env_var_z=string1")
j = _wputenv( "env_var_y=string2" );  // also results in implicit call:
                                      // putenv("env_var_z=string2")
```

Bu örnek için kullanılan gösterimde, karakter dizeleri C dize değişmez değerleri değildir; Bunun yerine, çağrı `_wputenv` ve çok baytlı ortam dizelerindeki Unicode ortam dize sabit değerlerini temsil eden yer tutuculardır `putenv` . `x`İki ayrı Unicode ortam dizesinde bulunan ' ' ve ' ' karakter yer tutucuları, `y` geçerli mbcs 'deki karakterlerle benzersiz bir şekilde eşlenmiyor. Bunun yerine, her ikisi de `z` dizeleri dönüştürme denemesinin varsayılan sonucu olan ' ' bazı MBCS karakteriyle eşlenir.

Bu nedenle, çok baytlı ortamda ilk örtük çağrının "" değeri "" `env_var_z` `putenv` olur `string1` , ancak `putenv` " `env_var_z` " değeri "" olarak ayarlandığında, bu değerin üzerine ikinci örtük çağrının üzerine yazılır `string2` . Bu nedenle, Unicode ortamı (ın `_wenviron` ) ve çok baytlı ortamı (' de `_environ` ) Bu çağrı dizisinin ardından farklı olacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Genel değişkenler](../c-runtime-library/global-variables.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)<br/>
[getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)
