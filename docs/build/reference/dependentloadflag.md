---
title: /DEPENDENTLOADFLAG (Varsayılan bağımlı yük bayraklarını ayarla)
description: /DEPENDENTLOADFLAG seçeneği, LoadLibrary kullanılarak yüklenen dll 'Ler için varsayılan bayrakları ayarlar
ms.date: 12/22/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 3a403f22c88ccd3e25ba95c183656ad2ffafd05a
ms.sourcegitcommit: ef34a11cb04511221bf5c7b9f4f55ad91a7a603f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/23/2019
ms.locfileid: "75330004"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (Varsayılan bağımlı yük bayraklarını ayarla)

Dll 'Leri yüklemek için `LoadLibrary` kullanıldığında kullanılan varsayılan yükleme bayraklarını ayarlar.

## <a name="syntax"></a>Sözdizimi

> **/Dependentloadflag**[ __:__ *load_flags*]

### <a name="arguments"></a>Arguments

*load_flags*<br/>
İsteğe bağlı bir "C" stili 16 bit tamsayı değeri ondalık, önünde sıfır ile sekizlik, tüm [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) çağrılarına uygulanacak bağımlı yükleme bayraklarını belirten önde gelen bir `0x`. Varsayılan değer 0'dır.

## <a name="remarks"></a>Açıklamalar

Bu seçenek, Visual Studio 2017 ' de yenidir. Yalnızca Windows 10 RS1 ve üzeri sürümlerde çalışan uygulamalar için geçerlidir. Bu seçenek, uygulamayı çalıştıran diğer işletim sistemleri tarafından yok sayılır.

Desteklenen işletim sistemlerinde, bu seçenek `LoadLibrary("dependent.dll")` çağrılarının `LoadLibraryEx("dependent.dll", 0, load_flags)`eşdeğerine değiştirilmesine etkisi vardır. [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) çağrıları etkilenmez. Bu seçenek, uygulamanız tarafından yüklenen dll 'lere yinelemeli olarak uygulanmaz.

Bu bayrak, [DLL planlamaları](/windows/win32/dlls/dynamic-link-library-security) daha zor hale getirmek için kullanılabilir. Örneğin, bir uygulama bağımlı DLL yüklemek için `LoadLibrary` kullanıyorsa, bir saldırgan, güvenli DLL arama modu devre dışı bırakılmışsa sistem dizinlerinden önce denetlenebilen geçerli dizin gibi `LoadLibrary`tarafından kullanılan arama yolunda aynı ada sahip bir DLL oluşturabilir. Güvenli DLL arama modu, kullanıcının geçerli dizinini daha sonra arama sırasına koyar ve Windows XP SP2 ve sonraki sürümlerinde varsayılan olarak etkindir. Daha fazla bilgi için bkz. [dinamik bağlantı kitaplığı arama sırası](/windows/win32/Dlls/dynamic-link-library-search-order).

`/DEPENDENTLOADFLAG:0xA00` bağlantı seçeneğini belirtirseniz (Birleşik bayrakların `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), ancak kullanıcının bilgisayarında güvenli DLL arama modu devre dışı bırakılmış olsa bile, DLL arama yolu uygulama diziniyle sınırlandırılmıştır ve sonrasında%Windows%\System32 dizinidir. `/DEPENDENTLOADFLAG:0x800` bir seçeneği daha kısıtlayıcı olduğundan, aramayı%Windows%\System32 diziniyle sınırlandırırsınız. Korunan dizinler daha zordur, ancak bir saldırganın değiştirmesine izin vermez. Kullanılabilir bayraklar ve bunların sembolik ve sayısal değerleri hakkında daha fazla bilgi için bkz. [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)Içindeki *dwFlags* parametre açıklaması. Çeşitli bağımlı yük bayrakları kullanıldığında kullanılan arama sırası hakkında daha fazla bilgi için, bkz. [LOAD_LIBRARY_SEARCH bayraklarını kullanarak arama sırası](/windows/win32/dlls/dynamic-link-library-search-order#search-order-using-load_library_search-flags).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında DEPENDENTLOADFLAG bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** Özellik sayfası ' nı seçin.

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
