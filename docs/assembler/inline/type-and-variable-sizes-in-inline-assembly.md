---
description: 'Hakkında daha fazla bilgi edinin: satır Içi derlemede tür ve değişken boyutları'
title: Satır İçi Derlemede Tür ve Değişken Boyutları
ms.date: 08/30/2018
ms.topic: reference
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
ms.openlocfilehash: 0d6822537f542c159c40c0ed6f14dca93aa36525
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122024"
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>Satır İçi Derlemede Tür ve Değişken Boyutları

**Microsoft'a Özgü**

**Uzunluk**, **Boyut** ve **tür** işleçleri satır içi derlemede sınırlı bir anlam taşır. Bunlar `DUP` işleçle birlikte kullanılamaz (Mase yönergeleriyle veya işleçlerle veri tanımlayamadığınız için). Ancak bunları, C veya C++ değişkenlerinin veya türlerinin boyutunu bulmak için kullanabilirsiniz:

- **Length** işleci bir dizideki öğe sayısını döndürebilir. Dizi olmayan değişkenler için 1 değerini döndürür.

- **Size** Işleci bir C veya C++ değişkeninin boyutunu döndürebilir. Değişkenin boyutu, **uzunluğu** ve **türü** ürünüdür.

- **Tür** Işleci bir C veya C++ türü ya da değişkeninin boyutunu döndürebilir. Değişken bir diziyse, **türü** dizideki tek bir öğenin boyutunu döndürür.

Örneğin, programınızın 8 öğeli bir **`int`** dizisi varsa,

```cpp
int arr[8];
```

Aşağıdaki C ve derleme ifadeleri, ve öğelerinin boyutunu verir `arr` .

|__asm|C|Boyut|
|-------------|-------|----------|
|**Uzunluk** ARR|`sizeof(arr)/sizeof(arr[0])`|8|
|**Boyut** ARR|`sizeof(arr)`|32|
|ARR **türü**|`sizeof(arr[0])`|4|

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında derleme dili kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
