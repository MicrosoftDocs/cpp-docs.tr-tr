---
title: /DEPENDENTLOADFLAG (Varsayılan bağımlı yük bayraklarını ayarla)
description: /DEPENDENTLOADFLAG seçeneği, LoadLibrary kullanılarak yüklenen dll 'Ler için varsayılan bayrakları ayarlar
ms.date: 05/18/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 072fa1103d049c7d5c395ae88d268f3b47e20b4f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492950"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (Varsayılan bağımlı yük bayraklarını ayarla)

Dll 'leri yüklemek için kullanıldığında kullanılan `LoadLibrary` varsayılan yükleme bayraklarını ayarlar.

## <a name="syntax"></a>Sözdizimi

> **/Dependentloadflag** [ **:** _loadflags_]

### <a name="arguments"></a>Arguments

*loadflags*<br/>
Tüm `0x` [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) çağrılarına uygulanacak bağımlı yükleme bayraklarını belirten, ondalık olarak, önünde sıfır değeri olan veya önünde olan onaltılı olan isteğe bağlı bir "C" stili 16 bit tamsayı değeri. Varsayılan değer 0’dır.

## <a name="remarks"></a>Açıklamalar

Bu seçenek, Visual Studio 2017 ' de yenidir ve yalnızca Windows 10 RS1 ve üzeri sürümlerde çalışan uygulamalar için geçerlidir. Bu seçenek, uygulamayı çalıştıran diğer işletim sistemleri tarafından yok sayılır.

Desteklenen işletim sistemlerinde, bu seçenek çağrıları `LoadLibrary("dependent.dll")` `LoadLibraryEx("dependent.dll", 0, loadflags)`' a değiştirme etkisi olur. [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) çağrıları etkilenmez. Bu seçenek, uygulamanız tarafından yüklenen dll 'lere yinelemeli olarak uygulanmaz.

Bu bayrak, DLL planlamaları saldırıları engellemek için kullanılabilir. Örneğin, bir uygulama bağımlı dll yüklemek `LoadLibrary` için kullanıyorsa, bir saldırgan tarafından `LoadLibrary`kullanılan arama yolundaki aynı ada sahip bir dll 'yi, güvenli dll arama modunun olması durumunda sistem dizinlerinden önce denetlenebilir olan geçerli dizin gibi devre dışı. Güvenli DLL arama modu, kullanıcının geçerli dizinini daha sonra arama sırasına koyar ve Windows XP SP2 ve sonraki sürümlerinde varsayılan olarak etkindir. Daha fazla bilgi için bkz. [dinamik bağlantı kitaplığı arama sırası](/windows/win32/Dlls/dynamic-link-library-search-order).

Bağlantı seçeneğini `/DEPENDENTLOADFLAG:0xA00` belirtirseniz (Birleşik bayrakların `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`değeri), ancak kullanıcının bilgisayarında güvenli dll arama modu devre dışı bırakılmış olsa bile, DLL arama yolu, bir saldırganın değişebilir. Kullanılabilir bayraklar ve bunların sembolik ve sayısal değerleri hakkında daha fazla bilgi için bkz. [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)Içindeki *dwFlags* parametre açıklaması.

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında DEPENDENTLOADFLAG bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > bağlayıcıkomut > **satırı** özellik sayfasını seçin.

1. **Ek seçenekler**' de seçeneği girin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC Bağlayıcı Seçenekleri](linker-options.md)
- [Bir yürütülebilir dosyayı DLL’ye bağlama](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Bir yürütülebilir dosyayı DLL’ye bağlama](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [Dinamik bağlantı kitaplığı arama sırası](/windows/win32/Dlls/dynamic-link-library-search-order)
