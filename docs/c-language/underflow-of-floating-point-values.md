---
title: Kayan nokta değerlerinin yetersiz kalması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 980000932c8cc4a6be3798976d273dae8608324f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089170"
---
# <a name="underflow-of-floating-point-values"></a>Kayan Nokta Değerlerinin Yetersiz Kalması

**ANSI 4.5.1** matematik işlevlerinin tamsayı ifadesini ayarlanmasına `errno` makro değerini `ERANGE` üzerinde yetersiz aralık hatalarında

Bir kayan nokta yetersizliği `errno` ifadesini `ERANGE` olarak ayarlamaz. Bir değer sıfıra yaklaştığında ve en sonunda yetersiz kaldığında, değer sıfır olarak ayarlanır.

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)