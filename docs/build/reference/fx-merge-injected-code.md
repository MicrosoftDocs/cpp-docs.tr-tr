---
title: "-Fx (eklenen kodu Birleştir) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExpandAttributedSource
- /Fx
- VC.Project.VCCLCompilerTool.ExpandAttributedSource
dev_langs:
- C++
helpviewer_keywords:
- Fx compiler option [C++]
- -Fx compiler option [C++]
- injected code
- merging injected code
- /Fx compiler option [C++]
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d00f54a3f7842108a7a9b144fe27058996d3c58b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fx-merge-injected-code"></a>/Fx (Eklenen Kodu Birleştir)
Eklenen kod kaynağına birleştirilmiş ile her kaynak dosyasının bir kopyasını oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Fx  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Özgün bir kaynak dosyasından birleştirilmiş kaynak dosyası ayırt etmek için **/Fx** .mrg uzantı arasında dosya adı ve dosya uzantısı ekler. Örneğin, bir dosya atanmış kodu içeren MyCode.cpp adlı ve ile oluşturulan **/Fx** aşağıdaki kodu içeren MyCode.mrg.cpp adlı bir dosya oluşturur:  
  
```  
//+++ Start Injected Code  
[no_injected_text(true)];      // Suppress injected text, it has   
                               // already been injected  
#pragma warning(disable: 4543) // Suppress warnings about skipping   
                               // injected text  
#pragma warning(disable: 4199) // Suppress warnings from attribute   
                               // providers  
//--- End Injected Code  
```  
  
 Bir .mrg dosyasında nedeniyle bir öznitelik eklendi kod aşağıdaki gibi sınırlı:  
  
```  
//+++ Start Injected Code  
...  
//--- End Injected Code  
```  
  
 [No_injected_text](../../windows/no-injected-text.md) reinjected metin .mrg dosyanın derleme için izin veren bir .mrg dosyasında özniteliği katıştırılmış.  
  
 .Mrg kaynak dosyası derleyici tarafından eklenen kaynak kodu gösterimi olması amaçlanmıştır bilmeniz gerekir. .Mrg dosyası değil derleme veya tam olarak özgün kaynak dosyası olarak çalıştırın.  
  
 Makroları .mrg dosyasında genişletilmiş değil.  
  
 Eklenen kodu kullanan bir üstbilgi dosyası programınızı içeriyorsa, **/Fx** oluşturur bir. Bu üstbilgisi mrg.h dosya. **/FX** değil birleştirme eklenen kodu kullanmayın dosyalarını içermez.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **çıktı dosyaları** özellik sayfası.  
  
4.  Değiştirme **öznitelikli kaynak genişletin** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)