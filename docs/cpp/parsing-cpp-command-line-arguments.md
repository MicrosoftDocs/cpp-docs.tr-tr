---
title: "C++ komut satırı bağımsız değişkenlerini ayrıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58db951b2c9459eb9511e0a354e1daec4b29b53d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="parsing-c-command-line-arguments"></a>C++ Komut Satırı Bağımsız Değişkenlerini Ayrıştırma
**Microsoft özel**  
  
 Microsoft C/C++ başlangıç kod, işletim sistemi komut satırında belirtilen bağımsız değişkenler yorumlanırken aşağıdaki kuralları kullanır:  
  
-   Bağımsız değişkenler, bir boşluk veya bir sekme olduğu boşluk tarafından sınırlandırılır.  
  
-   Şapka (^) karakteri kaçış karakteri veya sınırlayıcı tanınmıyor. Karakter tamamen tarafından işletim sisteminde komut satırı ayrıştırıcı için iletilmeden önce işlenir `argv` program dizisinde.  
  
-   Çift tırnak işaretleri bir dize ("*dize*") içinde yer alan boşluk bakılmaksızın tek bir bağımsız değişken olarak yorumlanır. Tırnak içine alınan bir dizeyi bir bağımsız değişken katıştırılabilir.  
  
-   Çift tırnak işareti eğik çizgi işaretinden (\\") değişmez değer çift tırnak işareti karakteri (") olarak yorumlanır.  
  
-   Bunlar hemen çift tırnak işareti koyun sürece ters eğik çizgi tam anlamıyla, yorumlanır.  
  
-   Ters eğik çizgi çift sayıda çift tırnak işareti izlediyseniz, bir ters eğik çizgi yerleştirilir `argv` dizi her çift ters eğik çizgi ve çift tırnak işareti dize ayırıcı olarak yorumlanır.  
  
-   Ters eğik çizgi tek sayıda çift tırnak işareti izlediyseniz, bir ters eğik çizgi yerleştirilir `argv` dizi her çift ters eğik çizgi ve çift tırnak işareti "kaçış" değişmez değer çift tırnak işareti neden kalan eğik (" ) yerleştirileceği `argv`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki programı nasıl komut satırı bağımsız değişkenleri gösterir geçirilir:  
  
```  
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
  
 Aşağıdaki tabloda, örnek giriş ve yukarıdaki listede kuralları gösteren beklenen çıkış gösterir.  
  
### <a name="results-of-parsing-command-lines"></a>Komut satırları ayrıştırma sonuçları  
  
|Komut satırı girişi|argv [1]|argv [2]|argv [3]|  
|-------------------------|---------------|---------------|---------------|  
|`"abc" d e`|`abc`|`d`|`e`|  
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|  
|`a\\\"b c d`|`a\"b`|`c`|`d`|  
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [main: Program Başlatma](../cpp/main-program-startup.md)