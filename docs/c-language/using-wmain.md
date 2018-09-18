---
title: Wmain kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- wmain function
ms.assetid: d0300812-adc4-40c6-bba3-b2da25468c80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9dbf0f06c20e45282adef6321c459b228285d91b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016448"
---
# <a name="using-wmain"></a>wmain Kullanma

**Microsoft'a özgü**

Unicode programlama modelinde, bir geniş karakter sürümünü tanımlayabilirsiniz **ana** işlevi. Kullanım **wmain** yerine **ana** Unicode programlama modeli için uyar taşınabilir kod yazmak istiyorsanız.

## <a name="syntax"></a>Sözdizimi

```
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

## <a name="remarks"></a>Açıklamalar

Biçimsel parametre bildirirsiniz **wmain** için benzer bir biçimde kullanarak **ana**. Ardından, geniş karakter bağımsız değişkenlerini ve isteğe bağlı olarak bir geniş karakter ortamında işaretçi programa geçirebilirsiniz. `argv` Ve `envp` parametreleri **wmain** türü `wchar_t*`. Örneğin:

Programınızı kullanıyorsa bir **ana** işlevi çok baytlı karakterli ortam program başlangıcında çalışma zamanı kitaplığı tarafından oluşturulur. Ortamın geniş karakterli kopyası yalnızca gerektiğinde oluşturulur (örneğin, bir çağrı tarafından `_wgetenv` veya `_wputenv` işlevler). Bir MBCS ortamı zaten varsa, `_wputenv` veya `_wgetenv` için yapılan ilk çağrıda karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve ardından `_wenviron` genel değişkeninin geniş karakterli bir sürümü olan `_environ` genel değişkeni tarafından gösterilir. Bu noktada, ortamın iki kopyası (MBCS ve Unicode) aynı anda var olur ve program ömrü boyunca işletim sistemi tarafından korunur.

Benzer şekilde, programınız kullanıyorsa bir **wmain** işlevi, bir geniş karakter ortamında program başlangıcında oluşturulur ve tarafından işaret edilen `_wenviron` genel değişkeni. İlk çağrıda bir MBCS (ASCII) ortamı oluşturulur `_putenv` veya `getenv`ve tarafından işaret edilen `_environ` genel değişkeni.

MBCS ortamı hakkında daha fazla bilgi için bkz. [uluslararası duruma getirme](../c-runtime-library/internationalization.md) içinde *çalışma zamanı kitaplığı başvurusu.*

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)