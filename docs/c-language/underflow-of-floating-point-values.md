---
description: 'Daha fazla bilgi edinin: Floating-Point değerlerinin yetersiz kalması'
title: Kayan Nokta Değerlerinin Yetersiz Kalması
ms.date: 11/04/2016
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
ms.openlocfilehash: 3d8ddd665aa33e1c47f9f187f759058501bc5484
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321303"
---
# <a name="underflow-of-floating-point-values"></a>Kayan Nokta Değerlerinin Yetersiz Kalması

**ANSI 4.5.1** Matematik işlevlerinin tamsayı ifadesini, `errno` `ERANGE` yetersiz Aralık hatalarında makro değerine ayarlayıp ayarlayamayacağı

Bir kayan nokta yetersizliği `errno` ifadesini `ERANGE` olarak ayarlamaz. Bir değer sıfıra yaklaştığında ve en sonunda yetersiz kaldığında, değer sıfır olarak ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık Işlevleri](../c-language/library-functions.md)
