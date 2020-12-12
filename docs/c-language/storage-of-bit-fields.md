---
description: 'Daha fazla bilgi edinin: bit alanları depolaması'
title: Bit Alanları Deposu
ms.date: 11/04/2016
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
ms.openlocfilehash: 43066fe648bc380a8278168f336ebcf10cbbbdf5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205310"
---
# <a name="storage-of-bit-fields"></a>Bit Alanları Deposu

**ANSI 3.5.2.1 &** Bir int içindeki bit alanlarının ayrılma sırası

Bit alanları, bir tamsayı içinde en az önemli olan bitten en önemli bite doğru ayrılır. Aşağıdaki kodda

```
struct mybitfields
{
   unsigned a : 4;
   unsigned b : 5;
   unsigned c : 7;
} test;

int main( void )
{
   test.a = 2;
   test.b = 31;
   test.c = 0;
}
```

bitler aşağıdaki gibi düzenlenir:

```
00000001 11110010
cccccccb bbbbaaaa
```

80x86 işlemcileri tamsayı değerlerinin düşük baytını yüksek bayttan önce depoladığı için yukarıdaki 0x01F2 tamsayısı, fiziksel bellekte arkasından 0x01 gelen 0xF2 olarak depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, birleşimler, numaralandırmalar ve bit alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)
