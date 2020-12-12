---
description: 'Daha fazla bilgi edinin: bağımsız değişken açıklaması'
title: Bağımsız Değişken Tanımı
ms.date: 11/04/2016
helpviewer_keywords:
- envp argument
- main function, syntax
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 91c2cbe3-9aca-4277-afa1-6137eb8fb704
ms.openlocfilehash: 97a4bbd8c483f26aa43065cb14a567e1050116d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280203"
---
# <a name="argument-description"></a>Bağımsız Değişken Tanımı

`argc` **Main** ve **wmain** işlevlerindeki parametresi, komut satırından programa kaç tane bağımsız değişken geçtiğini belirten bir tamsayıdır. Program adı bir bağımsız değişken olarak değerlendirildiğinden, değeri `argc` en az bir olur.

## <a name="remarks"></a>Açıklamalar

`argv`Parametresi, program bağımsız değişkenlerini temsil eden, null ile sonlandırılmış dizelerin işaretçilerinden oluşan bir dizidir. Dizideki her öğe, **Main** (veya **wmain**) öğesine geçirilen bir bağımsız değişkenin dize gösterimine işaret eder. (Diziler hakkında bilgi için bkz. [dizi bildirimleri](../c-language/array-declarations.md).) `argv` Parametresi, Type () işaretçilerinden oluşan bir dizi olarak ya da **`char`** `char *argv[]` Type () işaretçilerine işaretçi olarak belirtilebilir **`char`** `char **argv` . **Wmain** için parametresi, `argv` Type () işaretçilerinden oluşan bir dizi olarak **`wchar_t`** `wchar_t *argv[]` ya da Type () işaretçilerine işaretçi olarak belirtilebilir **`wchar_t`** `wchar_t **argv` .

Kural olarak, `argv` **[0]** programın çağrıldığı komuttur.  Ancak, [CreateProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessw) kullanarak bir işlem oluşturulabilir ve hem birinci hem de ikinci bağımsız değişkenleri ( `lpApplicationName` ve `lpCommandLine` ) kullanırsanız, `argv` **[0]** yürütülebilir ad olmayabilir; yürütülebilir adı almak için [GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) kullanın.

Son işaretçi ( `argv[argc]` ) **null**. (Ortam değişkeni bilgilerini almak için alternatif bir yöntem için *çalışma zamanı kitaplık başvurusunda* bkz. [getenv](../c-runtime-library/reference/getenv-wgetenv.md) .)

**Microsoft'a Özgü**

`envp`Parametresi, kullanıcının ortam değişkenlerinde ayarlanan değerleri temsil eden bir null sonlandırılmış dizeler dizisinin bir işaretçisidir. `envp`Parametresi, () işaretçilerinden oluşan bir dizi olarak **`char`** `char *envp[]` veya () işaretçilerin bir işaretçisi olarak belirtilebilir **`char`** `char **envp` . **Wmain** işlevinde, `envp` parametresi () işaretçilerinden oluşan bir dizi **`wchar_t`** `wchar_t *envp[]` veya () işaretçilerin bir işaretçisi olarak belirtilebilir **`wchar_t`** `wchar_t **envp` . Dizinin sonu, **null** \* işaretçiyle belirtilir. **Ana** veya **wmain** 'e geçirilen ortam bloğunun, geçerli ortamın "dondurulmuş" bir kopyası olduğunu unutmayın. Daha sonra ortamı _ **putenv** veya çağrısı yoluyla değiştirirseniz `_wputenv` , geçerli ortam ( `getenv` / `_wgetenv` ve `_environ` veya değişkenleri tarafından döndürülen `_wenviron` ) değişir ancak tarafından işaret edilen blok `envp` değişmez. `envp`Parametresi, C 'de ANSI uyumludur, ancak C++ ' da değildir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Main Işlevi ve program yürütme](../c-language/main-function-and-program-execution.md)
