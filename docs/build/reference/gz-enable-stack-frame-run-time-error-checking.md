---
title: "-GZ (etkinleştirmek yığın çerçevesi çalışma zamanı hata denetimini) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /gz
dev_langs: C++
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f3e4dc59154d64d79db0f4d15471b51ce67bed58
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ (Yığın Çerçevesi Çalışma Zamanı Hata Denetimini Etkinleştir)
Aynı işlemleri gerçekleştirir [eş yordamlarla/RTC (çalışma zamanı hata denetler)](../../build/reference/rtc-run-time-error-checks.md) seçeneği. Kullanım dışı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/GZ  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/GZ** bir nonoptimized içinde yalnızca için kullanılır ([/Od (devre dışı bırak (Hata Ayıkla))](../../build/reference/od-disable-debug.md)) oluşturun.  
  
 **/GZ** bu yana Visual Studio 2005; kullanım dışı kullanmak [eş yordamlarla/RTC (çalışma zamanı hata denetler)](../../build/reference/rtc-run-time-error-checks.md) yerine. Kullanım dışı derleyici seçeneklerinin listesi için bkz: **kullanım dışı ve kaldırılmış derleyici seçenekleri** içinde [derleyici seçenekleri kategoriye göre listelenen](../../build/reference/compiler-options-listed-by-category.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)