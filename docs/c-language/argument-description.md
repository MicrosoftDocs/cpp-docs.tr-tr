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
ms.openlocfilehash: 71301bd5eedf2806e97b8d24d95beaf2843427ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313537"
---
# <a name="argument-description"></a>Bağımsız Değişken Tanımı

`argc` Parametresinde **ana** ve **wmain** işlevleri, kaç tane bağımsız değişken, komut satırından programa geçirilen belirten bir tamsayı. Program adı değeri bağımsız değişken olarak kabul edilir beri `argc` en az biri.

## <a name="remarks"></a>Açıklamalar

`argv` Parametresi null ile sonlandırılmış dizeler program bağımsız değişkenleri temsil eden işaretçileri dizisidir. Geçirilen her öğe için bir bağımsız değişken bir dize gösterimini dizi noktaları **ana** (veya **wmain**). (Diziler hakkında daha fazla bilgi için bkz: [dizi bildirimleri](../c-language/array-declarations.md).) `argv` Parametre türü işaretçiler dizisi olarak ya da bildirilebilir `char` (`char *argv[]`) veya türü işaretçiler için bir işaretçi olarak `char` (`char **argv`). İçin **wmain**, `argv` parametre türü işaretçiler dizisi olarak ya da bildirilebilir `wchar_t` (`wchar_t *argv[]`) veya türü işaretçiler için bir işaretçi olarak `wchar_t` (`wchar_t **argv`).

Kural olarak, `argv` **[0]** ile programın çağrıldığı komuttur.  Ancak, bunu kullanarak bir işlem oluşturmak mümkündür [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) ve ilk ve ikinci bağımsız kullanıyorsanız (`lpApplicationName` ve `lpCommandLine`), `argv` **[0]** çalışmıyor olabilir yürütülebilir dosya adı; kullanma [GetModuleFileName](/windows/desktop/api/libloaderapi/nf-libloaderapi-getmodulefilenamea) yürütülebilir adını alamadı.

Son işaretçi (`argv[argc]`) olan **NULL**. (Bkz [getenv](../c-runtime-library/reference/getenv-wgetenv.md) içinde *çalışma zamanı kitaplığı başvurusu* ortam değişkeni bilgilerini almak için alternatif bir yöntem için.)

**Microsoft'a özgü**

`envp` Parametresi, bir kullanıcının Ortam değişkenlerinde ayarlanan değerleri temsil eden boş sonlandırılmış dize dizisine bir işaretçi. `envp` Parametresi, bir işaretçiler dizisi olarak bildirilebilir `char` (`char *envp[]`) veya işaretçilerinin işaretçisi olarak `char` (`char **envp`). İçinde bir **wmain** işlevi `envp` parametresi, bir işaretçiler dizisi olarak bildirilebilir `wchar_t` (`wchar_t *envp[]`) veya işaretçilerinin işaretçisi olarak `wchar_t` (`wchar_t **envp`). Dizinin sonuna tarafından belirtilen bir **NULL** \*işaretçi. Öğesine geçirilen ortam bloğu Not **ana** veya **wmain** geçerli ortamın "dondurulmuş" bir kopyasıdır. Daha sonra ortamı _ çağrısıyla değiştirirseniz**putenv** veya `_wputenv`, geçerli ortam (tarafından döndürülen `getenv` / `_wgetenv` ve `_environ` veya `_wenviron` değişkenler) değişir, ancak blok tarafından işaret edilen `envp` değişmez. `envp` ANSI C ancak C++ ' uyumlu bir parametredir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)
