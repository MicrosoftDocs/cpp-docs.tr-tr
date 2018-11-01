---
title: Kayan Nokta Değerlerinin Yetersiz Kalması
ms.date: 11/04/2016
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
ms.openlocfilehash: cd4aadc5ab006b79a43e31348fa101d40e8ca03a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477369"
---
# <a name="underflow-of-floating-point-values"></a>Kayan Nokta Değerlerinin Yetersiz Kalması

**ANSI 4.5.1** matematik işlevlerinin tamsayı ifadesini ayarlanmasına `errno` makro değerini `ERANGE` üzerinde yetersiz aralık hatalarında

Bir kayan nokta yetersizliği `errno` ifadesini `ERANGE` olarak ayarlamaz. Bir değer sıfıra yaklaştığında ve en sonunda yetersiz kaldığında, değer sıfır olarak ayarlanır.

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)