---
description: Daha fazla bilgi edinin:/CGTHREADS (derleyici Iş parçacıkları)
title: /CGTHREADS (Derleyici İş Parçacıkları)
ms.date: 11/04/2016
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
ms.openlocfilehash: 71c5031c7013ec6f8ddad153d9cc16bee2004751
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179258"
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS (Derleyici İş Parçacıkları)

Bağlantı zamanı kod üretimi belirtildiğinde iyileştirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını ayarlar.

## <a name="syntax"></a>Söz dizimi

```
/CGTHREADS:[1-8]
```

## <a name="arguments"></a>Bağımsız değişkenler

*sayısından*<br/>
cl.exe için kullanılacak en fazla iş parçacığı sayısı, 1 ile 8 arasındadır.

## <a name="remarks"></a>Açıklamalar

**/CGTHREADS** seçeneği, bağlantı zamanı kod üretimi ([/LTCG](ltcg-link-time-code-generation.md)) belirtildiğinde derleme için en iyi duruma getirme ve kod oluşturma aşamaları için paralel olarak kullanılan cl.exe en fazla iş parçacığı sayısını belirtir. Varsayılan olarak, cl.exe **/CGTHREADS: 4** belirtilmişse olduğu gibi dört iş parçacığı kullanır. Daha fazla işlemci çekirdeği varsa, daha büyük bir `number` değer derleme sürelerini iyileştirebilir.

Yapı için birden çok paralellik düzeyi belirtilebilir. **/Maxcpucount** msbuild.exe anahtarı paralel olarak çalıştırılabilen MSBuild işlemlerinin sayısını belirtir. [/MP (birden çok Işlemle derleme)](mp-build-with-multiple-processes.md) derleyici bayrağı, kaynak dosyaları aynı anda derleyen cl.exe işlem sayısını belirtir. [/CGTHREADS](cgthreads-code-generation-threads.md) derleyici seçeneği, her bir cl.exe işlemi tarafından kullanılan iş parçacığı sayısını belirtir. İşlemci, işlemci çekirdekleri ile aynı anda yalnızca çok sayıda iş parçacığı çalıştırabildiğinden, bu seçeneklerin tümü için aynı anda daha büyük değerler belirtmek yararlı değildir ve bu, önlem olarak üretken olabilir. Projeleri paralel olarak oluşturma hakkında daha fazla bilgi için bkz. [paralel olarak birden çok proje oluşturma](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **bağlayıcı** klasörü ' nü seçin.

1. **Komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** özelliğini **/CGTHREADS:** `number` , burada `number` 1 ile 8 arasında bir değer olacak şekilde değiştirin ve ardından **Tamam**' ı seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı seçenekleri](linker-options.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)
