---
title: C komut satırı bağımsız değişkenlerini ayrıştırma | Microsoft Docs
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
- command line, parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: ffce8037-2811-45c4-8db4-1ed787859c80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c7d4c0a1a5afc7c43b601f048d14b4bc9619b08
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065731"
---
# <a name="parsing-c-command-line-arguments"></a>C Komut Satırı Bağımsız Değişkenlerini Ayrıştırma

**Microsoft'a özgü**

Microsoft C başlatma kodunu, işletim sistemi komut satırında belirtilen bağımsız değişkenler yorumlarken aşağıdaki kuralları kullanır:

- Bağımsız değişkenler bir boşluk veya sekme olduğu boşluk tarafından ayrılmış.

- Çift tırnak işareti içine alınmış bir dize içindeki boşluk bağımsız olarak tek bir bağımsız değişken olarak yorumlanır. Tırnak işaretli dize bağımsız değişkeni eklenebilir. Unutmayın giriş işaretini (**^**) bir kaçış karakteri veya sınırlayıcı olarak tanınmıyor.

- Çift tırnak işareti bir ters eğik çizgi  **\\"**, değişmez değer çift tırnak işareti yorumlanır (**"**).

- Ters eğik çizgi, başka bir deyişle, bunlar hemen çift tırnak işareti koyun sürece yorumlanır.

- Ters eğik çizgi sayıda çift tırnak işareti ve sonra bir ters eğik çizgi izlediyseniz (**\\**) yerleştirildiğinden `argv` dizisi için her çift ters eğik çizgi (**\\ \\**) ve çift tırnak işareti (**"**) dize ayırıcı olarak yorumlanır.

- Ters eğik çizgi tek sayıda çift tırnak işareti ve sonra bir ters eğik çizgi izlediyseniz (**\\**) yerleştirildiğinden `argv` dizisi için her çift ters eğik çizgi (**\\ \\**) ve çift tırnak işareti sabit değeri çift tırnak işareti neden kalan eğik bir kaçış dizisi yorumlanır (**"**) yerleştirileceği `argv`.

Bu liste geçirilen yorumlanan sonucu göstererek kurallarına yukarıda gösterilmiştir `argv` çeşitli örneklerini komut satırı bağımsız değişkenleri için. Üçüncü olarak, çıkış saniye içinde listelenen ve dördüncü sütun ise ARGS. C programında listesini izler.

|Komut satırı girişi|argv [1]|argv [2]|argv [3]|
|-------------------------|---------------|---------------|---------------|
|`"a b c" d e`|`a b c`|`d`|`e`|
|`"ab\"c" "\\" d`|`ab"c`|`\`|`d`|
|`a\\\b d"e f"g h`|`a\\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```
// Parsing_C_Commandline_args.c
// ARGS.C illustrates the following variables used for accessing
// command-line arguments and environment variables:
// argc  argv  envp
//

#include <stdio.h>

int main( int argc, // Number of strings in array argv
char *argv[],      // Array of command-line argument strings
char **envp )      // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    printf_s( "\nCommand-line arguments:\n" );
    for( count = 0; count < argc; count++ )
        printf_s( "  argv[%d]   %s\n", count, argv[count] );

    // Display each environment variable.
    printf_s( "\nEnvironment variables:\n" );
    while( *envp != NULL )
        printf_s( "  %s\n", *(envp++) );

    return;
}
```

## <a name="comments"></a>Açıklamalar

Bu programdan çıktının bir örneği verilmiştir:

```
Command-line arguments:
  argv[0]   C:\MSC\TEST.EXE

Environment variables:
  COMSPEC=C:\NT\SYSTEM32\CMD.EXE

  PATH=c:\nt;c:\binb;c:\binr;c:\nt\system32;c:\word;c:\help;c:\msc;c:\;
  PROMPT=[$p]
  TEMP=c:\tmp
  TMP=c:\tmp
  EDITORS=c:\binr
  WINDIR=c:\nt
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)