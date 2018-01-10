---
title: "-ZW (Windows çalışma zamanı derlemesi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
dev_langs: C++
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 75f46c2eaaa42f473e02bc553dd06b86cd5bbc98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (Windows Çalışma Zamanı Derlemesi)
Kuyruktaki kaynak desteklemek için kodu [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]) oluşturulması için [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar.  
  
 Kullandığınızda **/ZW** derlemek için her zaman belirtmeniz **/EHsc** de.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
/ZW /EHsc  
/ZW:nostdlib /EHsc  
```  
  
## <a name="arguments"></a>Arguments  
 nostdlib  
 Bu Platform.winmd, Windows.Foundation.winmd ve Windows Meta veriler (.winmd) dosyaları otomatik olarak derlemede bulunmayan diğer varsayılan gösterir. Bunun yerine, kullanmanız gerekir [/FU (zorlanan adı #using)](../../build/reference/fu-name-forced-hash-using-file.md) Windows meta veri dosyaları açıkça belirtmek için derleyici seçeneği.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirttiğinizde **/ZW** derleyici seçeneği bu özellikleri destekler:  
  
-   Gerekli meta veri dosyaları, ad alanları, veri türleri ve Windows çalışma zamanı'nda yürütmek için uygulamanızı gerektirir işlevleri.  
  
-   Otomatik başvuru sayımı Windows çalışma zamanı nesnelerinin ve otomatik başvuru sayısı sıfır olarak gittiğinde bir nesnenin atılıyor.  
  
 Incremental bağlayıcı kullanılarak .obj dosyaları dahil Windows meta verileri desteklemediğinden **/ZW** seçeneği [/GM derlemeyi (etkinleştirmek en az yeniden derleme)](../../build/reference/gm-enable-minimal-rebuild.md) seçeneği ile uyumlu **/ZW** .  
  
 Daha fazla bilgi için bkz: [Visual C++ dil başvurusu](../../cppcx/visual-c-language-reference-c-cx.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)