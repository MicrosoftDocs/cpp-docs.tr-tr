---
description: 'Hakkında daha fazla bilgi edinin: wmain kullanma'
title: wmain Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- wmain function
ms.assetid: d0300812-adc4-40c6-bba3-b2da25468c80
ms.openlocfilehash: 575637700924876ffb3b54a4ea23dc2b62e5feb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198940"
---
# <a name="using-wmain"></a>wmain Kullanma

**Microsoft'a Özgü**

Unicode programlama modelinde, **ana** işlevin geniş karakterli bir sürümünü tanımlayabilirsiniz. Unicode programlama modeline bağlı taşınabilir kod yazmak istiyorsanız **Main** yerine **wmain** kullanın.

## <a name="syntax"></a>Syntax

```
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

## <a name="remarks"></a>Açıklamalar

**Ana** için benzer bir biçim kullanarak, biçimsel parametreleri **wmain** 'e bildirebilirsiniz. Daha sonra geniş karakterli bağımsız değişkenleri ve isteğe bağlı olarak programa geniş karakterli bir ortam işaretçisini geçirebilirsiniz. `argv` `envp` **Wmain** için ve parametreleri türündedir `wchar_t*` . Örneğin:

Programınız bir **ana** işlev kullanıyorsa, çok baytlı karakter ortamı program başlangıcında çalışma zamanı kitaplığı tarafından oluşturulur. Ortamın geniş karakterli bir kopyası yalnızca gerektiğinde oluşturulur (örneğin, veya işlevlerine yapılan bir çağrı ile `_wgetenv` `_wputenv` ). Bir MBCS ortamı zaten varsa, `_wputenv` veya `_wgetenv` için yapılan ilk çağrıda karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve ardından `_wenviron` genel değişkeninin geniş karakterli bir sürümü olan `_environ` genel değişkeni tarafından gösterilir. Bu noktada, ortamın iki kopyası (MBCS ve Unicode) aynı anda var olur ve program ömrü boyunca işletim sistemi tarafından korunur.

Benzer şekilde, programınız bir **wmain** işlevi kullanıyorsa, program başlangıcında geniş karakterli bir ortam oluşturulur ve genel değişken tarafından işaret edilir `_wenviron` . Bir MBCS (ASCII) ortamı, veya için yapılan ilk çağrıda oluşturulur `_putenv` `getenv` ve genel değişken tarafından işaret edilir `_environ` .

MBCS ortamı hakkında daha fazla bilgi için bkz *. çalışma zamanı kitaplık başvurusunda* [Uluslararası duruma getirme](../c-runtime-library/internationalization.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Main Işlevi ve program yürütme](../c-language/main-function-and-program-execution.md)
