---
title: /DEPENDENTLOADFLAG (Varsayılan bağımlı yük bayraklarını ayarla)
description: /DEPENDENTLOADFLAG seçeneği, bu modül tarafından yüklenen dll 'Ler için varsayılan bağımlı yükleme bayraklarını ayarlar.
ms.date: 01/22/2020
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 5e31a0d747e7186814cba3ae1c4cf243569d87a8
ms.sourcegitcommit: b67b08472b6f1ee8f1c5684bba7056d3e0fc745f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76725714"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (Varsayılan bağımlı yük bayraklarını ayarla)

::: moniker range="vs-2015"

**/Dependentloadflag** seçeneği, Visual Studio 2017 veya üstünü gerektirir.

::: moniker-end

::: moniker range=">=vs-2017"

İşletim sistemi bir modülün statik olarak bağlı içeri aktarmalarını çözdüğünde kullanılan varsayılan yükleme bayraklarını ayarlar.

## <a name="syntax"></a>Sözdizimi

> **/Dependentloadflag**[ __:__ *load_flags*]

### <a name="arguments"></a>Arguments

*load_flags*<br/>
Modülün statik olarak bağlı içeri aktarma bağımlılıklarını çözümlerken uygulanacak yükleme bayraklarını belirten isteğe bağlı bir tamsayı değeri. Varsayılan değer 0'dır. Desteklenen bayrak değerlerinin listesi için bkz. [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)içindeki `LOAD_LIBRARY_SEARCH_*` girdileri.

## <a name="remarks"></a>Açıklamalar

İşletim sistemi bir modülün statik olarak bağlı içeri aktarmalarını çözdüğünde, [varsayılan arama sırasını](/windows/win32/dlls/dynamic-link-library-search-order)kullanır. Bu içeri aktarmaları çözümlemek için kullanılan arama yolunu değiştiren *load_flags* bir değer belirtmek için **/Dependentloadflag** seçeneğini kullanın. Desteklenen işletim sistemlerinde, `LOAD_LIBRARY_SEARCH` parametreleri kullanılırken [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexa) öğesine benzer şekilde statik içeri aktarma çözümleme arama sırasını değiştirir. *Load_flags*tarafından ayarlanan arama sırası hakkında daha fazla bilgi için, bkz. [LOAD_LIBRARY_SEARCH bayraklarını kullanarak arama sırası](/windows/win32/dlls/dynamic-link-library-search-order#search-order-using-load_library_search-flags).

Bu bayrak, bir [DLL planlatma saldırı](/windows/win32/dlls/dynamic-link-library-security) vektörünü daha zor hale getirmek için kullanılabilir. Örneğin, bir DLL 'ye statik olarak bağlanan bir uygulama düşünün:

- Saldırgan, uygulama dizini gibi içeri aktarma çözümleme arama yolunda aynı ada sahip bir DLL 'i daha önce de verebilir. Korunan dizinler daha zordur, ancak bir saldırganın değiştirmesine izin vermez.

- DLL uygulamada,%Windows%\System32 ve% Windows% dizinlerinde yoksa, içeri aktarma çözünürlüğü geçerli dizine düşer. Bir saldırgan, bir DLL 'yi orada bir de verebilir.

Her iki durumda da bağlantı seçeneğini belirtirseniz `/DEPENDENTLOADFLAG:0x800` (`LOAD_LIBRARY_SEARCH_SYSTEM32`bayrağının değeri), modül arama yolu%Windows%\System32 diziniyle sınırlandırılmıştır. Diğer dizinlerde planlayarak saldırılara karşı koruma sağlar. Daha fazla bilgi için bkz. [dinamik bağlantı kitaplığı güvenliği](/windows/win32/dlls/dynamic-link-library-security).

Herhangi bir DLL 'de **/Dependentloadflag** seçeneği tarafından ayarlanan değeri görmek için, [/loadConfig](loadconfig.md) seçeneğiyle [dumpbin](dumpbin-reference.md) komutunu kullanın.

**/Dependentloadflag** seçeneği, Visual Studio 2017 ' de yenidir. Yalnızca Windows 10 RS1 ve üzeri sürümlerde çalışan uygulamalar için geçerlidir. Bu seçenek, uygulamayı çalıştıran diğer işletim sistemleri tarafından yok sayılır.

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında DEPENDENTLOADFLAG bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler**' de seçeneği girin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC bağlayıcı seçenekleri](linker-options.md)
- [Yürütülebilir dosyayı DLL 'ye örtük olarak bağlama](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Hangi bağlama yönteminin kullanılacağını belirleme](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [Dinamik bağlantı kitaplığı arama sırası](/windows/win32/Dlls/dynamic-link-library-search-order)
- [Dinamik bağlantı kitaplığı güvenliği](/windows/win32/dlls/dynamic-link-library-security)

::: moniker-end
