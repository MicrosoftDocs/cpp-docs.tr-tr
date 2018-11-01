---
title: /Gy (İşlev Düzeyi Bağlamayı Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
ms.openlocfilehash: 1fd06b17ca0cfb1583b3014fb2c8f02b5e5a5437
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629924"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (İşlev Düzeyi Bağlamayı Etkinleştir)

Derleyicinin ayrı ayrı işlevleri paketlenmiş işlevler (Comdat'lar) biçiminde sağlar.

## <a name="syntax"></a>Sözdizimi

```
/Gy[-]
```

## <a name="remarks"></a>Açıklamalar

Bağlayıcı işlevleri hariç tutmak veya ayrı ayrı işlevleri bir DLL veya .exe dosyasını düzenlemek için comdat'ları olarak ayrı ayrı paketlenmesi gerekir.

Bağlayıcı seçeneği kullanabileceğiniz [OPT (iyileştirmeler)](../../build/reference/opt-optimizations.md) .exe dosyasından başvurulmayan paketlenmiş işlevleri hariç tutmak için.

Bağlayıcı seçeneği kullanabileceğiniz [/order (Put işlevleri Sırala)](../../build/reference/order-put-functions-in-order.md) .exe dosyasının belirli bir sırada paketlenmiş işlevler dahil edilecek.

Satır içi işlevleri her zaman çağrıları olarak örneği oluşturulur, paketlenmiş (hangi oluşursa, örneğin, satır içi kullanım kapalı veya bir işlevin adresi alın). Ayrıca, bir sınıf bildiriminde tanımlanan C++ üye işlevleri otomatik olarak paketlenir; diğer işlevler değildir ve onları paketlenmiş işlevler derlemek için bu seçeneği gereklidir.

> [!NOTE]
>  [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) seçeneği, Düzenle ve devam et için kullanılan otomatik olarak ayarlar **/Gy** seçeneği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **kod oluşturma** özellik sayfası.

1. Değiştirme **işlev düzeyi bağlamayı etkinleştir** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)