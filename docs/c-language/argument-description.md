---
title: Bağımsız Değişken Tanımı
ms.date: 11/04/2016
helpviewer_keywords:
- envp argument
- main function, syntax
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 91c2cbe3-9aca-4277-afa1-6137eb8fb704
ms.openlocfilehash: 88d477c874d62800c47bb03220246cb3f0999724
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492514"
---
# <a name="argument-description"></a>Bağımsız Değişken Tanımı

**Main ve** **wmain** işlevlerindeki parametresi,komutsatırındanprogramakaçtanebağımsızdeğişkengeçtiğinibelirtenbir`argc` tamsayıdır. Program adı bir bağımsız değişken olarak değerlendirildiğinden, değeri `argc` en az bir olur.

## <a name="remarks"></a>Açıklamalar

`argv` Parametresi, program bağımsız değişkenlerini temsil eden, null ile sonlandırılmış dizelerin işaretçilerinden oluşan bir dizidir. Dizideki her öğe, **Main** (veya **wmain**) öğesine geçirilen bir bağımsız değişkenin dize gösterimine işaret eder. (Diziler hakkında bilgi için bkz. [dizi bildirimleri](../c-language/array-declarations.md).) Parametresi `argv` ,`char **argv`Type `char` (`char *argv[]`) işaretçilerinden oluşan bir dizi olarak ya da Type `char` () işaretçilerine işaretçi olarak belirtilebilir. **Wmain**için `argv` parametresi, Type `wchar_t` (`wchar_t *argv[]`) işaretçilerinden oluşan bir dizi olarak ya da Type `wchar_t` (`wchar_t **argv`) işaretçilerine işaretçi olarak belirtilebilir.

Kural olarak, `argv` **[0]** programın çağrıldığı komuttur.  Ancak, [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw) kullanarak bir işlem oluşturulabilir ve hem`lpApplicationName` birinci hem de ikinci bağımsız değişkenleri (ve `lpCommandLine`) kullanırsanız, `argv` **[0]** yürütülebilir ad olmayabilir; [GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) kullanın yürütülebilir adı alın.

Son işaretçi (`argv[argc]`) **null**. (Ortam değişkeni bilgilerini almak için alternatif bir yöntem için *çalışma zamanı kitaplık başvurusunda* bkz. [getenv](../c-runtime-library/reference/getenv-wgetenv.md) .)

**Microsoft 'a özgü**

`envp` Parametresi, kullanıcının ortam değişkenlerinde ayarlanan değerleri temsil eden bir null sonlandırılmış dizeler dizisinin bir işaretçisidir. Parametresi `envp` `char` , (`char *envp[]``char **envp` )işaretçilerindenoluşanbirdiziolarakveya(`char` ) işaretçilerin bir işaretçisi olarak belirtilebilir. **Wmain** `envp` işlevinde,`wchar_t **envp`parametresi `wchar_t` (`wchar_t *envp[]`) işaretçilerinden oluşan bir dizi veya `wchar_t` () işaretçilerin bir işaretçisi olarak belirtilebilir. Dizinin sonu, **null** \*işaretçiyle belirtilir. **Ana** veya **wmain** 'e geçirilen ortam bloğunun, geçerli ortamın "dondurulmuş" bir kopyası olduğunu unutmayın. Daha sonra ortamı _**putenv** `_wputenv`veya çağrısı yoluyla değiştirirseniz, geçerli ortam (ve `_environ` veya `_wenviron` değişkenleri tarafından `getenv` / `_wgetenv` döndürülen) değişir, ancak tarafından `envp` işaret edilen blok değişmeyecektir. Parametresi, C 'de ANSI uyumludur, ancak içinde C++değildir. `envp`

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)
