---
title: C Komut Satırı Bağımsız Değişkenlerini Ayrıştırma
description: Microsoft C çalışma zamanı başlatma kodunun, argv ve argc parametrelerini oluşturmak için komut satırı bağımsız değişkenlerini nasıl yorumlayacağını öğrenin.
ms.date: 11/09/2020
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- double quote marks
- command line, parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: ffce8037-2811-45c4-8db4-1ed787859c80
ms.openlocfilehash: 92921e91ee6bb37b2bf7b702a1b31ed045187b59
ms.sourcegitcommit: b38485bb3a9d479e0c5d64ffc3d841fa2c2b366f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441261"
---
# <a name="parsing-c-command-line-arguments"></a>C Komut Satırı Bağımsız Değişkenlerini Ayrıştırma

**Microsoft'a Özgü**

Microsoft C başlangıç kodu, işletim sistemi komut satırında verilen bağımsız değişkenleri yorumlarken aşağıdaki kuralları kullanır:

- Bağımsız değişkenler boşluk veya sekme olan boşluk ile sınırlandırılmıştır.

- İlk bağımsız değişken ( `argv[0]` ) özel olarak değerlendirilir. Program adını temsil eder. Geçerli bir yol adı olması gerektiğinden, çift tırnak işaretleriyle () çevrelenen bölümlere **`"`** izin verilir. Çift tırnak işaretleri çıkışa dahil edilmez `argv[0]` . Çift tırnak işareti içine alınmış parçalar, bağımsız değişkenin sonuna kadar bir boşluk veya sekme karakterinin yorumlanmasını önler. Bu listedeki sonraki kurallar uygulanmaz.

- Çift tırnak işaretleri içine alınmış bir dize, boşluk içerip içermediğini tek bir bağımsız değişken olarak yorumlanır. Tırnak içine alınmış bir dize bir bağımsız değişkene gömülebilir. Şapka işareti ( **`^`** ) bir kaçış karakteri veya sınırlayıcı olarak tanınmıyor. Tırnak içine alınmış bir dize içinde çift tırnak işareti çifti tek bir kaçan çift tırnak işareti olarak yorumlanır. Bir kapanış çift tırnak işareti olmadan önce komut satırı sona erdiğinde, son bağımsız değişken olarak o ana kadar okunan tüm karakterler çıktı olur.

- Önünde ters eğik çizgi () olan bir çift tırnak işareti **`\"`** , sabit bir çift tırnak işareti () olarak yorumlanır **`"`** .

- Ters eğik çizgiler, bir çift tırnak işaretinden hemen önce gelmedikleri takdirde tam olarak yorumlanır.

- İki ters eğik çizgi daha sonra çift tırnak işareti olursa, bir ters eğik çizgi () **`\`** `argv` , her ters eğik çizgi () için diziye yerleştirilir **`\\`** ve çift tırnak işareti ( **`"`** ) bir dize sınırlayıcısı olarak yorumlanır.

- Tek bir ters eğik çizgiden sonra çift tırnak işareti varsa, **`\`** `argv` her ters eğik çizgi () çifti için diziye bir ters eğik çizgi () konur **`\\`** . Çift tırnak işareti, geri kalan ters eğik çizgi tarafından bir kaçış sırası olarak yorumlanır ve değişmez değer çift tırnak işareti ( **`"`** ) konur `argv` .

Bu liste, `argv` komut satırı bağımsız değişkenlerinin çeşitli örnekleri için geçirilen yorumlanan sonucu göstererek yukarıdaki kuralları gösterir. İkinci, üçüncü ve dördüncü sütunlarda listelenen çıktı, bağımsız değişkenleri. Listeyi izleyen C programı.

|Command-Line girişi|argv [1]|argv [2]|argv [3]|
|-------------------------|---------------|---------------|---------------|
|`"a b c" d e`|`a b c`|`d`|`e`|
|`"ab\"c" "\\" d`|`ab"c`|`\`|`d`|
|`a\\\b d"e f"g h`|`a\\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|
|`a"b"" c d`|`ab" c d`|||

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```c
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

## <a name="comments"></a>Yorumlar

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

[Main Işlevi ve program yürütme](../c-language/main-function-and-program-execution.md)
