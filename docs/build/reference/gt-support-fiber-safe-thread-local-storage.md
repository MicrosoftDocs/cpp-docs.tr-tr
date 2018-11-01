---
title: /GT (Fiber-Güvenli İş Parçacığı-Yerel Depolamayı Destekle)
ms.date: 11/04/2016
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
ms.openlocfilehash: 22f9df6248b0ee1af2ef999bbf0dba2e716c9189
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557917"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT (Fiber-Güvenli İş Parçacığı-Yerel Depolamayı Destekle)

Statik iş parçacığı yerel depolama, diğer bir deyişle, ile ayrılmış veri kullanılarak yer ayrılmış veri için Fiber güvenliğini destekler `__declspec(thread)`.

## <a name="syntax"></a>Sözdizimi

```
/GT
```

## <a name="remarks"></a>Açıklamalar

Veri ile bildirilmiş `__declspec(thread)` iş parçacığı yerel depolama (TLS) dizisi başvurulur. TLS dizi, sistem her iş parçacığı için tutar adresleri dizisidir. Bu dizinin her adresi iş parçacığı yerel depolama veri konumunu sağlar.

Bir fiber bir yığın ve kayıt bağlam oluşur ve çeşitli iş parçacıklarında zamanlanabilir basit bir nesnedir. Bir fiber herhangi bir iş parçacığı üzerinde çalıştırabilirsiniz. Bir fiber takas ve daha sonra farklı bir iş parçacığını yeniden olduğundan, TLS dizi adresini gerekir önbelleğe veya ortak bir alt ifade bir işlev çağrısı arasında en iyi duruma getirilmiş (bkz [/Og (Global iyileştirmeler)](../../build/reference/og-global-optimizations.md) seçeneğini Ayrıntılar için). **/GT** gibi iyileştirmeler engeller.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **iyileştirme** özellik sayfası.

1. Değiştirme **Fiber uyumlu iyileştirmeleri etkinleştir** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)