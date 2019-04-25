---
title: Satır İçi Derlemede Tür ve Değişken Boyutları
ms.date: 08/30/2018
ms.topic: reference
f1_keywords:
- length
- Type
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
ms.openlocfilehash: 36c97ee866ca449e9bbcf514e464a13f24f12cd9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166899"
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>Satır İçi Derlemede Tür ve Değişken Boyutları

**Microsoft'a özgü**

**UZUNLUĞU**, **BOYUTU**, ve **türü** operatörleri, satır içi derlemede sınırlı bir anlama sahiptir. İle tüm kullanılamaz `DUP` işleci (MASM yönergeleri veya işleçleri verilerle tanımlanamaz için). Ancak, C veya C++ değişkenleri veya türleri boyutunu bulmak için kullanabilirsiniz:

- **UZUNLUĞU** işleci, bir dizideki öğelerin sayısını döndürebilir. Dizi olmayan değişkenleri için 1 değerini döndürür.

- **BOYUTU** işleci, bir C veya C++ değişkeni döndürebilir. Bir değişkenin boyutu ürünüdür kendi **UZUNLUĞU** ve **türü**.

- **Türü** işleci, bir C veya C++ tür veya değişken boyutunu döndürebilir. Değişken bir dizi ise **türü** tek bir öğe dizinin boyutunu döndürür.

Örneğin, programınız bir 8-öğe varsa **int** dizisi

```cpp
int arr[8];
```

Aşağıdaki C ve derleme ifadeler boyutunu yield `arr` ve alt öğeleri.

|__asm|C|Boyut|
|-------------|-------|----------|
|**UZUNLUĞU** arr|`sizeof`(arr) /`sizeof`(arr[0])|8|
|**BOYUTU** arr|`sizeof`(arr)|32|
|**TÜR** arr|`sizeof`(arr[0])|4|

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>