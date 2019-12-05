---
title: Bağımsız Değişken Tanımları
ms.date: 11/04/2016
helpviewer_keywords:
- envp argument
- main function, arguments
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
ms.openlocfilehash: aebd4800ad8d653d532708784ef0a5333211d46b
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857664"
---
# <a name="argument-definitions"></a>Bağımsız Değişken Tanımları

Prototipteki bağımsız değişkenler

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

bağımsız değişkenlerini komut satırlarıyla kolayca ayrıştırılmasına ve isteğe bağlı olarak ortam değişkenlerine erişime izin verir. Bağımsız değişken tanımları aşağıdaki gibidir:

*argc*<br/>
*Argv*içinde izleyen bağımsız değişkenlerin sayısını içeren bir tamsayı. *Argc* parametresi her zaman 1 ' den büyük veya eşittir.

*argv*<br/>
Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kural gereği, `argv[0]` programın çağrıldığı komuttur, `argv[1]` ilk komut satırı bağımsız değişkenidir ve bu nedenle, her zaman NULL olan `argv[argc]`kadar olur. Komut satırı işlemeyi gizleme hakkında bilgi için bkz. [komut satırı Işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) .

İlk komut satırı bağımsız değişkeni her zaman `argv[1]` ve en son bir `argv[argc - 1]`.

> [!NOTE]
> Kural gereği, `argv[0]` programın çağrıldığı komuttur.  Ancak, [CreateProcess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) kullanarak bir işlem oluşturulabilir ve hem birinci hem de ikinci bağımsız değişkenleri (*lpApplicationName* ve *lpcommandline*) kullanıyorsanız, `argv[0]` çalıştırılabilir ad olmayabilir; yürütülebilir adı ve tam yolunu almak için [GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) kullanın.

**Microsoft 'a özgü**

*envp*<br/>
Birçok UNIX sisteminde ortak bir uzantı olan *envp* dizisi, Microsoft C++'ta kullanılır. Kullanıcının ortamında ayarlanmış değişkenleri temsil eden bir dize dizisidir. Bu dizi bir NULL girdisiyle sonlandırılır. **Char** (`char *envp[]`) işaretçilerinden oluşan bir dizi veya **char** işaretçilerine (`char **envp`) yönelik bir işaretçi olarak bildirilebilecek. Programınız `main`yerine `wmain` kullanıyorsa, **char**yerine **wchar_t** veri türünü kullanın. `main` ve `wmain` geçirilen ortam bloğu, geçerli ortamın "dondurulmuş" bir kopyasıdır. Daha sonra ortamı `putenv` veya `_wputenv`çağrısıyla değiştirirseniz, geçerli ortam (`getenv` veya `_wgetenv` tarafından döndürülen) ve `_environ` veya `_wenviron` değişkeni) değişir, ancak envp tarafından işaret edilen blok değişmeyecektir. Ortam işlemeyi gizleme hakkında bilgi için bkz. [komut satırı Işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) . Bu bağımsız değişken, C'de ANSI ile uyumludur, ancak C++'da değildir.

**SON Microsoft 'a özgü**

## <a name="example"></a>Örnek

Aşağıdaki örnek, `main`için *argc*, *argv*ve *envp* bağımsız değişkenlerinin nasıl kullanılacağını gösterir:

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[main: Program Başlatma](../cpp/main-program-startup.md)