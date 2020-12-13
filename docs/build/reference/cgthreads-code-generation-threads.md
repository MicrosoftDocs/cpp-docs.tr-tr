---
description: 'Hakkında daha fazla bilgi edinin: `/cgthreads` (kod oluşturma iş parçacıkları)'
title: /cgthreads (Kod oluşturma iş parçacıkları)
ms.date: 07/31/2020
f1_keywords:
- /cgthreads
helpviewer_keywords:
- /cgthreads compiler option (C++)
- -cgthreads compiler option (C++)
- cgthreads compiler option (C++)
- cgthreads
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
ms.openlocfilehash: 41f1e2ab6aa9263a2faf81e83d47db953819827a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182482"
---
# <a name="cgthreads-code-generation-threads"></a>`/cgthreads` (Kod oluşturma iş parçacıkları)

İyileştirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını ayarlar.

## <a name="syntax"></a>Söz dizimi

> **`/cgthreads1`**\
> **`/cgthreads2`**\
> **`/cgthreads3`**\
> **`/cgthreads4`**\
> **`/cgthreads5`**\
> **`/cgthreads6`**\
> **`/cgthreads7`**\
> **`/cgthreads8`**

## <a name="arguments"></a>Bağımsız değişkenler

**`cgthreadsN`**\
cl.exe kullanılacak en fazla iş parçacığı sayısı ( *N* , 1 ile 8 arasında bir sayıdır).

## <a name="remarks"></a>Açıklamalar

**`cgthreads`** Seçeneği, derlemenin iyileştirme ve kod oluşturma aşamaları için paralel olarak kullanılan cl.exe en fazla iş parçacığı sayısını belirtir. **`cgthreads`** Ve *sayı* bağımsız değişkeni arasında boşluk olmadığına dikkat edin. Varsayılan olarak, cl.exe belirtildiği gibi dört iş parçacığı kullanır **`/cgthreads4`** . Daha fazla işlemci çekirdeği varsa, daha büyük bir *sayı* değeri derleme sürelerini iyileştirebilir. Bu seçenek özellikle [ `/GL` (tüm program iyileştirmesi)](gl-whole-program-optimization.md)ile birleştirildiğinde kullanışlıdır.

Yapı için birden çok paralellik düzeyi belirtilebilir. msbuild.exe anahtarı, **`/maxcpucount`** paralel olarak çalıştırılabilen MSBuild işlemlerinin sayısını belirtir. [ `/MP` (Birden çok işlemle derleme)](mp-build-with-multiple-processes.md) derleyici bayrağı, kaynak dosyaları aynı anda derleyen cl.exe işlem sayısını belirtir. **`cgthreads`** Seçeneği, her bir cl.exe işlemi tarafından kullanılan iş parçacığı sayısını belirtir. İşlemci, işlemci çekirdekleri ile aynı anda yalnızca çok sayıda iş parçacığı çalıştırabilir. Bu seçeneklerin tümü için aynı anda daha büyük değerler belirtmek yararlı değildir ve bu, onay açısından üretken olabilir. Projeleri paralel olarak oluşturma hakkında daha fazla bilgi için bkz. [paralel olarak birden çok proje oluşturma](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **`cgthreadsN`** , *`N`* 1 ile 8 arasında bir değer olan dahil edilecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)
