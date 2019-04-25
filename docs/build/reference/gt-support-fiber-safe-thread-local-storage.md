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
ms.openlocfilehash: 417ac00a446f773a424553e42478a4f0cf58efc6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291814"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT (Fiber-Güvenli İş Parçacığı-Yerel Depolamayı Destekle)

Statik iş parçacığı yerel depolama, diğer bir deyişle, ile ayrılmış veri kullanılarak yer ayrılmış veri için Fiber güvenliğini destekler `__declspec(thread)`.

## <a name="syntax"></a>Sözdizimi

```
/GT
```

## <a name="remarks"></a>Açıklamalar

Veri ile bildirilmiş `__declspec(thread)` iş parçacığı yerel depolama (TLS) dizisi başvurulur. TLS dizi, sistem her iş parçacığı için tutar adresleri dizisidir. Bu dizinin her adresi iş parçacığı yerel depolama veri konumunu sağlar.

Bir fiber bir yığın ve kayıt bağlam oluşur ve çeşitli iş parçacıklarında zamanlanabilir basit bir nesnedir. Bir fiber herhangi bir iş parçacığı üzerinde çalıştırabilirsiniz. Bir fiber takas ve daha sonra farklı bir iş parçacığını yeniden olduğundan, TLS dizi adresini gerekir önbelleğe veya ortak bir alt ifade bir işlev çağrısı arasında en iyi duruma getirilmiş (bkz [/Og (Global iyileştirmeler)](og-global-optimizations.md) seçeneğini Ayrıntılar için). **/GT** gibi iyileştirmeler engeller.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **iyileştirme** özellik sayfası.

1. Değiştirme **Fiber uyumlu iyileştirmeleri etkinleştir** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
