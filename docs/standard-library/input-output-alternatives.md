---
title: Giriş-çıkış alternatifleri
ms.date: 05/07/2019
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
ms.openlocfilehash: b46ff242fc263be5069eb691dd0ea9e8fb00b0f9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455299"
---
# <a name="inputoutput-alternatives"></a>Giriş/Çıkış Seçenekleri

Microsoft C++ derleyicisi g/ç programlama için birkaç seçenek sunar:

- C çalışma zamanı kitaplığı doğrudan, arabelleğe alınmamış g/ç.

- ANSI C çalışma zamanı kitaplığı akış g/ç.

- Konsol ve bağlantı noktası doğrudan g/ç.

- Microsoft Foundation Class Kitaplığı.

- Microsoft C++ standart kitaplığı.

İostream sınıfları, arabelleğe alınmış, biçimli metin g/ç için yararlıdır. Ayrıca, bir C++ programlama arabirimine ihtiyacınız varsa veya Microsoft Foundation Class (MFC) kitaplığı 'nı kullanmamaya karar verirseniz, arabelleğe alınmamış veya ikili g/ç için de kullanışlıdır. İostream sınıfları, C çalışma zamanı işlevlerine nesne odaklı bir g/ç alternatifi.

İostream sınıflarını Microsoft Windows işletim sistemi ile birlikte kullanabilirsiniz. Dize ve dosya akışları kısıtlama olmadan çalışır, ancak karakter modu `cin`akış nesneleri `cerr`, `cout`, ve `clog` Windows grafik kullanıcı arabirimiyle tutarsız. Ayrıca, Windows ortamıyla doğrudan etkileşimde bulunan özel akış sınıfları da türetebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Akışın Ne Olduğu](../standard-library/what-a-stream-is.md)
