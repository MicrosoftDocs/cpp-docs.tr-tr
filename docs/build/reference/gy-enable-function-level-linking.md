---
title: "-Gy (etkinleştir işlev düzeyi bağlantılandırma) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
dev_langs: C++
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e7d83e4409d9c46c926859f39029ea68f2411def
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="gy-enable-function-level-linking"></a>/Gy (İşlev Düzeyi Bağlamayı Etkinleştir)
Paketlenmiş işlevler (COMDATs) biçiminde paket tekil işlevler için derleyicisi tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Gy[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlayıcı işlevler hariç tutma veya tek bir DLL veya .exe dosyası işlevlerde sipariş için COMDATs olarak ayrı ayrı paketlenmesi gerektirir.  
  
 Bağlayıcı seçeneği kullanabilirsiniz [OPT (iyileştirmeler)](../../build/reference/opt-optimizations.md) .exe dosyasından başvurulmayan paketlenmiş işlevler hariç tutulacak.  
  
 Bağlayıcı seçeneği kullanabilirsiniz [/ORDER (Put işlevleri Sırala)](../../build/reference/order-put-functions-in-order.md) .exe dosyası belirtilen sırada paketlenmiş işlevler eklemek için.  
  
 Satır içi işlevler her zaman çağrıları oluşturulur, paketlenmiş (hangi oluşursa, örneğin, satır içi kullanım dışı ya da bir işlev adresi alın). Ayrıca, C++ üye işlevleri sınıfı bildiriminde tanımlanan otomatik olarak paketlenir; diğer işlevleri değildir ve paketlenmiş işlevler derlemek için bu seçeneği gereklidir.  
  
> [!NOTE]
>  [/Zı](../../build/reference/z7-zi-zi-debug-information-format.md) Düzenle ve devam et, için kullanılan seçeneği, otomatik olarak ayarlar **/Gy** seçeneği.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **kod oluşturma** özellik sayfası.  
  
4.  Değiştirme **işlev düzeyi bağlamayı etkinleştir** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)