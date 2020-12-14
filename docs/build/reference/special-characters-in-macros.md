---
description: 'Daha fazla bilgi edinin: makrolardaki özel karakterler'
title: Makrolardaki Özel Karakterler
ms.date: 11/04/2016
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
ms.openlocfilehash: 569aedbc474f660894b723f9356355e2360a4e61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224666"
---
# <a name="special-characters-in-macros"></a>Makrolardaki Özel Karakterler

Tanımdan sonra bir sayı işareti (#) bir açıklama belirler. Makroda bir sabit değer işareti belirtmek için, ^ # gibi bir giriş işareti (^) kullanın.

Dolar işareti ($) makro çağrısını belirtir. Bir sabit değer $ belirtmek için $ $ kullanın.

Bir tanımı yeni bir satıra genişletmek için çizgiyi ters eğik çizgiyle ( \\ ) sonlandırın. Makro çağrıldığında ters eğik çizgi artı yeni satır karakteri bir boşluk ile değiştirilmiştir. Çizginin sonunda sabit bir ters eğik çizgi belirtmek için, önüne bir şapka işareti (^) koyun veya bir açıklama Belirleyicisi (#) ile izleyin.

Sabit bir yeni satır karakteri belirtmek için satırı bir şapka (^) ile sonlandırın, örneğin:

```
CMDS = cls^
dir
```

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE makrosu tanımlama](defining-an-nmake-macro.md)
