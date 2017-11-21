---
title: "C komut satırı bağımsız değişkenlerini ayrıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- command line, parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: ffce8037-2811-45c4-8db4-1ed787859c80
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 95369f7554a557677636ea9c70665424e7e80c83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="parsing-c-command-line-arguments"></a>C Komut Satırı Bağımsız Değişkenlerini Ayrıştırma
**Microsoft özel**  
  
 Microsoft C başlangıç kod, işletim sistemi komut satırında belirtilen bağımsız değişkenler yorumlanırken aşağıdaki kuralları kullanır:  
  
-   Bağımsız değişkenler, bir boşluk veya bir sekme olduğu boşluk tarafından sınırlandırılır.  
  
-   Bir dize çift tırnak işaretleri içindeki boşluk bakılmaksızın tek bir bağımsız değişken olarak yorumlanır. Tırnak içine alınan bir dizeyi bir bağımsız değişken katıştırılabilir. Unutmayın şapka (**^**) bir kaçış karakteri veya sınırlayıcı olarak tanınmıyor.  
  
-   Bir ters eğik çizgi çift tırnak işareti  **\\"**, değişmez değer çift tırnak işareti yorumlanır (**"**).  
  
-   Bunlar hemen çift tırnak işareti koyun sürece ters eğik çizgi tam anlamıyla, yorumlanır.  
  
-   Ters eğik çizgi çift sayıda çift tırnak işareti sonra bir ters eğik çizgi izlediyseniz (**\\**) yerleştirilir `argv` dizi her çiftinin ters eğik çizgi ( **\\ \\** ) ve çift tırnak işareti (**"**) dizesi ayırıcı olarak yorumlanır.  
  
-   Ters eğik çizgi tek sayıda çift tırnak işareti sonra bir ters eğik çizgi izlediyseniz (**\\**) yerleştirilir `argv` dizi her çiftinin ters eğik çizgi ( **\\ \\** ) ve çift tırnak işareti değişmez değer çift tırnak işareti neden kalan eğik kaçış dizisi yorumlanır (**"**) yerleştirileceği `argv`.  
  
 Bu liste geçirilen yorumlanan sonuç göstererek yukarıda kuralları gösterir `argv` komut satırı bağımsız değişkenleri bazı örnekleri için. Üçüncü çıkış saniye içinde listelenen ve dördüncü sütun ise bağımsız değişken. Listenin izleyen C programı.  
  
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
 Bu programdan çıktının bir örnek verilmiştir:  
  
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
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Main işlevi ve Program yürütme](../c-language/main-function-and-program-execution.md)