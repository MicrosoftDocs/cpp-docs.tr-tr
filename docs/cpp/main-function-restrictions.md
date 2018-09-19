---
title: Main işlevi kısıtlamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Main
dev_langs:
- C++
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93f5cce15d4db9f7f6d4e3361d22028fccd676f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117367"
---
# <a name="main-function-restrictions"></a>main İşlevi Kısıtlamaları

Birkaç kısıtlama **ana** başka bir C++ işlevi için geçerli olmayan bir işlev. **Ana** işlevi:

- Aşırı yüklenemez (bkz [işlev aşırı yüklemesi](function-overloading.md)).

- Olarak bildirilemez **satır içi**.

- Olarak bildirilemez **statik**.

- Alınan adresi olamaz.

- Çağrılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[main: Program Başlatma](../cpp/main-program-startup.md)