---
title: Wmain kullanma desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- wWinMain
dev_langs:
- C++
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 390f2a11b98a851b5f33b4e0a941a515421d5836
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011623"
---
# <a name="support-for-using-wmain"></a>wmain Kullanma Desteği
Visual C++ destekler tanımlayan bir **wmain** işlevi ve Unicode uygulamanızı geniş karakter bağımsız değişkenleri geçirme. Biçimsel parametre bildirirsiniz **wmain**, benzer bir biçimde kullanarak `main`. Ardından, geniş karakter bağımsız değişkenlerini ve isteğe bağlı olarak bir geniş karakter ortamında işaretçi programa geçirebilirsiniz. `argv` Ve `envp` parametreleri **wmain** türü `wchar_t*`. Örneğin:  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  MFC Unicode uygulamaları `wWinMain` giriş noktası olarak. Bu durumda, `CWinApp::m_lpCmdLine` bir UNICODE dizesi. Ayarladığınızdan emin olun `wWinMainCRTStartup` ile [/Entry](../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneği.  
  
 Programınızı kullanıyorsa bir `main` işlevi çok baytlı karakterli ortam program başlangıcında çalışma zamanı kitaplığı tarafından oluşturulur. Ortamın geniş karakterli kopyası yalnızca gerektiğinde oluşturulur (örneğin, bir çağrı tarafından `_wgetenv` veya `_wputenv` işlevler). Yapılan ilk çağrıda `_wputenv`, veya yapılan ilk çağrıda `_wgetenv` bir MBCS ortamı zaten varsa, karşılık gelen bir geniş karakterli dize ortamı oluşturulur. Ortam ardından tarafından işaret edilen `_wenviron` genel değişkeninin geniş karakterli sürümüdür, `_environ` genel değişkeni. Bu noktada, ortamın (MBCS ve Unicode) iki kopyasını aynı anda mevcut ve program ömrü boyunca çalışma zamanı sistemi tarafından korunur.  
  
 Benzer şekilde, programınız kullanıyorsa bir **wmain** işlevi, bir geniş karakter ortamında program başlangıcında oluşturulur ve tarafından işaret edilen `_wenviron` genel değişkeni. İlk çağrıda bir MBCS (ASCII) ortamı oluşturulur `_putenv` veya `getenv` ve tarafından işaret edilen `_environ` genel değişkeni.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Unicode desteği](../text/support-for-unicode.md)   
 [Unicode Programlama Özeti](../text/unicode-programming-summary.md)   
 [WinMain işlevi](http://msdn.microsoft.com/library/windows/desktop/ms633559)