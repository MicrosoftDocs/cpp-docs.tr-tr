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
ms.openlocfilehash: c8b82b9f13da1b7c4884001fed5afce832147714
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856494"
---
# <a name="support-for-using-wmain"></a>wmain Kullanma Desteği
Visual C++ destekler tanımlayan bir **wmain** işlevi ve Unicode uygulamanıza joker karakter bağımsız değişkenleri geçirme. Biçimsel parametresi bildirme **wmain**, benzer bir biçimde kullanarak **ana**. Ardından, joker karakter bağımsız değişkenlerini ve isteğe bağlı olarak bir joker karakter ortamı işaretçisi program geçirebilirsiniz. `argv` Ve `envp` parametreleri **wmain** türü `wchar_t*`. Örneğin:  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  MFC Unicode uygulamaları **wWinMain** giriş noktası olarak. Bu durumda, `CWinApp::m_lpCmdLine` bir UNICODE dizesi. Ayarladığınızdan emin olun **wWinMainCRTStartup** ile [/Entry](../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneği.  
  
 Programınızı kullanıyorsa, bir **ana** işlevi, çok baytlı karakter ortamı program başlatma sırasında çalışma zamanı kitaplığı tarafından oluşturulur. Ortam geniş karakter kopyası yalnızca gerekli olduğunda oluşturulur (örneğin, bir çağrı tarafından `_wgetenv` veya `_wputenv` işlevleri). İlk çağrıda `_wputenv`, ya da ilk çağrıda `_wgetenv` MBCS ortam zaten varsa, karşılık gelen bir joker karakter dizesi ortam oluşturulur. Ortam sonra işaret ediyor `_wenviron` bir joker karakter sürümü genel değişkeni, `_environ` genel değişkeni. Bu noktada, iki kopyasını ortam (MBCS ve Unicode) aynı anda mevcut ve program ömrü boyunca çalışma zamanı sistemi tarafından korunur.  
  
 Benzer şekilde, program kullanıyorsa, bir **wmain** işlevi, bir joker karakter ortamı program başlangıcında oluşturulur ve işaret ediyor `_wenviron` genel değişkeni. MBCS (ASCII) ortamı ilk çağrıda oluşturulur `_putenv` veya `getenv` ve işaret ediyor `_environ` genel değişkeni.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Unicode desteği](../text/support-for-unicode.md)   
 [Unicode Programlama Özeti](../text/unicode-programming-summary.md)   
 [WinMain işlevi](http://msdn.microsoft.com/library/windows/desktop/ms633559)