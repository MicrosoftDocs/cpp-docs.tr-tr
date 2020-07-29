---
title: :::no-loc(main):::işlev ve komut satırı bağımsız değişkenleri (C++)
description: :::no-loc(main):::İşlevi, bir C++ programının giriş noktasıdır.
ms.date: 01/15/2019
ms.assetid: c6568ee6-40ab-4ae8-aa44-c99e232f64ac
no-loc:
- ':::no-loc(main):::'
- ':::no-loc(wmain):::'
- ':::no-loc(inline):::'
- ':::no-loc(static):::'
- ':::no-loc(_tmain):::'
- ':::no-loc(void):::'
- ':::no-loc(exit):::'
- ':::no-loc(argc):::'
- ':::no-loc(argv):::'
- ':::no-loc(envp):::'
- ':::no-loc(CreateProcess):::'
- ':::no-loc(GetModuleFileName):::'
- ':::no-loc(char):::'
- ':::no-loc(wchar_t):::'
- ':::no-loc(extern):::'
ms.openlocfilehash: 9fe7c7a0808584a70bffa541903866b3de364e5f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213326"
---
# <a name="no-locmain-function-and-command-line-arguments"></a>:::no-loc(main):::işlev ve komut satırı bağımsız değişkenleri

Tüm C++ programlarının bir işlevi olmalıdır `:::no-loc(main):::` . Bir C++ *. exe* projesini işlev olmadan derlemeye çalışırsanız :::no-loc(main)::: , derleyici bir hata oluşturacak. (Dinamik bağlantı kitaplıkları ve :::no-loc(static)::: kitaplıklarının `:::no-loc(main):::` işlevi yoktur.) `:::no-loc(main):::`İşlev, kaynak kodunuzun yürütmeyi başladığı yerdir, ancak bir program işleve girmeden önce `:::no-loc(main):::` :::no-loc(static)::: Açık başlatıcılar olmayan tüm sınıf üyeleri sıfır olarak ayarlanır. Microsoft C++ ' da, genel :::no-loc(static)::: nesneler öğesine girişinden önce de başlatılır `:::no-loc(main):::` . Çeşitli kısıtlamalar, `:::no-loc(main):::` diğer C++ işlevleri için uygulanan işlev için geçerlidir. `:::no-loc(main):::`İşlev:

- Aşırı yüklenemez (bkz. [Işlev aşırı yüklemesi](function-overloading.md)).
- Olarak bildirilemez **`:::no-loc(inline):::`** .
- Olarak bildirilemez **`:::no-loc(static):::`** .
- Alınan adresi olamaz.
- Çağrılamaz.

:::no-loc(main):::Dilde yerleşik olduğundan işlevin bildirimi yoktur. Olsaydı, için bildirim söz dizimi şöyle `:::no-loc(main):::` görünür:

```cpp
int :::no-loc(main):::();
int :::no-loc(main):::(int :::no-loc(argc):::, :::no-loc(char)::: *:::no-loc(argv):::[], :::no-loc(char)::: *:::no-loc(envp):::[]);
```

**Microsoft'a Özgü**

Kaynak dosyalarınız Unicode genelinde :::no-loc(char)::: acters erişim kullanıyorsa, `:::no-loc(wmain):::` ' nin geniş acter sürümü olan ' yi kullanabilirsiniz :::no-loc(char)::: `:::no-loc(main):::` . İçin bildirim sözdizimi `:::no-loc(wmain):::` aşağıdaki gibidir:

```cpp
int :::no-loc(wmain):::( );
int :::no-loc(wmain):::(int :::no-loc(argc):::, :::no-loc(wchar_t)::: *:::no-loc(argv):::[], :::no-loc(wchar_t)::: *:::no-loc(envp):::[]);
```

`:::no-loc(_tmain):::`T. h içinde tanımlanan öğesini de kullanabilirsiniz :::no-loc(char)::: . `:::no-loc(_tmain):::``:::no-loc(main):::`_UNICODE tanımlanmadığı müddetçe olarak çözümlenir. Bu durumda, `:::no-loc(_tmain):::` olarak çözümlenir `:::no-loc(wmain):::` .

Dönüş değeri belirtilmemişse, derleyici bir dönüş değeri olarak sıfır sağlar. Alternatif olarak, `:::no-loc(main):::` ve `:::no-loc(wmain):::` işlevleri döndüren **`:::no-loc(void):::`** (dönüş değeri yok) olarak bildirilemez. `:::no-loc(main):::`Öğesini bildirir veya `:::no-loc(wmain):::` iade ederseniz **`:::no-loc(void):::`** , :::no-loc(exit)::: bir [dönüş](../cpp/return-statement-in-program-termination-cpp.md) ifadesini kullanarak bir kodu üst işleme veya işletim sistemine geri dönemezsiniz. :::no-loc(exit):::Veya olarak bildirildiği zaman bir kod döndürmek için `:::no-loc(main):::` `:::no-loc(wmain):::` **`:::no-loc(void):::`** işlevini kullanmanız gerekir [:::no-loc(exit):::](../cpp/:::no-loc(exit):::-function.md) .

**SON Microsoft 'a özgü**

## <a name="command-line-arguments"></a>Komut satırı bağımsız değişkenleri

Bağımsız değişkenlerin `:::no-loc(main):::` `:::no-loc(wmain):::` ve isteğe bağlı olarak, ortam değişkenlerine erişim için uygun komut satırı ayrıştırmasını veya buna izin verir. `:::no-loc(argc):::`Ve türleri `:::no-loc(argv):::` dil tarafından tanımlanır. , `:::no-loc(argc):::` Ve adları `:::no-loc(argv):::` `:::no-loc(envp):::` geleneksel olarak bulunur, ancak bunları dilediğiniz gibi adlandırabilirsiniz.

```cpp
int :::no-loc(main):::( int :::no-loc(argc):::, :::no-loc(char):::* :::no-loc(argv):::[], :::no-loc(char):::* :::no-loc(envp):::[]);
int :::no-loc(wmain):::( int :::no-loc(argc):::, :::no-loc(wchar_t):::* :::no-loc(argv):::[], :::no-loc(wchar_t):::* :::no-loc(envp):::[]);
```

Bağımsız değişken tanımları aşağıdaki gibidir:

*:::no-loc(argc):::*<br/>
İçinde izleyen bağımsız değişkenlerin sayısını içeren bir tamsayı *:::no-loc(argv):::* . *:::no-loc(argc):::* Parametresi her zaman 1 ' den büyük veya eşittir.

*:::no-loc(argv):::*<br/>
Programın kullanıcısı tarafından girilen komut satırı bağımsız değişkenlerini temsil eden boş sonlandırılmış bir dize dizisi. Kuralına göre, `:::no-loc(argv):::[0]` programın çağrıldığı komuttur, `:::no-loc(argv):::[1]` ilk komut satırı bağımsız değişkeni, ve `:::no-loc(argv):::[:::no-loc(argc):::]` Bu nedenle her zaman null olan. Komut satırı işlemeyi gizleme hakkında bilgi için bkz. [komut satırı Işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) .

İlk komut satırı bağımsız değişkeni her zaman `:::no-loc(argv):::[1]` ve en son bir ' dır `:::no-loc(argv):::[:::no-loc(argc)::: - 1]` .

> [!NOTE]
> Kuralına göre, `:::no-loc(argv):::[0]` programın çağrıldığı komuttur. Ancak, kullanarak bir işlem oluşturulabilir [:::no-loc(CreateProcess):::](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) ve hem birinci hem de ikinci bağımsız değişkenleri (*lpApplicationName* ve *lpCommandLine*) kullanırsanız, `:::no-loc(argv):::[0]` yürütülebilir ad olmayabilir; [:::no-loc(GetModuleFileName):::](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) yürütülebilir adı ve tam yolunu almak için kullanın.

**Microsoft'a Özgü**

*:::no-loc(envp):::*<br/>
*:::no-loc(envp):::* Bırçok UNIX sisteminde ortak bir uzantı olan dizi, Microsoft C++ ' da kullanılır. Kullanıcının ortamında ayarlanmış değişkenleri temsil eden bir dize dizisidir. Bu dizi, NULL bir girdi tarafından sona erdirildi. () İşaretçilerinden oluşan bir dizi **`:::no-loc(char):::`** `:::no-loc(char)::: *:::no-loc(envp):::[]` ya da () işaretçilerin işaretçisi olarak belirtilebilir **`:::no-loc(char):::`** `:::no-loc(char)::: **:::no-loc(envp):::` . Programınız `:::no-loc(wmain):::` yerine kullanıyorsa `:::no-loc(main):::` , **`:::no-loc(wchar_t):::`** yerine veri türünü kullanın **`:::no-loc(char):::`** . Ortam bloğu, `:::no-loc(main):::` ve `:::no-loc(wmain):::` geçerli ortamın "dondurulmuş" bir kopyasına geçirilir. Daha sonra ortamı bir veya çağrısı yoluyla değiştirirseniz `putenv` `_wputenv` , geçerli ortam ( `getenv` veya ile veya değişkeni tarafından döndürülen `_wgetenv` `_environ` `_wenviron` ) değişir ancak tarafından işaret edilen blok :::no-loc(envp)::: değişmez. Ortam işlemeyi gizleme hakkında bilgi için bkz. [komut satırı Işlemeyi özelleştirme](../cpp/customizing-cpp-command-line-processing.md) . Bu bağımsız değişken, C'de ANSI ile uyumludur, ancak C++'da değildir.

**SON Microsoft 'a özgü**

### <a name="example"></a>Örnek

Aşağıdaki örnek *:::no-loc(argc):::* ,, *:::no-loc(argv):::* ve *:::no-loc(envp):::* bağımsız değişkenlerinin nasıl kullanılacağını gösterir `:::no-loc(main):::` :

```cpp
// argument_definitions.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;
int :::no-loc(main):::( int :::no-loc(argc):::, :::no-loc(char)::: *:::no-loc(argv):::[], :::no-loc(char)::: *:::no-loc(envp):::[] ) {
    int iNumberLines = 0;    // Default is no line numbers.

    // If /n is passed to the .exe, display numbered listing
    // of environment variables.

    if ( (:::no-loc(argc)::: == 2) && _stricmp( :::no-loc(argv):::[1], "/n" ) == 0 )
         iNumberLines = 1;

    // Walk through list of strings until a NULL is encountered.
    for( int i = 0; :::no-loc(envp):::[i] != NULL; ++i ) {
        if( iNumberLines )
            cout << i << ": " << :::no-loc(envp):::[i] << "\n";
    }
}
```

## <a name="parsing-c-command-line-arguments"></a>C++ komut satırı bağımsız değişkenlerini ayrıştırma

**Microsoft'a Özgü**

Microsoft C/C++ başlangıç kodu, işletim sistemi komut satırında verilen bağımsız değişkenleri yorumlarken aşağıdaki kuralları kullanır:

- Bağımsız değişkenler boşluk veya sekme olan boşluk ile sınırlandırılmıştır.

- Şapka işareti :::no-loc(char)::: (^) bir kaçış :::no-loc(char)::: veya sınırlayıcı olarak tanınmıyor. :::no-loc(char):::Acter, programdaki diziye geçirilmeden önce, işletim sistemindeki komut satırı ayrıştırıcısı tarafından tamamen işlenir `:::no-loc(argv):::` .

- Çift tırnak işaretleri ("*String*") ile çevrelenen bir dize, içinde yer alan boşluk ne olursa olsun tek bir bağımsız değişken olarak yorumlanır. Tırnak içine alınmış bir dize bir bağımsız değişkene gömülebilir.

- Önünde ters eğik çizgi (") olan bir çift tırnak işareti \\ , sabit değer çift tırnak işareti :::no-loc(char)::: (") olarak yorumlanır.

- Ters eğik çizgiler, bir çift tırnak işaretinden hemen önce gelmedikleri takdirde tam olarak yorumlanır.

- İki ters eğik çizgi daha sonra çift tırnak işareti kullanıyorsa, bir ters eğik çizgi `:::no-loc(argv):::` her çift eğik çizgi için diziye yerleştirilir ve çift tırnak işareti dize sınırlayıcısı olarak yorumlanır.

- Tek bir ters eğik çizgiden sonra çift tırnak işareti varsa, her ters eğik çizgi çifti için bir ters eğik çizgi konur `:::no-loc(argv):::` ve çift tırnak işareti, yeniden :::no-loc(main)::: oluşturma ters eğik çizgiyle ("), bir sabit değer çift tırnak işaretine (") yerleştirilmesine neden olur `:::no-loc(argv):::` .

### <a name="example"></a>Örnek

Aşağıdaki program komut satırı bağımsız değişkenlerinin nasıl geçtiğini göstermektedir:

```cpp
// command_line_arguments.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
int :::no-loc(main):::( int :::no-loc(argc):::,      // Number of strings in array :::no-loc(argv):::
          :::no-loc(char)::: *:::no-loc(argv):::[],   // Array of command-line argument strings
          :::no-loc(char)::: *:::no-loc(envp):::[] )  // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    cout << "\nCommand-line arguments:\n";
    for( count = 0; count < :::no-loc(argc):::; count++ )
         cout << "  :::no-loc(argv):::[" << count << "]   "
                << :::no-loc(argv):::[count] << "\n";
}
```

Aşağıdaki tabloda, önceki listede bulunan kuralları gösteren örnek giriş ve beklenen çıkış gösterilmektedir.

### <a name="results-of-parsing-command-lines"></a>Komut satırlarını ayrıştırma sonuçları

|Komut satırı girişi|:::no-loc(argv):::1|:::no-loc(argv):::iki|:::no-loc(argv):::03|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**SON Microsoft 'a özgü**

## <a name="wildcard-expansion"></a>Joker karakter genişletmesi

**Microsoft'a Özgü**

Dosya adı ve yol bağımsız değişkenlerini komut satırında belirtmek için soru işareti (?) ve yıldız işareti (*) gibi joker karakterler kullanabilirsiniz.

Komut satırı bağımsız değişkenleri `_set:::no-loc(argv):::` , (veya `_wset:::no-loc(argv):::` geniş acter ortamında) adlı bir yordam tarafından işlenir :::no-loc(char)::: . Bu, varsayılan olarak joker karakterleri dize dizisindeki ayrı dizelerde genişletmez `:::no-loc(argv):::` . Joker karakter genişletmeyi etkinleştirme hakkında daha fazla bilgi için bkz. [genişleyen joker bağımsız değişkenleri](../c-language/expanding-wildcard-arguments.md).

**SON Microsoft 'a özgü**

## <a name="customizing-c-command-line-processing"></a>C++ komut satırı işlemini özelleştirme

**Microsoft'a Özgü**

Programınız komut satırı bağımsız değişkenleri içermiyorsa, komut satırı işlemeyi gerçekleştiren kitaplık yordamının kullanımını kaldırarak az miktarda alan kaydedebilirsiniz. Bu yordam çağrılır `_set:::no-loc(argv):::` ve [joker karakter genişletmesi](../cpp/wildcard-expansion.md)bölümünde açıklanmıştır. Kullanımını bastırmak için, işlevi içeren dosyada hiçbir şey yapmayan bir yordam tanımlayın `:::no-loc(main):::` ve bunu adlandırın `_set:::no-loc(argv):::` . Çağrısı `_set:::no-loc(argv):::` daha sonra tanımınız tarafından karşılanır `_set:::no-loc(argv):::` ve kitaplık sürümü yüklenmez.

Benzer şekilde, ortam tablosuna hiçbir `:::no-loc(envp):::` daha bağımsız değişken aracılığıyla erişemiyorsanız, ortam işleme yordamının yerine, kendi boş bir yordamını sağlayabilirsiniz `_set:::no-loc(envp):::` . İşlevinde olduğu gibi `_set:::no-loc(argv):::` , `_set:::no-loc(envp):::` ** :::no-loc(extern)::: "C"** olarak bildirilmelidir.

Programınız, `spawn` `exec` C çalışma zamanı kitaplığındaki veya yordam ailesine çağrı yapabilir. Bu yordam, bir ortamı üst işlemden alt işleme geçirmek için kullanıldığından, ortam işleme yordamını gizlemez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Temel kavramlar](../cpp/basic-concepts-cpp.md)
