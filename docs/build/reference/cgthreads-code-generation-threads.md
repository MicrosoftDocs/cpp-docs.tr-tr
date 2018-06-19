---
title: -cgthreads (kod oluşturma iş parçacıkları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /cgthreads
dev_langs:
- C++
helpviewer_keywords:
- /cgthreads compiler option (C++)
- -cgthreads compiler option (C++)
- cgthreads compiler option (C++)
- cgthreads
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32c88fe00958a0fc767d8a316bfe4edab7b4fb0e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372448"
---
# <a name="cgthreads-code-generation-threads"></a>/cgthreads (Kod Oluşturma İş Parçacıkları)
En iyi duruma getirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/cgthreads[1-8]  
```  
  
## <a name="arguments"></a>Arguments  
 sayı  
 Cl.exe kullanılacak aralık 1-8 iş parçacığı sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 **/Cgthreads** seçeneği, iş parçacıkları cl.exe üst sınırını kullanır paralel olarak en iyi duruma getirme ve kod için derleme aşamaları nesil belirtir. Boşluk arasında olabilir fark **/cgthreads** ve `number` bağımsız değişkeni. Varsayılan olarak, dört iş parçacığı cl.exe kullanır gibi **/cgthreads4** belirtildi. Daha fazla işlemci çekirdeği mevcutsa, büyük bir `number` değeri derleme sürelerini geliştirebilir. İle birleştirildiğinde bu seçenek özellikle yararlıdır [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).  
  
 Birden çok düzeyi paralellik bir derleme için belirtilebilir. Msbuild.exe anahtar **/maxcpucount** paralel olarak çalıştırılabilir MSBuild işlemlerin sayısını belirtir. [/MP (birden çok süreçle derleme)](../../build/reference/mp-build-with-multiple-processes.md) derleyici bayrağı aynı anda kaynak dosyalarını derlemek cl.exe işlem sayısını belirtir. **/Cgthreads** seçeneği her cl.exe işlemi tarafından kullanılan iş parçacığı sayısını belirtir. İşlemci işlemci çekirdeği olduğu kadar iş parçacığı aynı anda yalnızca çalışabildiğinden bu seçeneklerin tümü için daha büyük değerler aynı anda belirtmek yararlı değildir ve ters etki olabilir. Paralel olarak projeler oluşturma hakkında daha fazla bilgi için bkz: [yapı paralel olarak birden çok proje](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **yapılandırma özellikleri**, **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Değiştirme **ek seçenekler** eklenecek özellik **/cgthreads**`N`, burada `N` 8 ile 1 arasında bir değer olan ve ardından **Tamam**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)