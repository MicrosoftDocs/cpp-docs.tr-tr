---
title: /FD (IDE En Az Yeniden Derleme)
ms.date: 04/08/2019
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: 896adcb97a259e6714cf23241424841456371491
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439812"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (IDE En Az Yeniden Derleme)

**/FD** yalnızca bir C++ projenin **Özellik sayfaları** iletişim kutusunun [komut satırı](command-line-property-pages.md) Özellik sayfasında kullanıcılara sunulur. Yalnızca kullanım dışı ve varsayılan olarak kapalı [/Ge (en az yeniden derlemeyi etkinleştir)](gm-enable-minimal-rebuild.md) seçeneği seçili değilse kullanılabilir. **/FD** 'in geliştirme ortamından farklı bir etkisi yoktur. **/FD** `cl /?`çıkışında gösterilmez.

Geliştirme ortamında kullanımdan kaldırılan **/g/** seçeneğini etkinleştirmezseniz, **/FD** kullanılır. **/FD** . IDB dosyasının yeterli bağımlılık bilgisine sahip olmasını sağlar. **/FD** yalnızca geliştirme ortamı tarafından kullanılır ve komut satırından veya bir yapı betiğinden kullanılmamalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
