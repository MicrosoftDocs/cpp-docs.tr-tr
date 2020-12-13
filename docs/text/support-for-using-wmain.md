---
description: 'Hakkında daha fazla bilgi edinin: wmain kullanma desteği'
title: wmain Kullanma Desteği
ms.date: 11/04/2016
f1_keywords:
- wWinMain
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
ms.openlocfilehash: b6a954ab62c9bc675bd2b71275d615b3ee4c1376
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335740"
---
# <a name="support-for-using-wmain"></a>wmain Kullanma Desteği

Visual C++, bir **wmain** işlevi tanımlamayı ve Unicode uygulamanıza geniş karakterli bağımsız değişkenleri geçirmeyi destekler. Benzer bir biçim kullanarak **wmain**'e biçimsel parametreler bildirirsiniz `main` . Daha sonra geniş karakterli bağımsız değişkenleri ve isteğe bağlı olarak programa geniş karakterli bir ortam işaretçisini geçirebilirsiniz. `argv` `envp` **Wmain** için ve parametreleri türündedir `wchar_t*` . Örneğin:

```cpp
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

> [!NOTE]
> MFC Unicode uygulamaları `wWinMain` giriş noktası olarak kullanılır. Bu durumda, `CWinApp::m_lpCmdLine` Unicode bir dizedir. `wWinMainCRTStartup` [/Entry](../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneğiyle ayarladığınızdan emin olun.

Programınız bir **ana** işlev kullanıyorsa, çok baytlı karakter ortamı program başlangıcında çalışma zamanı kitaplığı tarafından oluşturulur. Ortamın geniş karakterli bir kopyası yalnızca gerektiğinde oluşturulur (örneğin, veya işlevlerine yapılan bir çağrı ile `_wgetenv` `_wputenv` ). İçin ilk çağrıda `_wputenv` veya `_wgetenv` bir MBCS ortamı zaten varsa, buna karşılık gelen bir geniş karakterli dize ortamı oluşturulur. Daha sonra ortam, `_wenviron` genel değişkenin geniş karakterli bir sürümü olan genel değişken tarafından işaret edilir `_environ` . Bu noktada, ortamın iki kopyası (MBCS ve Unicode) aynı anda mevcuttur ve programın ömrü boyunca çalışma zamanı sistemi tarafından korunur.

Benzer şekilde, programınız bir **wmain** işlevi kullanıyorsa, program başlangıcında geniş karakterli bir ortam oluşturulur ve genel değişken tarafından işaret edilir `_wenviron` . Bir MBCS (ASCII) ortamı, veya için yapılan ilk çağrıda oluşturulur `_putenv` `getenv` ve genel değişken tarafından işaret edilir `_environ` .

## <a name="see-also"></a>Ayrıca bkz.

[Unicode desteği](../text/support-for-unicode.md)<br/>
[Unicode Programlama Özeti](../text/unicode-programming-summary.md)<br/>
[WinMain Işlevi](/windows/win32/api/winbase/nf-winbase-winmain)
