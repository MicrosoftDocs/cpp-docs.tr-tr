---
title: C++ komut satırı bağımsız değişkenlerini ayrıştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- command line [C++], parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: e634e733-ac2f-4298-abe2-7e9288c94951
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a48e731e714f59a249e5fa689e046e94faf360e6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040225"
---
# <a name="parsing-c-command-line-arguments"></a>C++ Komut Satırı Bağımsız Değişkenlerini Ayrıştırma

**Microsoft'a özgü**

Microsoft C/C++ başlatma kodunu, işletim sistemi komut satırında belirtilen bağımsız değişkenler yorumlarken aşağıdaki kuralları kullanır:

- Bağımsız değişkenler bir boşluk veya sekme olduğu boşluk tarafından ayrılmış.

- İnceltme işareti (^) bir kaçış karakteri veya sınırlayıcı olarak tanınmıyor. Karakter tamamen işletim sistemindeki komut satırı ayrıştırıcı tarafından için iletilmeden önce işlenir `argv` programı dizisi.

- Çift tırnak işareti içine alınmış bir dize ("*dize*") içinde yer alan boşluk bağımsız olarak tek bir bağımsız değişken olarak yorumlanır. Tırnak işaretli dize bağımsız değişkeni eklenebilir.

- Çift tırnak işareti öncesinde bir ters eğik çizgi (\\") bir değişmez değer çift tırnak işareti karakteri (") yorumlanır.

- Ters eğik çizgi, başka bir deyişle, bunlar hemen çift tırnak işareti koyun sürece yorumlanır.

- Çift tırnak işareti ters eğik çizgi sayıda izlediyseniz, bir ters eğik çizgi yerleştirildi `argv` dizisi için her çift ters eğik çizgi ve çift tırnak işareti, dize ayırıcı olarak yorumlanır.

- Çift tırnak işareti ters eğik çizgi tek sayıda izlediyseniz, bir ters eğik çizgi yerleştirildi `argv` dizisi için her çift ters eğik çizgi ve çift tırnak işareti "kaçış" değişmez değer çift tırnak işareti neden kalan eğik (" ) yerleştirileceği `argv`.

## <a name="example"></a>Örnek

Aşağıdaki program nasıl komut satırı bağımsız değişkenlerini gösterir geçirilir:

```cpp
// command_line_arguments.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
int main( int argc,      // Number of strings in array argv
          char *argv[],   // Array of command-line argument strings
          char *envp[] )  // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    cout << "\nCommand-line arguments:\n";
    for( count = 0; count < argc; count++ )
         cout << "  argv[" << count << "]   "
                << argv[count] << "\n";
}
```

Aşağıdaki tabloda örnek giriş ve yukarıdaki listede yer alan kurallara gösteren beklenen çıktıyı gösterir.

### <a name="results-of-parsing-command-lines"></a>Komut satırları ayrıştırma sonuçlarını

|Komut satırı girişi|argv [1]|argv [2]|argv [3]|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[main: Program Başlatma](../cpp/main-program-startup.md)