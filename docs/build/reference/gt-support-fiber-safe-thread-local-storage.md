---
title: -GT (Fiber-güvenli iş parçacığı-yerel depolamayı destekle) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
dev_langs:
- C++
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eeec9ddce36777fc6fcb15b30a864f1c04a7b09b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700849"
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

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)