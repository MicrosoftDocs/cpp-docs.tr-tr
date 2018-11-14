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
ms.openlocfilehash: 92e213b5accbf8fd5f48ac2111a169e585d82a1d
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328129"
---
# <a name="argument-definitions"></a>Bağımsız Değişken Tanımları

Prototipteki bağımsız değişkenler

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

bağımsız değişkenlerini komut satırlarıyla kolayca ayrıştırılmasına ve isteğe bağlı olarak ortam değişkenlerine erişime izin verir. Bağımsız değişken tanımları aşağıdaki gibidir:

*argc*<br/>
İçinde izleyen bağımsız değişkenlerin sayısını içeren bir tamsayı *argv*. *Argc* parametresi, her zaman 1'e eşit veya daha büyük.

*argv*<br/>
Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kural olarak, `argv[0]` , programın çağrıldığı komuttur `argv[1]` kadar ilk komut satırı bağımsız değişkeni vb. olan `argv[argc]`, olduğu her zaman NULL. Bkz: [komut satırı işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) komut satırı işlemeyi gizleme hakkında bilgi için.

İlk komut satırı bağımsız değişkeni her zaman olduğu `argv[1]` ve sonuncu `argv[argc - 1]`.

> [!NOTE]
> Kural olarak, `argv[0]` ile programın çağrıldığı komuttur.  Ancak, bunu kullanarak bir işlem oluşturmak mümkündür [CreateProcess](/windows/desktop/api/libloaderapi/nf-libloaderapi-getmodulefilenamea) ve ilk ve ikinci bağımsız kullanıyorsanız (*lpApplicationName* ve *lpCommandLine*), `argv[0]` ; yürütülebilir ad olmayabilir kullanma [GetModuleFileName](/windows/desktop/api/libloaderapi/nf-libloaderapi-getmodulefilenamea) yürütülebilir adı ve tam olarak nitelenmiş yolunu almak için.

## <a name="microsoft-specific"></a>Microsoft'a Özgü

*envp*<br/>
*Envp* çok UNIX sisteminde yaygın bir uzantı olan dizisi Microsoft C++'da kullanılır. Kullanıcının ortamında ayarlanmış değişkenleri temsil eden bir dize dizisidir. Bu dizi bir NULL girdisi ile sonlandırılır. Bir işaretçiler dizisi olarak bildirilebilir **char** (`char *envp[]`) veya işaretçilerinin işaretçisi olarak **char** (`char **envp`). Programınızı kullanıyorsa `wmain` yerine `main`, kullanın **wchar_t** veri türü yerine **char**. Öğesine geçirilen ortam bloğu `main` ve `wmain` geçerli ortamın "dondurulmuş" bir kopyasıdır. Daha sonra ortamı çağrısıyla değiştirirseniz `putenv` veya `_wputenv`, geçerli ortam (tarafından döndürülen `getenv` veya `_wgetenv` ve `_environ` veya `_wenviron` değişkeni) tarafından işaret edilen blok ancak değiştirir envp değiştirmez. Bkz: [komut satırı işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) ortam işlemeyi gizleme hakkında bilgi için. Bu bağımsız değişken, C'de ANSI ile uyumludur, ancak C++'da değildir.

**END Microsoft özgü**

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir *argc*, *argv*, ve *envp* bağımsız değişkenleri `main`:

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