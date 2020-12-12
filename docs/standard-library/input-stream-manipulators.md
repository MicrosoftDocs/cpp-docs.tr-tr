---
description: 'Daha fazla bilgi edinin: giriş akışı düzenlemeleri'
title: Giriş Akış Manipülatörleri
ms.date: 11/04/2016
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
ms.openlocfilehash: 3da317a9e01652debe0114cfbde284ec0edf6db3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323995"
---
# <a name="input-stream-manipulators"></a>Giriş Akış Manipülatörleri

[Setprecision](../standard-library/iomanip-functions.md#setprecision)gibi birçok işleyici, sınıfı için tanımlanır `ios` ve bu nedenle giriş akışları için geçerlidir. Ancak, bazı düzenlemeler, aslında giriş akışı nesnelerini etkiler. Bu uygulamalardan en önemlileri, `dec` `oct` `hex` giriş akışındaki sayılarla kullanılan dönüştürme temelini belirleyen,, ve.

Ayıklama sırasında, `hex` işleme çeşitli giriş biçimlerinin işlenmesini mümkün bir şekilde sunar. Örneğin, c, C, 0xC, 0xC, 0Xc ve 0XC, ondalık tamsayı 12 olarak yorumlanır. 0 ile 9 arasındaki herhangi bir karakter, A-F, a-f, x ve X, sayısal dönüştürmeyi sonlandırır. Bu nedenle sıra, `"124n5"` [basic_ios:: Fail](../standard-library/basic-ios-class.md#fail) bit set ile 124 numaralı sayıya dönüştürülür.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş akışları](../standard-library/input-streams.md)
