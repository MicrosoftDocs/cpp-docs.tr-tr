---
title: / DEPENDENTLOADFLAG (kümesi varsayılan bağımlı yük bayrakları)
description: /DEPENDENTLOADFLAG seçeneği varsayılan bayrakları LoadLibrary kullanılarak yüklenen DLL'ler için ayarlar.
ms.custom: ''
ms.date: 05/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- dependentloadflag
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94f7667d7da8d8e9cd7ef38cb01d0f03b0da82e3
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42466379"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/ DEPENDENTLOADFLAG (kümesi varsayılan bağımlı yük bayrakları)

Kullanılan ayarlar varsayılan yük bayrakları `LoadLibrary` DLL'lerini yüklemek için kullanılır.

## <a name="syntax"></a>Sözdizimi

> **/ DEPENDENTLOADFLAG**[**:**_loadflags_]

### <a name="arguments"></a>Arguments

|||
|-|-|
*loadflags*|İsteğe bağlı "C"-style 16 bit tam sayı değeri ondalık, önüne sıfır getirilmiş sekizlik veya onaltılık bir lider olan `0x`, Tümüne Uygula için bağımlı yük bayrakları belirtir [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187) çağırır. Varsayılan değer 0’dır.

## <a name="remarks"></a>Açıklamalar

Bu seçenek, Visual Studio 2017'de yenidir ve yalnızca Windows 10 RS1 ve üzeri sürümlerde çalışan uygulamalar için geçerlidir. Bu seçenek, uygulamayı çalıştıran diğer işletim sistemleri tarafından göz ardı edilir.

Desteklenen işletim sistemlerinde bu seçeneğin çağrıları değiştirmenin etkisi `LoadLibrary("dependent.dll")` denk için `LoadLibraryEx("dependent.dll", 0, loadflags)`. Çağrılar [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091) etkilenmez. Bu seçenek, uygulamanız tarafından yüklenen DLL'ler için yinelemeli olarak uygulanmaz.

Bu bayrak, DLL saldırıları yerleştirmeyi önlemek için kullanılabilir. Örneğin, bir uygulama kullanıyorsa `LoadLibrary` bağımlı DLL yüklemek için bir saldırganın aynı ada sahip bir DLL tarafından kullanılan arama yolu bitki `LoadLibrary`, geçerli dizini gibi hangi işaretli önce sistem dizinleri güvenli DLL arama modu ise devre dışı. Güvenli DLL arama modu, kullanıcının geçerli dizin daha sonra arama sırada yerleştirir ve Windows XP SP2 ve sonraki sürümlerde varsayılan olarak etkindir. Daha fazla bilgi için [dinamik bağlantı kitaplığı arama sırası](/windows/desktop/Dlls/dynamic-link-library-search-order).

Bağlantı seçeneğini belirtirseniz `/DEPENDENTLOADFLAG:0xA00` (Birleşik bayrak değerini `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), sonra güvenli DLL arama modu, kullanıcının bilgisayarında devre dışı bırakılmış olsa bile, DLL arama yolu için bir saldırganın daha zor olan korunan dizinler sınırlıdır. değiştirin. Kullanılabilir bayrakları hakkında bilgi ve sembolik ve sayısal değerleri için bkz: *CertOpenStore* parametresi açıklamasında [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında DEPENDENTLOADFLAG bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. De seçeneği girin **ek seçenekler**.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](setting-linker-options.md)
- [Bağlayıcı Seçenekleri](linker-options.md)
- [DLL'ye örtük olarak bağlama](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Hangi bağlama yönteminin kullanılacağını belirleme](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187)
- [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091)
- [Dinamik bağlantı kitaplığı arama sırası](/windows/desktop/Dlls/dynamic-link-library-search-order)
