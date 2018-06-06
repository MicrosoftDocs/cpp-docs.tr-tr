---
title: / DEPENDENTLOADFLAG (kümesi varsayılan bağımlı yük flags)
description: /DEPENDENTLOADFLAG seçeneği varsayılan bayrakları LoadLibrary kullanılarak yüklenen DLL'ler için ayarlar
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
ms.openlocfilehash: 5a171f3c2edbbbf614a986ff78dd2405e734a1d1
ms.sourcegitcommit: d1f576a0f59678edc3d93508cf46485138332178
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753725"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/ DEPENDENTLOADFLAG (kümesi varsayılan bağımlı yük flags)

Ayarlar varsayılan yük bayrakları kullanılan `LoadLibrary` DLL'leri yüklemek için kullanılır.

## <a name="syntax"></a>Sözdizimi

> **/ DEPENDENTLOADFLAG**[**:**_loadflags_]

### <a name="arguments"></a>Arguments

|||
|-|-|
*loadflags*|İsteğe bağlı "C" Stili 16 bit tam sayı değeri ondalık, sıfır sekizli veya başında onaltılık `0x`, tümüne uygulamak için bağımlı yük bayrakları belirtir [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187) çağrıları. Varsayılan değer 0’dır.

## <a name="remarks"></a>Açıklamalar

Bu seçenek Visual Studio 2017 yenidir ve yalnızca Windows 10 RS1 ve sonraki sürümleri çalıştıran uygulamaları için geçerlidir. Bu seçenek, uygulama çalıştırma diğer işletim sistemleri tarafından göz ardı edilir.

Desteklenen işletim sistemlerinde, bu seçeneğin çağrıları değiştirmenin etkisi `LoadLibrary("dependent.dll")` denk için `LoadLibraryEx("dependent.dll", 0, loadflags)`. Çağrılar [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091) etkilenmez. Bu seçenek, uygulamanız tarafından yüklenen DLL'ler için yinelemeli olarak uygulanmaz.

Bu bayrak, DLL yerleştirmeyi saldırıları önlemek için kullanılabilir. Örneğin, bir uygulama kullanıyorsa `LoadLibrary` bağımlı DLL yüklemek için bir saldırganın aynı ada sahip bir DLL tarafından kullanılan arama yolu planlayın `LoadLibrary`, geçerli dizin gibi denetleneceği önce sistem dizinleri güvenli DLL arama modu ise devre dışı. Güvenli DLL arama modu daha sonra arama sırada kullanıcının geçerli dizinine yerleştirir ve Windows XP SP2 ve sonraki sürümlerinde varsayılan olarak etkindir. Daha fazla bilgi için bkz: [dinamik bağlantı kitaplığı arama sırası](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx).

Bağlantı seçeneği belirtirseniz, `/DEPENDENTLOADFLAG:0xA00` (Birleşik bayrakları değerini `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), DLL arama yolu güvenli DLL arama modu kullanıcının bilgisayarda devre dışı olsa bile, bir saldırganın daha zor olduğu korunan dizinler sınırlı ise değiştirin. Kullanılabilir bayrakları hakkında bilgi ve simgesel ve sayısal değerleri için bkz: *dwFlags* parametresi açıklamasında [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında DEPENDENTLOADFLAG bağlayıcı seçeneği ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Seçenek girin **ek seçenekler**.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](setting-linker-options.md)
- [Bağlayıcı Seçenekleri](linker-options.md)
- [Bir DLL'e örtük olarak bağlanma](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Hangi bağlama yöntemini kullanacağınızı belirleme](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187)
- [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091)
- [Dinamik bağlantı kitaplığı arama sırası](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)
