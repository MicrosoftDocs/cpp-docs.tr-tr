---
description: Giriş/çıkış alternatifleri hakkında daha fazla bilgi edinin
title: Input-Output alternatifleri
ms.date: 05/07/2019
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
ms.openlocfilehash: a6df022dd38bc23eaaaad49620067aca408b2df2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324008"
---
# <a name="inputoutput-alternatives"></a>Giriş/Çıkış Seçenekleri

Microsoft C++ derleyicisi, g/ç programlama için birkaç seçenek sunar:

- C çalışma zamanı kitaplığı doğrudan, arabelleğe alınmamış g/ç.

- ANSI C çalışma zamanı kitaplığı akış g/ç.

- Konsol ve bağlantı noktası doğrudan g/ç.

- Microsoft Foundation Class Kitaplığı.

- Microsoft C++ Standart Kitaplığı.

İostream sınıfları, arabelleğe alınmış, biçimli metin g/ç için yararlıdır. Ayrıca, bir C++ programlama arabirimine ihtiyacınız varsa veya Microsoft Foundation Class (MFC) kitaplığı 'nı kullanmamaya karar verirseniz, arabelleğe alınmamış veya ikili g/ç için de kullanışlıdır. İostream sınıfları, C çalışma zamanı işlevlerine nesne odaklı bir g/ç alternatifi.

İostream sınıflarını Microsoft Windows işletim sistemi ile birlikte kullanabilirsiniz. Dize ve dosya akışları kısıtlama olmadan çalışır, ancak karakter modu akış nesneleri,, `cin` `cout` `cerr` ve `clog` Windows grafik kullanıcı arabirimiyle tutarsız. Ayrıca, Windows ortamıyla doğrudan etkileşimde bulunan özel akış sınıfları da türetebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Akışın ne olduğu](../standard-library/what-a-stream-is.md)
