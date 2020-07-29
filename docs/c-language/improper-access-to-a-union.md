---
title: Birleşime Düzgün Olmayan Erişim
ms.date: 11/04/2016
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
ms.openlocfilehash: 5a804ed80c8f1ac2f5dd9a24f12c67e96e199b6b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227835"
---
# <a name="improper-access-to-a-union"></a>Birleşime Düzgün Olmayan Erişim

**ANSI 3.3.2.3** Bir UNION nesnesinin üyesine, farklı türde bir üye kullanılarak erişilir

İki tür birleşimi bildirilirse ve bir değer depolanıyorsa, ancak birleşime diğer türle erişildiğinde sonuçlar güvenilir değildir.

Örneğin, **`float`** ve birleşimi **`int`** bildirilmiştir. Bir **`float`** değer depolanır, ancak program daha sonra değerine bir olarak erişir **`int`** . Böyle bir durumda, değer, değerlerin iç depolamasına bağlıdır **`float`** . Tamsayı değeri güvenilir değil.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, birleşimler, numaralandırmalar ve bit alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)
