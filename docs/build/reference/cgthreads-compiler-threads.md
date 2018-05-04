---
title: -CGTHREADS (derleyici iş parçacıkları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5905c29170a7ad636420a9bcdbd282ccfc2e7ec3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS (Derleyici İş Parçacıkları)
Bağlama zamanı kodu oluşturma belirtildiğinde en iyi duruma getirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/CGTHREADS:[1-8]  
```  
  
## <a name="arguments"></a>Arguments  
 sayı  
 Cl.exe kullanılacak aralık 1-8 iş parçacığı sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 **/Cgthreads** seçeneği derleme bağlama zamanı zaman için en iyi duruma getirme ve kod oluşturma aşamaları paralel olarak iş parçacığı cl.exe kullandığı üst sınırını belirtir kod oluşturma ([/LTCG](../../build/reference/ltcg-link-time-code-generation.md)) değil Belirtilen. Varsayılan olarak, dört iş parçacığı cl.exe kullanır gibi **/CGTHREADS:4** belirtildi. Daha fazla işlemci çekirdeği mevcutsa, büyük bir `number` değeri derleme sürelerini geliştirebilir.  
  
 Birden çok düzeyi paralellik bir derleme için belirtilebilir. Msbuild.exe anahtar **/maxcpucount** paralel olarak çalıştırılabilir MSBuild işlemlerin sayısını belirtir. [/MP (birden çok süreçle derleme)](../../build/reference/mp-build-with-multiple-processes.md) derleyici bayrağı aynı anda kaynak dosyalarını derlemek cl.exe işlem sayısını belirtir. [/Cgthreads](../../build/reference/cgthreads-code-generation-threads.md) derleyici seçeneği her cl.exe işlemi tarafından kullanılan iş parçacığı sayısını belirtir. İşlemci işlemci çekirdeği olduğu kadar iş parçacığı aynı anda yalnızca çalışabildiğinden bu seçeneklerin tümü için daha büyük değerler aynı anda belirtmek yararlı değildir ve ters etki olabilir. Paralel olarak projeler oluşturma hakkında daha fazla bilgi için bkz: [yapı paralel olarak birden çok proje](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **yapılandırma özellikleri**, **bağlayıcı** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Değiştirme **ek seçenekler** eklenecek özellik **/cgthreads:**`number`, burada `number` 8 ile 1 arasında bir değer olan ve ardından **Tamam**.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)