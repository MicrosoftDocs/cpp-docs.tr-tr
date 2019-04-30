---
title: Giriş Akış Manipülatörleri
ms.date: 11/04/2016
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
ms.openlocfilehash: 17f18aa127b84538229b3cf4e4246dfefb6c1f98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404916"
---
# <a name="input-stream-manipulators"></a>Giriş Akış Manipülatörleri

Birçok manipülatörleri gibi [setprecision](../standard-library/iomanip-functions.md#setprecision), tanımlanmış `ios` sınıfı ve bu nedenle giriş akışları uygulanır. Ancak, birkaç manipülatörleri Giriş akışı nesneleri gerçekten etkiler. Yapan, en önemli taban manipülatörleri olanlardır `dec`, `oct`, ve `hex`, giriş akışından sayılarla kullanılan temel dönüşümü belirler.

Ayıklama üzerinde `hex` işleyici çeşitli giriş biçimleri işlenmesini sağlar. Örneğin, c, C, 0xc, 0xC 0Xc ve 0XC tüm yorumlanır ondalık tamsayı 12. Herhangi bir karakter dışında 0-9, A-F, a ile f, x ve X sayısal dönüştürme sonlandırır. Bu nedenle dizisi `"124n5"` numarasıyla 124 dönüştürülür [basic_ios::fail](../standard-library/basic-ios-class.md#fail) biti ayarlanmamış.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)<br/>
