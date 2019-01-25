---
title: wmain Kullanma Desteği
ms.date: 11/04/2016
f1_keywords:
- wWinMain
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
ms.openlocfilehash: 4ef970174a56361fdbd2102f363b4849ad4af9f3
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54894191"
---
# <a name="support-for-using-wmain"></a>wmain Kullanma Desteği

Visual C++ destekler tanımlayan bir **wmain** işlevi ve Unicode uygulamanızı geniş karakter bağımsız değişkenleri geçirme. Biçimsel parametre bildirirsiniz **wmain**, benzer bir biçimde kullanarak `main`. Ardından, geniş karakter bağımsız değişkenlerini ve isteğe bağlı olarak bir geniş karakter ortamında işaretçi programa geçirebilirsiniz. `argv` Ve `envp` parametreleri **wmain** türü `wchar_t*`. Örneğin:

```cpp
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

> [!NOTE]
> MFC Unicode uygulamaları `wWinMain` giriş noktası olarak. Bu durumda, `CWinApp::m_lpCmdLine` bir UNICODE dizesi. Ayarladığınızdan emin olun `wWinMainCRTStartup` ile [/Entry](../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneği.

Programınızı kullanıyorsa bir **ana** işlevi çok baytlı karakterli ortam program başlangıcında çalışma zamanı kitaplığı tarafından oluşturulur. Ortamın geniş karakterli kopyası yalnızca gerektiğinde oluşturulur (örneğin, bir çağrı tarafından `_wgetenv` veya `_wputenv` işlevler). Yapılan ilk çağrıda `_wputenv`, veya yapılan ilk çağrıda `_wgetenv` bir MBCS ortamı zaten varsa, karşılık gelen bir geniş karakterli dize ortamı oluşturulur. Ortam ardından tarafından işaret edilen `_wenviron` genel değişkeninin geniş karakterli sürümüdür, `_environ` genel değişkeni. Bu noktada, ortamın (MBCS ve Unicode) iki kopyasını aynı anda mevcut ve program ömrü boyunca çalışma zamanı sistemi tarafından korunur.

Benzer şekilde, programınız kullanıyorsa bir **wmain** işlevi, bir geniş karakter ortamında program başlangıcında oluşturulur ve tarafından işaret edilen `_wenviron` genel değişkeni. İlk çağrıda bir MBCS (ASCII) ortamı oluşturulur `_putenv` veya `getenv` ve tarafından işaret edilen `_environ` genel değişkeni.

## <a name="see-also"></a>Ayrıca Bkz.

[Unicode Desteği](../text/support-for-unicode.md)<br/>
[Unicode Programlama Özeti](../text/unicode-programming-summary.md)<br/>
[WinMain işlevi](/windows/desktop/api/winbase/nf-winbase-winmain)