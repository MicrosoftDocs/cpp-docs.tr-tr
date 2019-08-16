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
ms.openlocfilehash: 14e5ea3a051d81828c5f88ac16df60b6ebb5b559
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498810"
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
Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kuralına göre, `argv[0]` programın çağrıldığı komuttur, `argv[1]` ilk komut satırı bağımsız değişkeni, `argv[argc]`ve bu nedenle her zaman null olan. Komut satırı işlemeyi gizleme hakkında bilgi için bkz. [komut satırı Işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) .

İlk komut satırı bağımsız değişkeni her zaman `argv[1]` ve en son `argv[argc - 1]`bir ' dır.

> [!NOTE]
> Kuralına göre, `argv[0]` programın çağrıldığı komuttur.  Ancak, [CreateProcess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) kullanarak bir işlem oluşturulabilir ve hem birinci hem de ikinci bağımsız değişkenleri (*lpApplicationName* ve `argv[0]` *lpCommandLine*) kullanırsanız yürütülebilir dosya adı olmayabilir; [GetModuleFileName kullanın ](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew)yürütülebilir adını ve tam yolunu almak için.

## <a name="microsoft-specific"></a>Microsoft'a Özgü

*envp*<br/>
Birçok UNIX sisteminde ortak bir uzantı olan *envp* dizisi, Microsoft C++'ta kullanılır. Kullanıcının ortamında ayarlanmış değişkenleri temsil eden bir dize dizisidir. Bu dizi, NULL bir girdi tarafından sona erdirildi. **Char** (`char *envp[]`) işaretçilerinden oluşan bir dizi veya **char** (`char **envp`) işaretçilerine işaretçi olarak belirtilebilir. Programınız `wmain`yerine kullanıyorsa ,charyerinewchar_t`main`veri türünü kullanın. Ortam bloğu, `main` ve `wmain` geçerli ortamın "dondurulmuş" bir kopyasına geçirilir. Daha sonra ortamı bir `putenv` veya `_wputenv`çağrısı yoluyla değiştirirseniz, geçerli ortam (veya `_wgetenv` ile `_environ` veya `_wenviron` değişkeni tarafından `getenv` döndürülen) değişir, ancak bu blok tarafından işaret edilir envp değişmeyecektir. Ortam işlemeyi gizleme hakkında bilgi için bkz. [komut satırı Işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) . Bu bağımsız değişken, C'de ANSI ile uyumludur, ancak C++'da değildir.

**SON Microsoft 'a özgü**

## <a name="example"></a>Örnek

Aşağıdaki örnek, *argc*, `main` *argv*ve *envp* bağımsız değişkenlerinin nasıl kullanılacağını gösterir:

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