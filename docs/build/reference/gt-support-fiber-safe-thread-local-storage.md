---
title: /GT (Fiber-güvenli iş parçacığı-yerel depolamayı destekle)
description: MSVC derleyici seçeneği/GT, iş parçacığı yerel depolama verileri için güvenli iyileştirmelere izin vermez.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
ms.openlocfilehash: 1b1d9f6514cec8c3d247f86be063f2ac3e0dfe72
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180818"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>`/GT`(Fiber-güvenli iş parçacığı-yerel depolamayı destekle)

Statik iş parçacığı yerel depolama, diğer bir deyişle ile ayrılan veriler kullanılarak ayrılan veriler için fiber güvenliği destekler `__declspec(thread)` .

## <a name="syntax"></a>Sözdizimi

> **`/GT`**

## <a name="remarks"></a>Açıklamalar

İle belirtilen verilere `__declspec(thread)` , bir iş parçacığı yerel depolama (TLS) dizisi aracılığıyla başvurulur. TLS dizisi, sistemin her iş parçacığı için sakladığı adreslerin bir dizisidir. Bu dizideki her adres, iş parçacığı yerel depolama verilerinin konumunu verir.

Fiber bir yığın ve YAZMAÇ bağlamından oluşan basit bir nesnedir ve çeşitli iş parçacıklarında zamanlanabilir. Bir fiber, herhangi bir iş parçacığında çalıştırılabilir. Bir fiber daha sonra farklı bir iş parçacığında takas edilen ve yeniden başlatılan için, derleyici TLS dizisinin adresini önbelleğe almaz veya bir işlev çağrısında ortak bir alt ifade olarak en iyi hale getirir. **`/GT`** Bu iyileştirmeleri engeller.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **iyileştirme** özellik sayfasını seçin.

1. **Fiber güvenli Iyileştirmeleri etkinleştir** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)
