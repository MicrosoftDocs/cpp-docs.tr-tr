---
title: C Komut Satırı Bağımsız Değişkenlerini Ayrıştırma
ms.date: 11/04/2016
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- command line, parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: ffce8037-2811-45c4-8db4-1ed787859c80
ms.openlocfilehash: ace6d1b8295d0901ef22f3c354b32ad17e296e87
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75299097"
---
# <a name="parsing-c-command-line-arguments"></a>C Komut Satırı Bağımsız Değişkenlerini Ayrıştırma

**Microsoft'a Özgü**

Microsoft C başlangıç kodu, işletim sistemi komut satırında verilen bağımsız değişkenleri yorumlarken aşağıdaki kuralları kullanır:

- Bağımsız değişkenler boşluk veya sekme olan boşluk ile sınırlandırılmıştır.

- Çift tırnak işareti içine alınmış bir dize, içinde yer alan boşluk ne olursa olsun tek bir bağımsız değişken olarak yorumlanır. Tırnak içine alınmış bir dize bir bağımsız değişkene gömülebilir. Şapka işareti (**^**) bir kaçış karakteri veya sınırlayıcı olarak tanınmadığını unutmayın.

- Önünde ters eğik çizgi **"** ** \\**olan bir çift tırnak işareti ("), sabit değer çift tırnak işareti (") olarak yorumlanır.

- Ters eğik çizgiler, bir çift tırnak işaretinden hemen önce gelmedikleri takdirde tam olarak yorumlanır.

- Çift sayıda ters eğik çizgiden sonra çift tırnak işareti varsa, bir ters eğik**\\**çizgi () her çift eğik çizgi ( `argv` **\\**) için diziye yerleştirilir ve çift tırnak işareti (**"**) dize sınırlayıcısı olarak yorumlanır.

- Tek bir ters eğik çizgiden sonra çift tırnak işareti varsa, her ters**\\**eğik çizgi ( `argv` **\\**) için diziye bir ters eğik çizgi () konur ve çift tırnak işareti kalan ters eğik çizgi tarafından bir kaçış sırası olarak yorumlanır ve bir sabit değer çift tırnak işareti (**"**) konur. `argv`

Bu liste, komut satırı bağımsız değişkenlerinin çeşitli örnekleri `argv` için geçirilen yorumlanan sonucu göstererek yukarıdaki kuralları gösterir. İkinci, üçüncü ve dördüncü sütunlarda listelenen çıktı, bağımsız değişkenleri. Listeyi izleyen C programı.

|Komut satırı girişi|argv [1]|argv [2]|argv [3]|
|-------------------------|---------------|---------------|---------------|
|`"a b c" d e`|`a b c`|`d`|`e`|
|`"ab\"c" "\\" d`|`ab"c`|`\`|`d`|
|`a\\\b d"e f"g h`|`a\\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```c
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

Bu programdan alınan bir çıkış örneği şunlardır:

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)
