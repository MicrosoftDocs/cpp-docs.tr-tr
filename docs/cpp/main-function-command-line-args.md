---
title: '`main` işlev ve komut satırı bağımsız değişkenleri (C++)'
description: '`main`İşlevi, bir C++ programının giriş noktasıdır.'
ms.date: 11/19/2020
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
ms.openlocfilehash: 8a5ed43bdacf5d9d6dd2cbc5d1c56783c82b8e9a
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483223"
---
# <a name="no-locmain-function-and-command-line-arguments"></a>`main` işlev ve komut satırı bağımsız değişkenleri

Tüm C++ programlarının bir işlevi olmalıdır `main` . Bir C++ programını işlev olmadan derlemeye çalışırsanız `main` , derleyici bir hata oluşturur. (Dinamik bağlantı kitaplıkları ve static kitaplıklarının `main` işlevi yoktur.) `main` İşlev, kaynak kodunuzun yürütmeyi başladığı yerdir, ancak bir program işleve girmeden önce `main` static Açık başlatıcılar olmayan tüm sınıf üyeleri sıfır olarak ayarlanır. Microsoft C++ ' da, genel static nesneler öğesine girişinden önce de başlatılır `main` . Çeşitli kısıtlamalar, `main` diğer C++ işlevleri için Uygulanmadıkları işlev için geçerlidir. `main`İşlev:

- Aşırı yüklenemez (bkz. [işlev aşırı yüklemesi](./function-overloading.md)).
- Olarak bildirilemez **`inline`** .
- Olarak bildirilemez **`static`** .
- Adresi alınamaz.
- , Programınızdan çağrılamaz.

## <a name="the-no-locmain-function-signature"></a>`main`İşlev imzası

`main`Dilde yerleşik olduğundan işlevin bildirimi yoktur. Olsaydı, için bildirim söz dizimi şöyle `main` görünür:

```cpp
int main();
int main(int argc, char *argv[]);
```

İçinde dönüş değeri belirtilmemişse `main` , derleyici bir dönüş değeri sağlar.

## <a name="standard-command-line-arguments"></a>Standart komut satırı bağımsız değişkenleri

Bağımsız değişkenleri için `main` uygun komut satırı ayrıştırmaya izin veren için bağımsız değişkenler. `argc`Ve türleri `argv` dil tarafından tanımlanır. Adlar `argc` ve `argv` geleneksel bir addır, ancak bunları dilediğiniz gibi adlandırabilirsiniz.

Bağımsız değişken tanımları aşağıdaki gibidir:

*`argc`*\
İçinde izleyen bağımsız değişkenlerin sayısını içeren bir tamsayı *argv* . *argc* Parametresi her zaman 1 ' den büyük veya eşittir.

*`argv`*\
Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kuralına göre, `argv[0]` programın çağrıldığı komuttur. `argv[1]` İlk komut satırı bağımsız değişkenidir. Komut satırındaki son bağımsız değişken `argv[argc - 1]` , `argv[argc]` her zaman null olur.

Komut satırı işlemesini gösterme hakkında daha fazla bilgi için bkz. [C++ komut satırı Işlemeyi özelleştirme](#customize).

> [!NOTE]
> Kurala göre, `argv[0]` programın dosya adıdır. Ancak, Windows üzerinde kullanarak bir işlem oluşturulabilir [`CreateProcess`](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) . Hem birinci hem de ikinci bağımsız değişkenleri ( *`lpApplicationName`* ve) kullanırsanız *`lpCommandLine`* , `argv[0]` yürütülebilir ad olmayabilir. [`GetModuleFileName`](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew)Yürütülebilir adını ve tam yolunu almak için öğesini kullanabilirsiniz.

## <a name="microsoft-specific-extensions"></a>Microsoft 'a özgü uzantılar

Aşağıdaki bölümlerde Microsoft 'a özgü davranış açıklanır.

## <a name="the-no-locwmain-function-and-no-loc_tmain-macro"></a>`wmain`İşlev ve `_tmain` makro

Kaynak kodunuzu Unicode geniş acter kullanmak üzere tasarlarsanız char , ' `wmain` char ın geniş acter sürümü olan Microsoft 'a özgü giriş noktasını kullanabilirsiniz `main` . İşte şu için geçerli bildirim söz dizimi `wmain` :

```cpp
int wmain();
int wmain(int argc, wchar_t *argv[]);
```

Ayrıca `_tmain` , içinde tanımlanan bir önişlemci makrosu olan Microsoft 'a özgü ' i de kullanabilirsiniz *`tchar.h`* . `_tmain``main`tanımlı olmadığı durumlar olarak çözümlenir `_UNICODE` . Bu durumda, `_tmain` olarak çözümlenir `wmain` . `_tmain`Makro ve ile başlayan diğer makrolar, `_t` hem dar hem de geniş acter kümeleri için ayrı sürümler oluşturması gereken kod için yararlıdır char . Daha fazla bilgi için bkz. [Genel metin eşlemelerini kullanma](../c-runtime-library/using-generic-text-mappings.md).

## <a name="returning-no-locvoid-from-no-locmain"></a>`void`Şuradan döndürülüyormain

Bir Microsoft uzantısı olarak, `main` ve `wmain` işlevleri döndüren **`void`** (dönüş değeri yok) olarak bildirilemez. Bu uzantı diğer bazı derleyicilerde de kullanılabilir, ancak kullanımı önerilmez. Değer döndürmezse simetri için kullanılabilir `main` .

`main`Öğesini bildirir veya `wmain` iade ederseniz **`void`** , exit bir bildirimi kullanarak üst işleme veya işletim sistemine bir kod geri dönemezsiniz [`return`](./program-termination.md) . exitVeya olarak bildirildiği zaman bir kod döndürmek için `main` `wmain` **`void`** işlevini kullanmanız gerekir [`exit`](./program-termination.md) .

## <a name="the-no-locenvp-command-line-argument"></a>`envp`Komut satırı bağımsız değişkeni

`main`Veya `wmain` imzaları, ortam değişkenlerine erişim için Isteğe bağlı Microsoft 'a özgü bir uzantıya izin verir. Bu uzantı, Windows ve UNIX sistemleri için diğer derleyicilerde da ortaktır. Ad *`envp`* geleneksel olarak belirlenir, ancak ortam parametresini dilediğiniz gibi adlandırabilirsiniz. Ortam parametresini içeren bağımsız değişken listelerine yönelik etkili bildirimler aşağıda verilmiştir:

```cpp
int main(int argc, char* argv[], char* envp[]);
int wmain(int argc, wchar_t* argv[], wchar_t* envp[]);
```

*`envp`*\
İsteğe bağlı *`envp`* parametresi, kullanıcının ortamında ayarlanmış değişkenleri temsil eden bir dize dizisidir. Bu dizi, NULL bir girdi tarafından sona erdirildi. () İşaretçilerinden oluşan bir dizi **`char`** `char *envp[]` ya da () işaretçilerin işaretçisi olarak belirtilebilir **`char`** `char **envp` . Programınız `wmain` yerine kullanıyorsa `main` , **`wchar_t`** yerine veri türünü kullanın **`char`** .

Ortam bloğu, `main` ve `wmain` geçerli ortamın "dondurulmuş" bir kopyasına geçirilir. Daha sonra, veya için bir çağrısı yaparak ortamı değiştirirseniz `putenv` `_wputenv` , geçerli ortam (veya ile veya değişkeni tarafından döndürülen `getenv` `_wgetenv` `_environ`  `_wenviron` ) değişir, ancak tarafından işaret edilen blok *`envp`* değişmeyecektir. Ortam işlemeyi gösterme hakkında daha fazla bilgi için bkz. [C++ komut satırı Işlemeyi özelleştirme](#customize). *`envp`* Bağımsız değişken c89 standardı ile uyumludur, ancak C++ standartlarıyla birlikte değildir.

### <a name="example-arguments-to-no-locmain"></a>İçin örnek bağımsız değişkenler `main`

Aşağıdaki örnek *`argc`* ,, *`argv`* ve *`envp`* bağımsız değişkenlerinin nasıl kullanılacağını gösterir `main` :

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

## <a name="parsing-c-command-line-arguments"></a>C++ komut satırı bağımsız değişkenlerini ayrıştırma

Microsoft C/C++ kodu tarafından kullanılan komut satırı ayrıştırma kuralları, Microsoft 'a özgüdür. Çalışma zamanı başlangıç kodu, işletim sistemi komut satırında verilen bağımsız değişkenleri yorumlarken bu kuralları kullanır:

- Bağımsız değişkenler boşluk veya sekme olan boşluk ile sınırlandırılmıştır.

- İlk bağımsız değişken ( `argv[0]` ) özel olarak değerlendirilir. Program adını temsil eder. Geçerli bir yol adı olması gerektiğinden, çift tırnak işaretleriyle () çevrelenen bölümlere **`"`** izin verilir. Çift tırnak işaretleri çıkışa dahil edilmez `argv[0]` . Çift tırnak işareti içine alınmış parçalar, bağımsız değişkenin sonuna kadar bir boşluk veya sekme acter yorumu yapılmasını önler char . Bu listedeki sonraki kurallar uygulanmaz.

- Çift tırnak işaretleri içine alınmış bir dize, boşluk vericileri içerebilen tek bir bağımsız değişken olarak yorumlanır char . Tırnak içine alınmış bir dize bir bağımsız değişkene gömülebilir. Şapka işareti ( **`^`** ) bir kaçış char veya sınırlayıcı olarak tanınmıyor. Tırnak içine alınmış bir dize içinde çift tırnak işareti çifti tek bir kaçan çift tırnak işareti olarak yorumlanır. Bir kapanış çift tırnak işareti olmadan önce komut satırı sona erdiğinde, char son bağımsız değişken olarak çıkış için o kadar okunan tüm alıcılar.

- Önünde ters eğik çizgi () olan bir çift tırnak işareti **`\"`** , sabit bir çift tırnak işareti () olarak yorumlanır **`"`** .

- Ters eğik çizgiler, bir çift tırnak işaretinden hemen önce gelmedikleri takdirde tam olarak yorumlanır.

- İki ters eğik çizgi daha sonra çift tırnak işareti olursa, bir ters eğik çizgi () **`\`** `argv` , her ters eğik çizgi () için diziye yerleştirilir **`\\`** ve çift tırnak işareti ( **`"`** ) bir dize sınırlayıcısı olarak yorumlanır.

- Tek bir ters eğik çizgiden sonra çift tırnak işareti varsa, **`\`** `argv` her ters eğik çizgi () çifti için diziye bir ters eğik çizgi () konur **`\\`** . Çift tırnak işareti, yeniden eğik çizgi tarafından bir kaçış sırası olarak yorumlanır main ve değişmez değer çift tırnak işareti ( **`"`** ) konur `argv` .

### <a name="example-of-command-line-argument-parsing"></a>Komut satırı bağımsız değişkeni ayrıştırma örneği

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

### <a name="results-of-parsing-command-lines"></a>Komut satırlarını ayrıştırma sonuçları

Aşağıdaki tabloda, önceki listede bulunan kuralları gösteren örnek giriş ve beklenen çıkış gösterilmektedir.

| Komut satırı girişi | argv1 | argviki | argv03 |
|--|--|--|--|
| `"abc" d e` | `abc` | `d` | `e` |
| `a\\b d"e f"g h` | `a\\b` | `de fg` | `h` |
| `a\\\"b c d` | `a\"b` | `c` | `d` |
| `a\\\\"b c" d e` | `a\\b c` | `d` | `e` |
| `a"b"" c d` | `ab" c d` |  |  |

## <a name="wildcard-expansion"></a>Joker karakter genişletmesi

Microsoft derleyicisi isteğe bağlı olarak *wildcard* char , **`?`** **`*`** komut satırında dosya adı ve yol bağımsız değişkenlerini belirtmek için joker karakterleri, soru işaretini () ve yıldız işaretini () kullanmanıza olanak tanır.

Komut satırı bağımsız değişkenleri, varsayılan olarak joker karakterleri dize dizisindeki ayrı dizelerde genişletmeyen çalışma zamanı başlangıç kodundaki bir iç yordam tarafından işlenir `argv` . *`setargv.obj`* *`wsetargv.obj`* `wmain` **`/link`** Derleyici seçeneklerinizde veya komut satırlarınızın dosyasını (dosyası) **`LINK`** ekleyerek joker karakter genişletmeyi etkinleştirebilirsiniz.

Çalışma zamanı başlatma bağlayıcı seçenekleri hakkında daha fazla bilgi için bkz. [bağlantı seçenekleri](../c-runtime-library/link-options.md).

## <a name="customize-c-command-line-processing"></a><a name="customize"/> C++ komut satırı işlemini özelleştirme

Programınız komut satırı bağımsız değişkenleri içermiyorsa, az miktarda alan kaydetmek için komut satırı işleme yordamını gizleyebilirsiniz. Kullanımını bastırmak için, *`noarg.obj`* `main` `wmain` **`/link`** derleyici seçeneklerinizde veya **`LINK`** komut satırlarınızın dosyasını (hem hem de için) dahil edin.

Benzer şekilde, ortam tablosuna hiçbir daha bağımsız değişken aracılığıyla erişemiyorsanız *`envp`* , iç ortam işleme yordamını gizleyebilirsiniz. Kullanımını bastırmak için, *`noenv.obj`* `main` `wmain` **`/link`** derleyici seçeneklerinizde veya **`LINK`** komut satırlarınızın dosyasını (hem hem de için) dahil edin.

Programınız, `spawn` `exec` C çalışma zamanı kitaplığı 'nda veya yordam ailesine çağrı yapabilir. Varsa, bir ortamı üst işlemden alt işleme geçirmek için kullanıldığından, ortam işleme yordamını gizmemelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Temel kavramlar](../cpp/basic-concepts-cpp.md)
