---
title: /GA (Windows Uygulaması için İyileştir)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
ms.openlocfilehash: 04f8e9e19e5224c1a03ab1c7679d37b7bb8d1389
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503344"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Windows Uygulaması için İyileştir)

İş parçacığı yerel depolama (TLS) değişkenleri erişmek için bir .exe dosyası için daha verimli kod sonuçlanır.

## <a name="syntax"></a>Sözdizimi

```
/GA
```

## <a name="remarks"></a>Açıklamalar

**/GA** veri erişimi ile bildirilmiş [gt;__declspec(thread)](../../cpp/declspec.md) Windows tabanlı bir programı. Bu seçenek ayarlandığında [__tls_index](/windows/desktop/ProcThread/thread-local-storage) makrosu 0 olarak varsayılır.

Kullanarak **/GA** için bir DLL hatalı kod oluşturma neden olabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)