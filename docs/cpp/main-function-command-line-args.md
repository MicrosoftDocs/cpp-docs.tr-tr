---
title: main işlev ve komut satırı bağımsız değişkenleri (C++)
description: mainİşlevi, bir C++ programının giriş noktasıdır.
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
ms.openlocfilehash: b27668c3c7ce77e4369af144bb8be4efb695e522
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499818"
---
# <a name="no-locmain-function-and-command-line-arguments"></a>main işlev ve komut satırı bağımsız değişkenleri

Tüm C++ programlarının bir işlevi olmalıdır `main` . Bir C++ *. exe* projesini işlev olmadan derlemeye çalışırsanız main , derleyici bir hata oluşturacak. (Dinamik bağlantı kitaplıkları ve static kitaplıklarının `main` işlevi yoktur.) `main` İşlev, kaynak kodunuzun yürütmeyi başladığı yerdir, ancak bir program işleve girmeden önce `main` static Açık başlatıcılar olmayan tüm sınıf üyeleri sıfır olarak ayarlanır. Microsoft C++ ' da, genel static nesneler öğesine girişinden önce de başlatılır `main` . Çeşitli kısıtlamalar, `main` diğer C++ işlevleri için uygulanan işlev için geçerlidir. `main`İşlev:

- Aşırı yüklenemez (bkz. [Işlev aşırı yüklemesi](function-overloading.md)).
- Olarak bildirilemez **`inline`** .
- Olarak bildirilemez **`static`** .
- Alınan adresi olamaz.
- Çağrılamaz.

mainDilde yerleşik olduğundan işlevin bildirimi yoktur. Olsaydı, için bildirim söz dizimi şöyle `main` görünür:

```cpp
int main();
int main(int argc, char *argv[], char *envp[]);
```

**Microsoft'a Özgü**

Kaynak dosyalarınız Unicode genelinde char acters erişim kullanıyorsa, `wmain` ' nin geniş acter sürümü olan ' yi kullanabilirsiniz char `main` . İçin bildirim sözdizimi `wmain` aşağıdaki gibidir:

```cpp
int wmain( );
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);
```

`_tmain`T. h içinde tanımlanan öğesini de kullanabilirsiniz char . `_tmain``main`_UNICODE tanımlanmadığı müddetçe olarak çözümlenir. Bu durumda, `_tmain` olarak çözümlenir `wmain` .

Dönüş değeri belirtilmemişse, derleyici bir dönüş değeri olarak sıfır sağlar. Alternatif olarak, `main` ve `wmain` işlevleri döndüren **`void`** (dönüş değeri yok) olarak bildirilemez. `main`Öğesini bildirir veya `wmain` iade ederseniz **`void`** , exit bir [dönüş](./program-termination.md) ifadesini kullanarak bir kodu üst işleme veya işletim sistemine geri dönemezsiniz. exitVeya olarak bildirildiği zaman bir kod döndürmek için `main` `wmain` **`void`** işlevini kullanmanız gerekir [exit](./program-termination.md) .

**SON Microsoft 'a özgü**

## <a name="command-line-arguments"></a>Komut satırı bağımsız değişkenleri

Bağımsız değişkenlerin `main` `wmain` ve isteğe bağlı olarak, ortam değişkenlerine erişim için uygun komut satırı ayrıştırmasını veya buna izin verir. `argc`Ve türleri `argv` dil tarafından tanımlanır. , `argc` Ve adları `argv` `envp` geleneksel olarak bulunur, ancak bunları dilediğiniz gibi adlandırabilirsiniz.

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

Bağımsız değişken tanımları aşağıdaki gibidir:

*argc*<br/>
İçinde izleyen bağımsız değişkenlerin sayısını içeren bir tamsayı *argv* . *argc* Parametresi her zaman 1 ' den büyük veya eşittir.

*argv*<br/>
Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kuralına göre, `argv[0]` programın çağrıldığı komuttur, `argv[1]` ilk komut satırı bağımsız değişkeni, ve `argv[argc]` Bu nedenle her zaman null olan. Komut satırı işlemeyi gizleme hakkında bilgi için bkz. [komut satırı Işlemeyi özelleştirme]() .

İlk komut satırı bağımsız değişkeni her zaman `argv[1]` ve en son bir ' dır `argv[argc - 1]` .

> [!NOTE]
> Kuralına göre, `argv[0]` programın çağrıldığı komuttur. Ancak, kullanarak bir işlem oluşturulabilir [CreateProcess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) ve hem birinci hem de ikinci bağımsız değişkenleri (*lpApplicationName* ve *lpCommandLine*) kullanırsanız, `argv[0]` yürütülebilir ad olmayabilir; [GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) yürütülebilir adı ve tam yolunu almak için kullanın.

**Microsoft'a Özgü**

*envp*<br/>
*envp* Bırçok UNIX sisteminde ortak bir uzantı olan dizi, Microsoft C++ ' da kullanılır. Kullanıcının ortamında ayarlanmış değişkenleri temsil eden bir dize dizisidir. Bu dizi, NULL bir girdi tarafından sona erdirildi. () İşaretçilerinden oluşan bir dizi **`char`** `char *envp[]` ya da () işaretçilerin işaretçisi olarak belirtilebilir **`char`** `char **envp` . Programınız `wmain` yerine kullanıyorsa `main` , **`wchar_t`** yerine veri türünü kullanın **`char`** . Ortam bloğu, `main` ve `wmain` geçerli ortamın "dondurulmuş" bir kopyasına geçirilir. Daha sonra ortamı bir veya çağrısı yoluyla değiştirirseniz `putenv` `_wputenv` , geçerli ortam ( `getenv` veya ile veya değişkeni tarafından döndürülen `_wgetenv` `_environ`  `_wenviron` ) değişir ancak tarafından işaret edilen blok envp değişmez. Ortam işlemeyi gizleme hakkında bilgi için bkz. [komut satırı Işlemeyi özelleştirme]() . Bu bağımsız değişken, C'de ANSI ile uyumludur, ancak C++'da değildir.

**SON Microsoft 'a özgü**

### <a name="example"></a>Örnek

Aşağıdaki örnek *argc* ,, *argv* ve *envp* bağımsız değişkenlerinin nasıl kullanılacağını gösterir `main` :

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

**Microsoft'a Özgü**

Microsoft C/C++ başlangıç kodu, işletim sistemi komut satırında verilen bağımsız değişkenleri yorumlarken aşağıdaki kuralları kullanır:

- Bağımsız değişkenler boşluk veya sekme olan boşluk ile sınırlandırılmıştır.

- Şapka işareti char (^) bir kaçış char veya sınırlayıcı olarak tanınmıyor. charActer, programdaki diziye geçirilmeden önce, işletim sistemindeki komut satırı ayrıştırıcısı tarafından tamamen işlenir `argv` .

- Çift tırnak işaretleri ("*String*") ile çevrelenen bir dize, içinde yer alan boşluk ne olursa olsun tek bir bağımsız değişken olarak yorumlanır. Tırnak içine alınmış bir dize bir bağımsız değişkene gömülebilir.

- Önünde ters eğik çizgi (") olan bir çift tırnak işareti \\ , sabit değer çift tırnak işareti char (") olarak yorumlanır.

- Ters eğik çizgiler, bir çift tırnak işaretinden hemen önce gelmedikleri takdirde tam olarak yorumlanır.

- İki ters eğik çizgi daha sonra çift tırnak işareti kullanıyorsa, bir ters eğik çizgi `argv` her çift eğik çizgi için diziye yerleştirilir ve çift tırnak işareti dize sınırlayıcısı olarak yorumlanır.

- Tek bir ters eğik çizgiden sonra çift tırnak işareti varsa, her ters eğik çizgi çifti için bir ters eğik çizgi konur `argv` ve çift tırnak işareti, yeniden main oluşturma ters eğik çizgiyle ("), bir sabit değer çift tırnak işaretine (") yerleştirilmesine neden olur `argv` .

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

|Komut satırı girişi|argv1|argviki|argv03|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**SON Microsoft 'a özgü**

## <a name="wildcard-expansion"></a>Joker karakter genişletmesi

**Microsoft'a Özgü**

Dosya adı ve yol bağımsız değişkenlerini komut satırında belirtmek için soru işareti (?) ve yıldız işareti (*) gibi joker karakterler kullanabilirsiniz.

Komut satırı bağımsız değişkenleri `_setargv` , (veya `_wsetargv` geniş acter ortamında) adlı bir yordam tarafından işlenir char . Bu, varsayılan olarak joker karakterleri dize dizisindeki ayrı dizelerde genişletmez `argv` . Joker karakter genişletmeyi etkinleştirme hakkında daha fazla bilgi için bkz. [genişleyen joker bağımsız değişkenleri](../c-language/expanding-wildcard-arguments.md).

**SON Microsoft 'a özgü**

## <a name="customizing-c-command-line-processing"></a>C++ komut satırı işlemini özelleştirme

**Microsoft'a Özgü**

Programınız komut satırı bağımsız değişkenleri içermiyorsa, komut satırı işlemeyi gerçekleştiren kitaplık yordamının kullanımını kaldırarak az miktarda alan kaydedebilirsiniz. Bu yordam çağrılır `_setargv` ve [joker karakter genişletmesi]()bölümünde açıklanmıştır. Kullanımını bastırmak için, işlevi içeren dosyada hiçbir şey yapmayan bir yordam tanımlayın `main` ve bunu adlandırın `_setargv` . Çağrısı `_setargv` daha sonra tanımınız tarafından karşılanır `_setargv` ve kitaplık sürümü yüklenmez.

Benzer şekilde, ortam tablosuna hiçbir `envp` daha bağımsız değişken aracılığıyla erişemiyorsanız, ortam işleme yordamının yerine, kendi boş bir yordamını sağlayabilirsiniz `_setenvp` . İşlevinde olduğu gibi `_setargv` , `_setenvp` ** extern "C"** olarak bildirilmelidir.

Programınız, `spawn` `exec` C çalışma zamanı kitaplığındaki veya yordam ailesine çağrı yapabilir. Bu yordam, bir ortamı üst işlemden alt işleme geçirmek için kullanıldığından, ortam işleme yordamını gizlemez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Temel kavramlar](../cpp/basic-concepts-cpp.md)
