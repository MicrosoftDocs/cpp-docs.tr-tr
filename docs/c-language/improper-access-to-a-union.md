---
title: Birleşime Düzgün Olmayan Erişim
ms.date: 11/04/2016
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
ms.openlocfilehash: 9fd7bdc753f6359a8760e58813f9009411c1bf44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326137"
---
# <a name="improper-access-to-a-union"></a>Birleşime Düzgün Olmayan Erişim

**ANSI 3.3.2.3** Bir UNION nesnesinin üyesine, farklı türde bir üye kullanılarak erişilir

İki tür birleşimi bildirilirse ve bir değer depolanıyorsa, ancak birleşime diğer türle erişildiğinde sonuçlar güvenilir değildir.

Örneğin, **float** birleşimi ve `int` olarak bildirilmiştir. Bir **float** değeri depolanır, ancak program daha sonra değerine bir `int`olarak erişir. Böyle bir durumda, değer **float** değerlerinin iç depolamasına bağlıdır. Tamsayı değeri güvenilir değil.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Birleşimler, Numaralandırmalar ve Bit Alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)
