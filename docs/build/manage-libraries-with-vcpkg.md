---
title: Vcpkg ile kitaplıkları yönetme
description: Windows, macOS ve Linux 'ta vcpkg kullanarak kitaplıkları yönetmeyi öğrenin.
ms.date: 12/11/2020
ms.technology: cpp-ide
ms.openlocfilehash: 88f8bc1cff7b4b04f5e38b5018676e313383733f
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97684268"
---
# <a name="manage-libraries-with-vcpkg"></a>Vcpkg ile kitaplıkları yönetme

[Vcpkg 'yı yükledikten](install-vcpkg.md)sonra, yerel makinenizde kitaplıklar almak ve bunları oluşturmak için kullanabilirsiniz.

## <a name="search-the-list-of-available-libraries"></a>Kullanılabilir Kitaplıklar listesinde arama yapın

### <a name="windows"></a>[Windows](#tab/windows)

Hangi paketlerin kullanılabilir olduğunu görmek için **`vcpkg search`** komut istemine yazın.

Bu komut, alt klasörlerdeki denetim dosyalarını numaralandırır *`vcpkg/ports`* . Şöyle bir liste görürsünüz:

```cmd
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

Bir modele filtre uygulayabilirsiniz, örneğin **`vcpkg search ta`** :

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-local-machine"></a>Yerel makinenize kitaplık yükler

Kullanarak bir kitaplığın adını aldıktan sonra **`vcpkg search`** , **`vcpkg install`** kitaplığı indirmek ve derlemek için kullanın. vcpkg, *bağlantı noktaları* dizininde kitaplığın portfile dosyasını kullanır. Bir üçlü değer belirtilmemişse, vcpkg, hedef platform için varsayılan Üçlü değer için yüklenir ve derlenir: x86-Windows, x64-Linux. CMake veya x64-OSX. CMake.

Linux kitaplıkları için vcpkg, yerel makinede GCC 'nin yüklü olmasına bağlıdır. MacOS 'ta vcpkg, Clang kullanır.

Portfile bağımlılıkları belirttiğinde, vcpkg bunları indirir ve yükler. İndirmeden sonra, vcpkg kitaplığı, kitaplığın kullandığı yapı sistemini kullanarak oluşturur. CMake ve (Windows üzerinde) MSBuild projeleri tercih edilir, ancak başka bir derleme sistemiyle birlikte desteklenir. Vcpkg, belirtilen yapı sistemini yerel makinede bulamazsa, indirir ve yükler.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

CMake projeleri için, `CMAKE_TOOLCHAIN_FILE` kitaplıklarını ile kullanılabilir hale getirmek için kullanın `find_package()` . Örneğin, Linux veya macOS 'ta:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg/scripts/buildsystems/vcpkg.cmake
```

Windows'da:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg\scripts\buildsystems\vcpkg.cmake
```

Bazı kitaplıklar yüklenebilir seçenekleri içerir. Örneğin, kıvrımlı kitaplığı aradığınızda, köşeli ayraçlar içinde desteklenen seçeneklerin bir listesini de görürsünüz:

```cmd
> vcpkg search curl
curl                 7.68.0-3         A library for transferring data with URLs
curl[tool]                            Builds curl executable
curl[non-http]                        Enables protocols beyond HTTP/HTTPS/HTTP2
curl[http2]                           HTTP2 support
curl[ssl]                             Default SSL backend
curl[ssh]                             SSH support via libssh2
curl[openssl]                         SSL support (OpenSSL)
curl[winssl]                          SSL support (Secure Channel / "WinSSL")
curl[mbedtls]                         SSL support (mbedTLS)
curl[sectransp]                       SSL support (sectransp)
curl[c-ares]                          c-ares support
curl[sspi]                            SSPI support
curl[brotli]                          brotli support (brotli)
curlpp               2018-06-15-3     C++ wrapper around libcURL
```

Bu durumda, köşeli ayraçlar **`[`** ve **`]`** meta karakterler değil değişmez değer.

Komut satırına yüklemek için belirli bir seçenek belirleyebilirsiniz. Örneğin, Windows için varsayılan SSL arka ucunu kullanarak, kıvrımlı kitaplıklar yüklemek için **`vcpkg install curl[ssl]:x86-windows`** komutunu kullanın. Bu komut, gerekirse Çekirdek Kitaplığı da dahil olmak üzere tüm gerekli önkoşulları yüklüyor:

```cmd
> vcpkg list
curl:x86-windows            7.68.0-3   A library for transferring data with URLs
curl[non-http]:x86-windows             Enables protocols beyond HTTP/HTTPS/HTTP2
curl[ssl]:x86-windows                  Default SSL backend
curl[sspi]:x86-windows                 SSPI support
curl[winssl]:x86-windows               SSL support (Secure Channel / "WinSSL")
zlib:x86-windows            1.2.11-6   A compression library
```

### <a name="macos"></a>[macOS](#tab/macos)

Hangi paketlerin kullanılabilir olduğunu görmek için vcpkg kök dizinine geçin ve Terminal bölümüne girin **`./vcpkg search`** .

Bu komut, alt klasörlerdeki denetim dosyalarını numaralandırır *`vcpkg/ports`* . Şöyle bir liste görürsünüz:

```Terminal
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

Bir modele filtre uygulayabilirsiniz, örneğin **`vcpkg search ta`** :

```Terminal
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-computer"></a>Bilgisayarınıza bir kitaplık yükler

Kullanarak bir kitaplığın adını aldıktan sonra **`vcpkg search`** , **`vcpkg install`** kitaplığı indirmek ve derlemek için kullanın. vcpkg, *bağlantı noktaları* dizininde kitaplığın portfile dosyasını kullanır. Bir üçlü değer belirtilmemişse, vcpkg, hedef platform için varsayılan Üçlü değer için yüklenir ve derlenir: x86-Windows, x64-Linux. CMake veya x64-OSX. CMake.

Linux kitaplıkları için vcpkg, yerel makinede GCC 'nin yüklü olmasına bağlıdır. MacOS 'ta vcpkg, Clang kullanır.

Portfile bağımlılıkları belirttiğinde, vcpkg bunları indirir ve yükler. İndirmeden sonra, vcpkg kitaplığı, kitaplığın kullandığı yapı sistemini kullanarak oluşturur. CMake ve (Windows üzerinde) MSBuild projeleri tercih edilir, ancak başka bir derleme sistemiyle birlikte desteklenir. Vcpkg, belirtilen yapı sistemini yerel makinede bulamazsa, indirir ve yükler.

```Terminal
$ ./vcpkg install boost

The following packages will be built and installed:
    boost:x86-macos
  * bzip2:x86-macos
  * zlib:x86-macos
Additional packages (*) will be installed to complete this operation.
```

CMake projeleri için, `CMAKE_TOOLCHAIN_FILE` kitaplıklarını ile kullanılabilir hale getirmek için kullanın `find_package()` . Örnek:

```Terminal
cmake .. -DCMAKE_TOOLCHAIN_FILE=./vcpkg/scripts/buildsystems/vcpkg.cmake
```

Bazı kitaplıklar yüklenebilir seçenekleri içerir. Örneğin, kıvrımlı kitaplığı aradığınızda, köşeli ayraçlar içinde desteklenen seçeneklerin bir listesini de görürsünüz:

```cmd
> vcpkg search curl
curl                 7.68.0-3         A library for transferring data with URLs
curl[tool]                            Builds curl executable
curl[non-http]                        Enables protocols beyond HTTP/HTTPS/HTTP2
curl[http2]                           HTTP2 support
curl[ssl]                             Default SSL backend
curl[ssh]                             SSH support via libssh2
curl[openssl]                         SSL support (OpenSSL)
curl[winssl]                          SSL support (Secure Channel / "WinSSL")
curl[mbedtls]                         SSL support (mbedTLS)
curl[sectransp]                       SSL support (sectransp)
curl[c-ares]                          c-ares support
curl[sspi]                            SSPI support
curl[brotli]                          brotli support (brotli)
curlpp               2018-06-15-3     C++ wrapper around libcURL
```

Bu durumda, köşeli ayraçlar **`[`** ve **`]`** meta karakterler değil değişmez değer.

Komut satırına yüklemek için belirli bir seçenek belirleyebilirsiniz. Örneğin, varsayılan SSL arka ucunu kullanarak, kıvrımlı kitaplıkları yüklemek için **`./vcpkg install curl[ssl]`** komutunu kullanın. Bu komut, gerekirse Çekirdek Kitaplığı da dahil olmak üzere tüm gerekli önkoşulları yüklüyor.

### <a name="linux"></a>[Linux](#tab/linux)

Hangi paketlerin kullanılabilir olduğunu görmek için, kabukta vcpkg kök dizinine geçin ve girin **`./vcpkg search`** .

Bu komut, alt klasörlerdeki denetim dosyalarını numaralandırır *`vcpkg/ports`* . Şöyle bir liste görürsünüz:

```shell
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

Bir modele filtre uygulayabilirsiniz, örneğin **`./vcpkg search ta`** :

```shell
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-linux-machine"></a>Linux makinenize bir kitaplık yükler

Kullanarak bir kitaplığın adını aldıktan sonra **`./vcpkg search`** , **`/vcpkg install`** kitaplığı indirmek ve derlemek için kullanın. vcpkg, kitaplığın portfile dosyasını *`ports`* dizininde kullanır. Bir üçlü değer belirtilmemişse, vcpkg, hedef platform için x64-Linux. CMake gibi varsayılan üçlü performans için yüklenir ve derlenir.

Linux kitaplıkları için vcpkg, yerel makinede GCC 'nin yüklü olmasına bağlıdır.

Portfile bağımlılıkları belirttiğinde, vcpkg bunları indirir ve yükler. İndirmeden sonra, vcpkg kitaplığı, kitaplığın kullandığı yapı sistemini kullanarak oluşturur. CMake projeleri tercih edilir, ancak başka bir derleme sistemiyle birlikte desteklenir. Vcpkg, belirtilen yapı sistemini yerel makinede bulamazsa, indirir ve yükler.

```shell
$ ./vcpkg install boost:x64-linux

The following packages will be built and installed:
    boost:x64-linux
  * bzip2:x64-linux
  * zlib:x64-linux
Additional packages (*) will be installed to complete this operation.
```

CMake projeleri için, `CMAKE_TOOLCHAIN_FILE` kitaplıklarını ile kullanılabilir hale getirmek için kullanın `find_package()` . Örnek:

```shell
cmake .. -DCMAKE_TOOLCHAIN_FILE=./vcpkg/scripts/buildsystems/vcpkg.cmake
```

Bazı kitaplıklar yüklenebilir seçenekleri içerir. Örneğin, kıvrımlı kitaplığı aradığınızda, köşeli ayraçlar içinde desteklenen seçeneklerin bir listesini de görürsünüz:

```cmd
> vcpkg search curl
curl                 7.68.0-3         A library for transferring data with URLs
curl[tool]                            Builds curl executable
curl[non-http]                        Enables protocols beyond HTTP/HTTPS/HTTP2
curl[http2]                           HTTP2 support
curl[ssl]                             Default SSL backend
curl[ssh]                             SSH support via libssh2
curl[openssl]                         SSL support (OpenSSL)
curl[winssl]                          SSL support (Secure Channel / "WinSSL")
curl[mbedtls]                         SSL support (mbedTLS)
curl[sectransp]                       SSL support (sectransp)
curl[c-ares]                          c-ares support
curl[sspi]                            SSPI support
curl[brotli]                          brotli support (brotli)
curlpp               2018-06-15-3     C++ wrapper around libcURL
```

Bu durumda, köşeli ayraçlar **`[`** ve **`]`** meta karakterler değil değişmez değer.

Komut satırına yüklemek için belirli bir seçenek belirleyebilirsiniz. Örneğin, varsayılan SSL arka ucunu kullanarak, kıvrımlı kitaplıkları yüklemek için **`./vcpkg install curl[ssl]`** komutunu kullanın. Bu komut, gerekirse Çekirdek Kitaplığı da dahil olmak üzere tüm gerekli önkoşulları yüklüyor.

---

## <a name="list-the-libraries-already-installed"></a>Zaten yüklü olan kitaplıkları listeleyin

Bazı kitaplıkları yükledikten sonra, **`vcpkg list`** neleri görmek Için Windows üzerinde komutunu kullanabilirsiniz. Linux ve macOS komutları benzerdir.

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

## <a name="target-linux-from-windows-via-wsl"></a>WSL aracılığıyla Windows 'dan Linux 'u hedefleyin

Linux için Windows alt sistemini veya WSL 'yi kullanarak bir Windows makinesinde Linux ikilileri oluşturabilirsiniz. [Windows 10 ' da WSL 'Yi ayarlamak](/windows/wsl/install-win10)için yönergeleri izleyin. Ardından, [Linux Için Visual Studio uzantısıyla](https://devblogs.microsoft.com/cppblog/targeting-windows-subsystem-for-linux-from-visual-studio/)yapılandırın. Windows ve Linux için tüm yerleşik kitaplıklarınızı aynı klasöre yerleştirmekle sorunsuz. Bunlar hem Windows hem de WSL 'den erişilebilir.

## <a name="export-compiled-binaries-and-headers"></a><a name="export_binaries_per_project"></a> Derlenmiş ikili dosyaları ve üstbilgileri dışarı aktarma

Bir ekibin ortak kitaplıklarını indirmesi ve derlemesi için herkese açık hale getirmek verimsiz olur. Tek bir takım üyesi, **`vcpkg export`** ikili dosyaları ve üstbilgileri veya bir NuGet paketini ortak bir ZIP dosyası oluşturmak için komutunu kullanabilir. Daha sonra, diğer ekip üyeleriyle kolayca paylaşabilirsiniz.

## <a name="updateupgrade-installed-libraries"></a>Yüklü kitaplıkları güncelleştirme/yükseltme

Genel Katalog, kitaplıkların en son sürümleriyle güncel tutulur. Yerel kitaplıklarınızdan hangilerinin güncel kalmadığını öğrenmek için kullanın **`vcpkg update`** . Bağlantı noktası koleksiyonunuzu ortak kataloğun en son sürümüne güncelleştirmeye hazırsanız **`vcpkg upgrade`** komutunu çalıştırın. Bu, güncel olmayan yüklü kitaplıklarınızın tümünü veya tümünü otomatik olarak indirir ve yeniden oluşturur.

Varsayılan olarak, **`vcpkg upgrade`** komut yalnızca güncel olmayan kitaplıkları listeler; bunları yükseltmez. Kitaplıkları gerçekten yükseltmek için **`--no-dry-run`** seçeneğini kullanın.

```cmd
> vcpkg upgrade --no-dry-run
```

### <a name="upgrade-options"></a>Yükseltme seçenekleri

- **`--no-dry-run`**  Yükseltmeyi gerçekleştirin; belirtilmediğinde, komut yalnızca güncel olmayan paketleri listeler.
- **`--keep-going`**  Başarısız olsa bile paketleri yüklemeye devam edin.
- **`--triplet <t>`**  Nitelenmemiş paketler için varsayılan Üçlü değer ayarla ' yı ayarlayın.
- **`--vcpkg-root <path>`**  Geçerli dizin veya araç dizini yerine kullanılacak vcpkg dizinini belirtin.

### <a name="upgrade-example"></a>Yükseltme örneği

Aşağıdaki örnek, yalnızca Windows 'da belirtilen kitaplıkların nasıl yükseltileceğini gösterir. Linux ve macOS komutları benzerdir. vcpkg, gerektiğinde otomatik olarak bağımlılıkları çeker.

```cmd
c:\users\username\vcpkg> vcpkg upgrade tiny-dnn:x86-windows zlib
The following packages are up-to-date:
   tiny-dnn:x86-windows

The following packages will be rebuilt:
    * libpng[core]:x86-windows
    * tiff[core]:x86-windows
      zlib[core]:x86-windows
Additional packages (*) will be modified to complete this operation.
If you are sure you want to rebuild the above packages, run this command with the --no-dry-run option.
```

## <a name="contribute-new-libraries"></a>Yeni kitaplıklara katkıda bulunma

Özel bağlantı noktaları koleksiyonunuzda istediğiniz kitaplıkları dahil edebilirsiniz. Ortak kataloğa yönelik yeni bir kitaplık önermek için [GitHub vcpkg sorun sayfasında](https://github.com/Microsoft/vcpkg/issues)bir sorun açın.

## <a name="remove-a-library"></a>Kitaplığı kaldırma

**`vcpkg remove`** Yüklü bir kitaplığı kaldırmak için yazın. Başka herhangi bir kitaplık buna bağımlıysa, **`--recurse`** tüm aşağı akış kitaplıklarının kaldırılmasına neden olan komutunu ile yeniden çalıştırmanız istenir.

## <a name="see-also"></a>Ayrıca bkz.

[vcpkg: Windows, Linux ve macOS için C++ Paket Yöneticisi](./vcpkg.md)\
[GitHub üzerinde vcpkg](https://github.com/Microsoft/vcpkg)\
[Vcpkg 'yi yükler](install-vcpkg.md)\
[Vcpkg 'yi tümleştirin](integrate-vcpkg.md)\
[vcpkg komut satırı başvurusu](vcpkg-command-line-reference.md)\
[Hızlı başlangıç](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[Sık sorulan sorular](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)\
[Paketleri yükleme ve kullanma örnek: SQLite](https://github.com/microsoft/vcpkg/blob/master/docs/examples/installing-and-using-packages.md)
