---
title: wmain Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- wmain function
ms.assetid: d0300812-adc4-40c6-bba3-b2da25468c80
ms.openlocfilehash: d467d50a7188cd665f64de8b6f0ce6e6a37df752
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62290826"
---
# <a name="using-wmain"></a>wmain Kullanma

**Microsoft'a Özgü**

Unicode programlama modelinde, **ana** işlevin geniş karakterli bir sürümünü tanımlayabilirsiniz. Unicode programlama modeline bağlı taşınabilir kod yazmak istiyorsanız **Main** yerine **wmain** kullanın.

## <a name="syntax"></a>Sözdizimi

```
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

## <a name="remarks"></a>Açıklamalar

**Ana**için benzer bir biçim kullanarak, biçimsel parametreleri **wmain** 'e bildirebilirsiniz. Daha sonra geniş karakterli bağımsız değişkenleri ve isteğe bağlı olarak programa geniş karakterli bir ortam işaretçisini geçirebilirsiniz. `argv` **Wmain** için ve `wchar_t*` `envp` parametreleri türündedir. Örneğin:

Programınız bir **ana** işlev kullanıyorsa, çok baytlı karakter ortamı program başlangıcında çalışma zamanı kitaplığı tarafından oluşturulur. Ortamın geniş karakterli bir kopyası yalnızca gerektiğinde oluşturulur (örneğin, `_wgetenv` veya `_wputenv` işlevlerine yapılan bir çağrı ile). Bir MBCS ortamı zaten varsa, `_wputenv` veya `_wgetenv` için yapılan ilk çağrıda karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve ardından `_wenviron` genel değişkeninin geniş karakterli bir sürümü olan `_environ` genel değişkeni tarafından gösterilir. Bu noktada, ortamın iki kopyası (MBCS ve Unicode) aynı anda var olur ve program ömrü boyunca işletim sistemi tarafından korunur.

Benzer şekilde, programınız bir **wmain** işlevi kullanıyorsa, program başlangıcında geniş karakterli bir ortam oluşturulur ve `_wenviron` genel değişken tarafından işaret edilir. Bir MBCS (ASCII) ortamı, veya `_putenv` `getenv`için yapılan ilk çağrıda oluşturulur ve `_environ` genel değişken tarafından işaret edilir.

MBCS ortamı hakkında daha fazla bilgi için bkz *. çalışma zamanı kitaplık başvurusunda* [Uluslararası duruma getirme](../c-runtime-library/internationalization.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)
