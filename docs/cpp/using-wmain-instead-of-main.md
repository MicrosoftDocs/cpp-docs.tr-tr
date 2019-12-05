---
title: main Yerine wmain Kullanma
ms.date: 11/04/2016
f1_keywords:
- wmain
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
ms.openlocfilehash: f47d7219a54b197ec59f109cf08879774b48e6f7
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857222"
---
# <a name="using-wmain-instead-of-main"></a>main Yerine wmain Kullanma

**Microsoft 'a özgü**

Unicode programlama modelinde `main` işlevinin geniş karakterli bir sürümünü tanımlayabilirsiniz. Unicode belirtimine uygun taşınabilir kod yazmak istiyorsanız `main` yerine **wmain** kullanın.

`main`için benzer bir biçim kullanarak, biçimsel parametreleri **wmain** 'e bildirebilirsiniz. Daha sonra geniş karakterli bağımsız değişkenleri ve isteğe bağlı olarak programa geniş karakterli bir ortam işaretçisini geçirebilirsiniz. Bu tür bir **wmain** için *argv* ve *envp* parametreleri `wchar_t*`.

Programınız bir `main` işlevi kullanıyorsa, çok baytlı karakter ortamı, program başlangıcında işletim sistemi tarafından oluşturulur. Ortamın geniş karakterli bir kopyası yalnızca gerektiğinde oluşturulur (örneğin, [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) veya [_wputenv](../c-runtime-library/reference/putenv-wputenv.md) işlevler çağrısıyla). Bir MBCS ortamı zaten varsa, `_wputenv` veya `_wgetenv` için yapılan ilk çağrıda karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve ardından `_wenviron` genel değişkeninin geniş karakterli bir sürümü olan `_environ` genel değişkeni tarafından gösterilir. Bu noktada, ortamın iki kopyası (MBCS ve Unicode) aynı anda var olur ve program ömrü boyunca işletim sistemi tarafından korunur.

Benzer şekilde, programınız bir **wmain** işlevi kullanıyorsa, `_putenv` veya `getenv`yapılan ilk ÇAĞRıDA bir MBCS (ASCII) ortamı oluşturulur ve `_environ` genel değişkeni tarafından gösterilir.

MBCS ortamı hakkında daha fazla bilgi için bkz *. çalışma zamanı kitaplık başvurusunda* [tek baytlı ve çok baytlı karakter kümeleri](../c-runtime-library/single-byte-and-multibyte-character-sets.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[main: Program Başlatma](../cpp/main-program-startup.md)