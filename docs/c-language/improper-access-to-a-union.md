---
description: 'Hakkında daha fazla bilgi edinin: bir birleşime hatalı erişim'
title: Birleşime Düzgün Olmayan Erişim
ms.date: 11/04/2016
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
ms.openlocfilehash: edff4d74e4e31b505e8c6b71555358fcd4b7e070
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182118"
---
# <a name="improper-access-to-a-union"></a>Birleşime Düzgün Olmayan Erişim

**ANSI 3.3.2.3** Bir UNION nesnesinin üyesine, farklı türde bir üye kullanılarak erişilir

İki tür birleşimi bildirilirse ve bir değer depolanıyorsa, ancak birleşime diğer türle erişildiğinde sonuçlar güvenilir değildir.

Örneğin, **`float`** ve birleşimi **`int`** bildirilmiştir. Bir **`float`** değer depolanır, ancak program daha sonra değerine bir olarak erişir **`int`** . Böyle bir durumda, değer, değerlerin iç depolamasına bağlıdır **`float`** . Tamsayı değeri güvenilir değil.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, birleşimler, numaralandırmalar ve bit alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)
