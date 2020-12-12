---
description: 'Daha fazla bilgi edinin: tanımlayıcılar (C++)'
title: Tanımlayıcılar (C++)
ms.date: 05/07/2019
helpviewer_keywords:
- decorated names
- decorated names, about decorated names
- identifiers, C++
- white space, in C++ identifiers
- identifiers [C++]
ms.assetid: 03a0dfb1-4530-4cdf-8295-5ea4dca4c1b8
ms.openlocfilehash: 24798675940761eb7a2b8cbdeb6d63592bb4d05a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114019"
---
# <a name="identifiers-c"></a>Tanımlayıcılar (C++)

Tanımlayıcı, aşağıdakilerden birini belirtmek için kullanılan bir karakter dizisidir:

- Nesne veya değişken adı

- Sınıf, yapı veya birleşim adı

- Numaralandırılmış tür adı

- Bir sınıf, yapı, birleşim veya numaralandırma üyesi

- Function veya Class-member işlevi

- TypeDef adı

- Etiket adı

- Makro adı

- Makro parametresi

Aşağıdaki karakterlere, bir tanımlayıcının herhangi bir karakteri olarak izin verilir:

```
_ a b c d e f g h i j k l m
n o p q r s t u v w x y z
A B C D E F G H I J K L M
N O P Q R S T U V W X Y Z
```

Bir tanımlayıcıda evrensel karakter adlarının belirli aralıklarına de izin verilir.  Tanımlayıcıdaki bir evrensel karakter adı bir denetim karakteri veya temel kaynak karakter kümesinde bir karakter belirleyemez. Daha fazla bilgi için bkz. [karakter kümeleri](../cpp/character-sets.md). Bu Unicode kod noktası sayı aralıklarına, Tanımlayıcıdaki herhangi bir karakter için evrensel karakter adları olarak izin verilir:

- 00A8, 00AA, 00AD, 00AF, 00B2-00B5, 00B7-00BA, 00BC-00IN, 00C0-00D6, 00D8-00F6, 00F8-00FF, 0100-02FF, 0370-167F, 1681-180D, 180F-1DBF, 1E00-1FFF, 200B-200D, 202A-202E, 203F-2040, 2054, 2060-206F, 2070-20CF, 2100-218F, 2460-24FF, 2776-2793, 2C00-2DFF, 2E80-2FFF, 3004-3007, 3021-302F, 3031-303F, 3040-D7FF, F900-FD3D, FD40-FDCF, FDF0-FE1F, FE30-FE44, FE47-FFFD, 10000-1FFFD, 20000-2FFFD, 30000-3FFFD, 40000-4FFFD, 50000-5FFFD, 60.000 KARAKTERE-6FFFD, 70000-7FFFD, 80000-8FFFD, 90000-9FFFD, A0000-AFFD, B0000-BFFFD, C0000-CFFFD, D0000-DFFFD, E0000-EFFFD

İlk dışında, Tanımlayıcıdaki herhangi bir karakter olarak aşağıdaki karakterlere izin verilir:

```
0 1 2 3 4 5 6 7 8 9
```

Bu Unicode kod noktası sayı aralıklarına, ilki hariç bir Tanımlayıcıdaki herhangi bir karakter için evrensel karakter adları olarak da izin verilir:

- 0300-036F, 1DC0-1DFF, 20D0-20FF, FE20-FE2F

**Microsoft'a Özgü**

Microsoft C++ tanımlayıcılarının yalnızca ilk 2048 karakteri önemlidir. Kullanıcı tanımlı türlerin adları, tür bilgilerini korumak için derleyici tarafından "tasarlanacaktır". Tür bilgileri de dahil olmak üzere sonuçtaki ad 2048 karakterden daha uzun olamaz. (Daha fazla bilgi için bkz. [düzenlenmiş adlar](../build/reference/decorated-names.md) .) Düzenlenmiş bir tanımlayıcının uzunluğunu etkileyebilecek faktörler şunlardır:

- Tanımlayıcının Kullanıcı tanımlı türdeki bir nesneyi veya Kullanıcı tanımlı bir türden türetilmiş bir türü içerip içermediğini belirtir.

- Tanımlayıcının bir işlevi veya bir işlevden türetilmiş bir türü içerip içermediğini belirtir.

- Bir işlev için bağımsız değişken sayısı.

Dolar işareti, `$` Microsoft C++ derleyicisinde (MSVC) geçerli bir tanımlayıcı karakterdir. MSVC, tanımlayıcılardaki evrensel karakter adları için izin verilen aralıkların gösterdiği gerçek karakterleri kullanmanıza da olanak tanır. Bu karakterleri kullanmak için, dosyaları içeren bir dosya kodlama kod sayfasını kullanarak dosyayı kaydetmelisiniz.  Bu örnek, kodunuzda hem genişletilmiş karakterlerin hem de evrensel karakter adlarının nasıl yerine kullanılabileceğini gösterir.

```cpp
// extended_identifier.cpp
// In Visual Studio, use File, Advanced Save Options to set
// the file encoding to Unicode codepage 1200
struct テスト         // Japanese 'test'
{
    void トスト() {}  // Japanese 'toast'
};

int main() {
    テスト \u30D1\u30F3;  // Japanese パン 'bread' in UCN form
    パン.トスト();        // compiler recognizes UCN or literal form
}
```

Bir tanımlayıcıda izin verilen karakter aralığı, C++/CLı kodu derlenirken daha az kısıtlayıcıdır. /Clr kullanılarak derlenen koddaki tanımlayıcılar  [standart ECMA-335: ortak dil altyapısı (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm)izlemelidir.

**SON Microsoft 'a özgü**

Bir tanımlayıcının ilk karakteri alfabetik bir karakter, büyük harf ya da küçük harf veya alt çizgi ( **_** ) olmalıdır. C++ tanımlayıcıları büyük/küçük harfe duyarlı olduğundan, `fileName` öğesinden farklıdır `FileName` .

Tanımlayıcılar, anahtar sözcüklerle tam olarak aynı yazım ve büyük/küçük harf olamaz. Anahtar sözcükleri içeren tanımlayıcılar geçerlidir. Örneğin, `Pint` bir anahtar sözcük olan olsa da, yasal bir tanımlayıcıdır **`int`** .

Bir tanımlayıcıda iki sıralı alt çizgi karakteri ( **__** ) veya bir büyük harfle izlenen tek başına bir alt çizgi kullanımı, tüm kapsamlardaki C++ uygulamaları için ayrılmıştır. Geçerli veya gelecekteki ayrılmış tanımlayıcılarla olası çakışmalar nedeniyle, dosya kapsamına sahip adlar için bir öndeki alt çizgi ve ardından küçük harfli bir harf kullanmaktan kaçının.

## <a name="see-also"></a>Ayrıca bkz.

[Sözcük temelli kurallar](../cpp/lexical-conventions.md)
