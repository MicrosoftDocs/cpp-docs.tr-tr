---
title: "-Qfast_transcendentals (hızlı Soyutları zorla) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Qfast_transcendentals
dev_langs:
- C++
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8d7e8de17c096d061653b469207352be4b9b8bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (Hızlı Soyutları Zorla)
Soyut işlevleri için satır içi kod oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Qfast_transcendentals  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu derleyici seçeneği yürütme hızını artırmak için satır içi kod dönüştürülecek soyut işlevleri zorlar. Bu seçenek yalnızca ile eşleştirilmiş olduğunda bir etkisi **/fp: dışında** veya **/fp: kesin**. Soyut işlevleri için satır içi kod oluşturma altındaki varsayılan davranışı bulunmakta **/fp:fast**.  
  
 Bu seçenek ile uyumsuz **/fp: katı**. Bkz: [/fp (Floating-Point davranış belirtin)](../../build/reference/fp-specify-floating-point-behavior.md) kayan nokta derleyici seçenekleri hakkında daha fazla bilgi.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)