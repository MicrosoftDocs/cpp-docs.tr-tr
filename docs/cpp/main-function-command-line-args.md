---
title: main işlevi ve komut satırı bağımsız değişkenleri (C++)
description: main işlevi, bir C++ programın giriş noktasıdır.
ms.date: 01/15/2019
ms.assetid: c6568ee6-40ab-4ae8-aa44-c99e232f64ac
no-loc:
- main
- wmain
- inline
- static
- _tmain
- void
- exit
- argc
- argv
- envp
- CreateProcess
- GetModuleFileName
- char
- wchar_t
- extern
ms.openlocfilehash: 33753e30304a9bb63c135979d3f20098e6b6401a
ms.sourcegitcommit: e93f3e6a110fe38bc642055bdf4785e620d4220f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76123909"
---
# <a name="opno-locmain-function-and-command-line-arguments"></a>main işlevi ve komut satırı bağımsız değişkenleri

Tüm C++ programlar `main` işleve sahip olmalıdır. Bir C++ *. exe* projesini main işlevi olmadan derlemeye çalışırsanız, derleyici bir hata oluşturacak. (Dinamik bağlantı kitaplıkları ve static kitaplıklarında `main` işlevi yoktur.) `main` işlevi, kaynak kodunuzun yürütmeyi başladığı yerdir, ancak bir program `main` işlevine girmeden önce, açık başlatıcıları olmayan tüm static sınıf üyeleri sıfır olarak ayarlanır. Microsoft C++'ta, genel static nesneleri `main`girişinden önce de başlatılır. Çeşitli kısıtlamalar, diğer C++ işlevler için uygulanan `main` işlevi için geçerlidir. `main` işlevi:

- Aşırı yüklenemez (bkz. [Işlev aşırı yüklemesi](function-overloading.md)).
- **inline** olarak bildirilemez.
- **static** olarak bildirilemez.
- Alınan adresi olamaz.
- Çağrılamaz.

main işlevi, dile yerleştirilmiş olduğundan bir bildirime sahip değildir. Olsaydı, `main` için bildirim söz dizimi şöyle görünür:

```cpp
int main();
int main(int argc, char *argv[], char *envp[]);
```

**Microsoft 'a özgü**

Kaynak dosyalarınız Unicode geniş karakterler kullanıyorsa, `main`geniş karakterli sürümü olan `wmain`kullanabilirsiniz. `wmain` için bildirim sözdizimi şöyledir:

```cpp
int wmain( );
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);
```

Ayrıca, Tchar. h içinde tanımlanan `_tmain`de kullanabilirsiniz. _UNICODE tanımlanmadığı müddetçe `_tmain` `main` çözümlenir. Bu durumda, `_tmain` `wmain`çözümlenmektedir.

Dönüş değeri belirtilmemişse, derleyici bir dönüş değeri olarak sıfır sağlar. Alternatif olarak, `main` ve `wmain` işlevleri döndürülen **void** (dönüş değeri yok) olarak da bildirilemez. **void** döndüren `main` veya `wmain` bildirirseniz, bir [Return](../cpp/return-statement-in-program-termination-cpp.md) ifadesini kullanarak üst işleme veya işletim sistemine bir exit kodu geri dönemezsiniz. `main` veya `wmain` **void** olarak bildirildiği zaman bir exit kodu döndürmek için [exit](../cpp/exit-function.md) işlevini kullanmanız gerekir.

**SON Microsoft 'a özgü**

## <a name="command-line-arguments"></a>Komut satırı bağımsız değişkenleri

`main` veya `wmain` bağımsız değişkenleri, bağımsız değişkenlerin ve isteğe bağlı olarak ortam değişkenlerine erişimin uygun komut satırı ayrıştırmasını sağlar. `argc` ve `argv` türleri, dil tarafından tanımlanır. `argc`, `argv`ve `envp` adları geleneksel olarak bulunur, ancak bunları dilediğiniz gibi adlandırabilirsiniz.

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

Bağımsız değişken tanımları aşağıdaki gibidir:

*argc*<br/>
*argv* ' de izleyen bağımsız değişkenlerin sayısını içeren bir tamsayı. *argc* parametresi her zaman 1 ' den büyük veya eşittir.

*argv*<br/>
Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kural gereği, `argv[0]` programın çağrıldığı komuttur, `argv[1]` ilk komut satırı bağımsız değişkenidir ve bu nedenle, her zaman NULL olan `argv[argc]`kadar olur. Komut satırı işlemeyi gizleme hakkında bilgi için bkz. [komut satırı Işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) .

İlk komut satırı bağımsız değişkeni her zaman `argv[1]` ve en son bir `argv[argc - 1]`.

> [!NOTE]
> Kural gereği, `argv[0]` programın çağrıldığı komuttur. Ancak, [CreateProcess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) kullanarak bir işlem oluşturulabilir ve hem birinci hem de ikinci bağımsız değişkenleri (*lpApplicationName* ve *lpcommandline*) kullanıyorsanız, `argv[0]` yürütülebilir bir ad olmayabilir; yürütülebilir adı ve tam yolunu almak için [GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) kullanın.

**Microsoft 'a özgü**

*envp*<br/>
Birçok UNIX sisteminde ortak bir uzantı olan *envp* dizisi Microsoft C++'ta kullanılır. Kullanıcının ortamında ayarlanmış değişkenleri temsil eden bir dize dizisidir. Bu dizi bir NULL girdisiyle sonlandırılır. **char** (`char *envp[]`) işaretçilerin bir dizisi olarak veya **char** işaretçilerine işaretçi olarak (`char **envp`) belirtilebilir. Programınız `main`yerine `wmain` kullanıyorsa, **char** yerine **wchar_t** veri türünü kullanın. `main` ve `wmain` geçirilen ortam bloğu, geçerli ortamın "dondurulmuş" bir kopyasıdır. Daha sonra ortamı `putenv` veya `_wputenv`çağrısıyla değiştirirseniz, geçerli ortam (`getenv` veya `_wgetenv` tarafından döndürülen) ve `_environ` veya `_wenviron` değişkeni) değişir, ancak envp tarafından işaret edilen blok değişmeyecektir. Ortam işlemeyi gizleme hakkında bilgi için bkz. [komut satırı Işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) . Bu bağımsız değişken, C'de ANSI ile uyumludur, ancak C++'da değildir.

**SON Microsoft 'a özgü**

### <a name="example"></a>Örnek

Aşağıdaki örnek, `main`için *argc* , *argv* ve *envp* bağımsız değişkenlerinin nasıl kullanılacağını gösterir:

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

## <a name="parsing-c-command-line-arguments"></a>Komut C++ satırı bağımsız değişkenlerini ayrıştırma

**Microsoft 'a özgü**

Microsoft C/C++ başlangıç kodu, işletim sistemi komut satırında verilen bağımsız değişkenleri yorumlarken aşağıdaki kuralları kullanır:

- Bağımsız değişkenler boşluk veya sekme olan boşluk ile sınırlandırılmıştır.

- Giriş işareti karakteri (^) bir kaçış karakteri veya sınırlayıcı olarak tanınmıyor. Karakter, programdaki `argv` dizisine geçirilmeden önce, işletim sistemindeki komut satırı ayrıştırıcısı tarafından tamamen işlenir.

- Çift tırnak işaretleri ("*String*") ile çevrelenen bir dize, içinde yer alan boşluk ne olursa olsun tek bir bağımsız değişken olarak yorumlanır. Tırnak içine alınmış bir dize bir bağımsız değişkene gömülebilir.

- Önünde ters eğik çizgi (\\") olan çift tırnak işareti, sabit değer çift tırnak işareti karakteri (") olarak yorumlanır.

- Ters eğik çizgiler, bir çift tırnak işaretinden hemen önce gelmedikleri takdirde tam olarak yorumlanır.

- İki ters eğik çizgi daha sonra çift tırnak işaretiyle, bir ters eğik çizgi, her ters eğik çizgi çifti için `argv` dizisine yerleştirilir ve çift tırnak işareti bir dize sınırlayıcısı olarak yorumlanır.

- Tek bir ters eğik çizgiden sonra çift tırnak işareti varsa, her ters eğik çizgi çifti için `argv` dizisine bir ters eğik çizgi konur ve çift tırnak işareti geri kalan ters eğik çizgi ile, bir sabit değer çift tırnak işareti (") `argv`yerleştirilmesine neden olur.

### <a name="example"></a>Örnek

Aşağıdaki program komut satırı bağımsız değişkenlerinin nasıl geçtiğini göstermektedir:

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

Aşağıdaki tabloda, önceki listede bulunan kuralları gösteren örnek giriş ve beklenen çıkış gösterilmektedir.

### <a name="results-of-parsing-command-lines"></a>Komut satırlarını ayrıştırma sonuçları

|Komut satırı girişi|argv[1]|argv[2]|argv[3]|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**SON Microsoft 'a özgü**

## <a name="wildcard-expansion"></a>Joker karakter genişletmesi

**Microsoft 'a özgü**

Dosya adı ve yol bağımsız değişkenlerini komut satırında belirtmek için soru işareti (?) ve yıldız işareti (*) gibi joker karakterler kullanabilirsiniz.

Komut satırı bağımsız değişkenleri, `_setargv` (veya geniş karakter ortamında `_wsetargv`) adlı bir yordam tarafından işlenir. Bu, varsayılan olarak joker karakterleri `argv` dize dizisindeki ayrı dizelere genişletmez. Joker karakter genişletmeyi etkinleştirme hakkında daha fazla bilgi için bkz. [genişleyen joker bağımsız değişkenleri](../c-language/expanding-wildcard-arguments.md).

**SON Microsoft 'a özgü**

## <a name="customizing-c-command-line-processing"></a>C++ komut satırı işlemini özelleştirme

**Microsoft 'a özgü**

Programınız komut satırı bağımsız değişkenleri içermiyorsa, komut satırı işlemeyi gerçekleştiren kitaplık yordamının kullanımını kaldırarak az miktarda alan kaydedebilirsiniz. Bu yordam `_setargv` olarak adlandırılır ve [joker karakter genişletmesi](../cpp/wildcard-expansion.md)bölümünde açıklanmıştır. Kullanımını bastırmak için `main` işlevini içeren dosyada hiçbir şey yapmaz ve `_setargv`adlandırın. `_setargv` çağrısı daha sonra `_setargv`tanımınız tarafından karşılanır ve kitaplık sürümü yüklenmez.

Benzer şekilde, ortam tablosuna hiçbir daha `envp` bağımsız değişkeni aracılığıyla erişemiyorsanız, ortam işleme yordamının `_setenvp`yerine, kendi boş bir yordamını sağlayabilirsiniz. `_setargv` işlevinde olduğu gibi, `_setenvp` **"C"extern** olarak bildirilmelidir.

Programınız, C çalışma zamanı kitaplığındaki `spawn` veya `exec` ailesinden bir yordam çağrısı yapabilir. Bu yordam, bir ortamı üst işlemden alt işleme geçirmek için kullanıldığından, ortam işleme yordamını gizlemez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Temel Kavramlar](../cpp/basic-concepts-cpp.md)
