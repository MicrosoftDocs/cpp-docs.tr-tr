---
title: Bağımsız değişken tanımları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- envp argument
- main function, arguments
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca012d7b391e011d9658b0b74e0f4433d5dc9fd4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="argument-definitions"></a>Bağımsız Değişken Tanımları
Prototipteki bağımsız değişkenler  
  
```  
  
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);  
```  
  
 bağımsız değişkenlerini komut satırlarıyla kolayca ayrıştırılmasına ve isteğe bağlı olarak ortam değişkenlerine erişime izin verir. Bağımsız değişken tanımları aşağıdaki gibidir:  
  
 `argc`  
 `argv` içinde, izleyen bağımsız değişkenlerin sayısını içeren bir tamsayı. `argc` parametresi her zaman 1'e eşit veya daha büyüktür.  
  
 `argv`  
 Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kural tarafından `argv` **[0]** ile program çağrılır, komut `argv` **[1]** kadar ilk komut satırı bağımsız değişkeni vb. olan `argv`  **[**`argc`**]**, her zaman olduğu **NULL**. Bkz: [komut satırı işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) komut satırı işlemeyi gizleme hakkında bilgi için.  
  
 Her zaman ilk komut satırı bağımsız değişkeni olan `argv` **[1]** ve son `argv` **[** `argc` - 1 **]**.  
  
> [!NOTE]
>  Kural tarafından `argv` **[0]** ile program çağrılır komutu.  Ancak, bir işlemi kullanarak oluşturma olası [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms683197) ve birinci ve ikinci bağımsız kullanıyorsanız (`lpApplicationName` ve `lpCommandLine`), `argv` **[0]** olmayabilir yürütülebilir dosya adı; kullanmak [GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197) yürütülebilir dosya adı ve tam yolu alınamadı.  
  
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 `envp`  
 Bir çok UNIX sisteminde yaygın bir uzantı olan `envp` dizisi Microsoft C++'da kullanılır. Kullanıcının ortamında ayarlanmış değişkenleri temsil eden bir dize dizisidir. Bu dizi tarafından sonlandırılır bir **NULL** girişi. İşaretçiler dizisi olarak bildirilebilir **char (char** \*envp []**)** veya işaretçileri gösteren bir işaretçi olarak **char (char** \* \* envp **)**. Programınızı kullanıyorsa **wmain** yerine **ana**, kullanın `wchar_t` veri türü yerine `char`. Ortam bloğu geçirilen **ana** ve **wmain** geçerli ortamda "dondurulmuş" bir kopyasıdır. Ortam için bir çağrı aracılığıyla daha sonra değiştirirseniz **putenv** veya `_wputenv`, geçerli ortamı (tarafından döndürülen `getenv` / `_wgetenv` ve `_environ` /  `_wenviron` değişkeni) değişikliği ancak envp tarafından işaret blok değişmez. Bkz: [komut satırı işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) ortam işlemeyi gizleme hakkında bilgi için. Bu bağımsız değişken, C'de ANSI ile uyumludur, ancak C++'da değildir.  
  
**SON Microsoft özel**  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `argc`, `argv`, ve `envp` bağımsız değişkenleri **ana**:  
  
```  
// argument_definitions.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
int main( int argc, char *argv[], char *envp[] ) {  
    int iNumberLines = 0;    // Default is no line numbers.  
  
    // If /n is passed to the .exe, display numbered listing  
    // of environment variables.  
  
    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )  
         iNumberLines = 1;  
  
    // Walk through list of strings until a NULL is encountered.  
    for( int i = 0; envp[i] != NULL; ++i ) {  
        if( iNumberLines )  
            cout << i << ": " << envp[i] << "\n";  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [main: Program Başlatma](../cpp/main-program-startup.md)