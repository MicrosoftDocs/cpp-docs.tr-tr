---
description: Daha fazla bilgi edinin:/FD (IDE minimal yeniden oluşturma)
title: /FD (IDE En Az Yeniden Derleme)
ms.date: 04/08/2019
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: d9b2a91c14b80890c703b8f4dd5b2de3aefb012b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192297"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD (IDE En Az Yeniden Derleme)

**/FD** yalnızca bir C++ projesinin **Özellik sayfaları** iletişim kutusunun [komut satırı](command-line-property-pages.md) Özellik sayfasında kullanıcılara sunulur. Yalnızca kullanım dışı ve varsayılan olarak kapalı [/Ge (en az yeniden derlemeyi etkinleştir)](gm-enable-minimal-rebuild.md) seçeneği seçili değilse kullanılabilir. **/FD** 'in geliştirme ortamından farklı bir etkisi yoktur. **/FD** , çıktısında gösterilmez `cl /?` .

Geliştirme ortamında kullanımdan kaldırılan **/g/** seçeneğini etkinleştirmezseniz, **/FD** kullanılır. **/FD** . IDB dosyasının yeterli bağımlılık bilgisine sahip olmasını sağlar. **/FD** yalnızca geliştirme ortamı tarafından kullanılır ve komut satırından veya bir yapı betiğinden kullanılmamalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı dosyası (/F) seçenekleri](output-file-f-options.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
