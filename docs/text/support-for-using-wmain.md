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
ms.openlocfilehash: 4af389c00f6065df631f891dadcb0b2f350f984d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491195"
---
# <a name="support-for-using-wmain"></a>wmain Kullanma Desteği

Visual C++ , bir **wmain** işlevi tanımlamayı ve Unicode uygulamanıza geniş karakterli bağımsız değişkenleri geçirmeyi destekler. Benzer`main`bir biçim kullanarak **wmain**'e biçimsel parametreler bildirirsiniz. Daha sonra geniş karakterli bağımsız değişkenleri ve isteğe bağlı olarak programa geniş karakterli bir ortam işaretçisini geçirebilirsiniz. **Wmain** `wchar_t*`için `envp`veparametreleritüründedir `argv` . Örneğin:

```cpp
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )
```

> [!NOTE]
> MFC Unicode uygulamaları giriş `wWinMain` noktası olarak kullanılır. Bu durumda, `CWinApp::m_lpCmdLine` Unicode bir dizedir. [/Entry](../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneğiyle `wWinMainCRTStartup` ayarladığınızdan emin olun.

Programınız bir **ana** işlev kullanıyorsa, çok baytlı karakter ortamı program başlangıcında çalışma zamanı kitaplığı tarafından oluşturulur. Ortamın geniş karakterli bir kopyası yalnızca gerektiğinde oluşturulur (örneğin, `_wgetenv` veya `_wputenv` işlevlerine yapılan bir çağrı ile). İçin `_wputenv`ilk çağrıda veya `_wgetenv` bir MBCS ortamı zaten varsa, buna karşılık gelen bir geniş karakterli dize ortamı oluşturulur. Daha sonra ortam, `_wenviron` `_environ` genel değişkenin geniş karakterli bir sürümü olan genel değişken tarafından işaret edilir. Bu noktada, ortamın iki kopyası (MBCS ve Unicode) aynı anda mevcuttur ve programın ömrü boyunca çalışma zamanı sistemi tarafından korunur.

Benzer şekilde, programınız bir **wmain** işlevi kullanıyorsa, program başlangıcında geniş karakterli bir ortam oluşturulur ve `_wenviron` genel değişken tarafından işaret edilir. Bir MBCS (ASCII) ortamı, veya `_putenv` `getenv` için yapılan ilk çağrıda oluşturulur ve `_environ` genel değişken tarafından işaret edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Unicode Desteği](../text/support-for-unicode.md)<br/>
[Unicode Programlama Özeti](../text/unicode-programming-summary.md)<br/>
[WinMain Işlevi](/windows/win32/api/winbase/nf-winbase-winmain)
