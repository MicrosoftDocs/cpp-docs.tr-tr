---
title: Bit Alanları Deposu
ms.date: 11/04/2016
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
ms.openlocfilehash: 4dbfb3c6ad27fb023881dafde74bb27132959085
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157896"
---
# <a name="storage-of-bit-fields"></a>Bit Alanları Deposu

**ANSI 3.5.2.1** bir tamsayı içindeki bit alanlarının sırası

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

[Yapılar, Birleşimler, Numaralandırmalar ve Bit Alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)
