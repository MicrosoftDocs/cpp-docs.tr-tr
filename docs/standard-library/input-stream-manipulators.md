---
title: Giriş Akış Manipülatörleri
ms.date: 11/04/2016
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
ms.openlocfilehash: d9a6f00f1b5a52d4d388ace376676b45547bdd49
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451023"
---
# <a name="input-stream-manipulators"></a>Giriş Akış Manipülatörleri

[Setprecision](../standard-library/iomanip-functions.md#setprecision)gibi birçok işleyici, `ios` sınıfı için tanımlanır ve bu nedenle giriş akışları için geçerlidir. Ancak, bazı düzenlemeler, aslında giriş akışı nesnelerini etkiler. Bu uygulamalardan en önemlileri `dec` `oct`, giriş akışındaki sayılarla kullanılan dönüştürme temelini belirleyen,, ve `hex`.

Ayıklama sırasında, `hex` işleme çeşitli giriş biçimlerinin işlenmesini mümkün bir şekilde sunar. Örneğin, c, C, 0xC, 0xC, 0Xc ve 0XC, ondalık tamsayı 12 olarak yorumlanır. 0 ile 9 arasındaki herhangi bir karakter, A-F, a-f, x ve X, sayısal dönüştürmeyi sonlandırır. Bu nedenle, `"124n5"` [basic_ios:: Fail](../standard-library/basic-ios-class.md#fail) bit set ile sıra 124 numaralı sayıya dönüştürülür.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)
