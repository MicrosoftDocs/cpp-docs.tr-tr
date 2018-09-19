---
title: Bit alanları deposu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c39fa4455cfdc387ab5aa2068c80494a4a8810ef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020100"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Birleşimler, Numaralandırmalar ve Bit Alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)