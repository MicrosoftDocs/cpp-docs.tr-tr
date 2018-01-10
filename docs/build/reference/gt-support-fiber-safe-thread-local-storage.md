---
title: "-GT (Fiber-güvenli iş parçacığı-yerel depolamayı destekle) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
dev_langs: C++
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86c027a1796f42d7b2932f68aff00136ee0d217f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT (Fiber-Güvenli İş Parçacığı-Yerel Depolamayı Destekle)
Statik iş parçacığı yerel depolama, diğer bir deyişle, ile ayrılmış veri kullanılarak ayrılmış veriler için Fiber güvenliği destekleyen `__declspec(thread)`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/GT  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Veri bildirilen ile `__declspec(thread)` bir iş parçacığı yerel depolaması (TLS) dizisi başvurulur. Her iş parçacığı için sistem tutar adresler dizisinin TLS dizisidir. Bu dizinin her adresi iş parçacığı yerel depolama verilerin konumunu sağlar.  
  
 Bir fiber bir yığını ve bir kayıt bağlamı oluşur ve çeşitli iş parçacıklarında zamanlanmış basit bir nesnedir. Bir fiber hiçbir iş parçacığı üzerinde çalışabilir. Bir fiber takas ve daha sonra farklı bir iş parçacığı yeniden çünkü TLS dizi adresini gerekir değil önbelleğe alınacak veya işlev çağrısı arasında ortak bir alt en iyi duruma getirilmiş (bkz [/Og (Global iyileştirmeler)](../../build/reference/og-global-optimizations.md) seçenek için Ayrıntılar için). **/GT** gibi en iyi duruma getirme engeller.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **en iyi duruma getirme** özellik sayfası.  
  
4.  Değiştirme **etkinleştirmek Fiber-güvenli iyileştirmeler** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)