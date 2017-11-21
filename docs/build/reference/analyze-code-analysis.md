---
title: "-analyze (kod çözümleme) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
dev_langs: C++
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b640d042f1f8a30246f4d7277a8a5b001722acd9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="analyze-code-analysis"></a>/analyze (Kod Çözümleme)
Kod analizini ve denetim seçeneklerini etkinleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only]  
```  
  
## <a name="arguments"></a>Arguments  
 /analyze  
 Varsayılan modda analizi açar. Analiz çıkış gider **çıkış** pencere gibi diğer hata iletileri. Kullanım **/ analyze-** açıkça analiz devre dışı bırakma.  
  
 /analyze:WX-  
 Belirtme **/ analyze: WX -** Kod Analizi uyarıları anlamına gelir değil kabul edilir hata olarak kullanarak derlediğinizde **/WX**. Daha fazla bilgi için bkz: [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, wln, /wd, / biz, /wo, /Wv, /WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md).  
  
 / analyze: günlük`filename`  
 Ayrıntılı Çözümleyicisi sonuçları tarafından belirtilen dosya için XML olarak yazılır `filename`.  
  
 /analyze:quiet  
 Çözümleyici çıktısına kapatır **çıkış** penceresi.  
  
 / analyze: stacksıze`number`  
 `number` Bu seçenek ile kullanılır parametre yığın çerçevesi hangi uyarı için bayt cinsinden boyutu belirtir [C6262](/visualstudio/code-quality/c6262) oluşturulur. Bu parametre belirtilmezse, yığın çerçevesinin boyutu varsayılan olarak 16 KB olur.  
  
 / analyze: max_paths`number`  
 `number` Bu seçenek ile kullanılan parametre çözümlenecek kod yollarının en fazla sayısını belirtir. Bu parametre belirtilmezse, sayı varsayılan olarak 256 olur. Daha büyük değerler daha kapsamlı denetleme gerçekleştirir ancak çözümleme uzun sürebilir.  
  
 /analyze:only  
 Genellikle, derleyici kodu oluşturur ve çözümleyiciyi çalıştırdıktan sonra biraz daha sözdizimi denetimi yapar. **/ Analyze: yalnızca** seçeneği bu kod oluşturma geçişi devre dışı bırakır; Bu analiz hızlandırır ancak derleme hataları ve kod oluşturma geçişi derleyici tarafından bulunmuş uyarıları yayılan değil. Programda kod oluşturma hataları varsa, analiz sonuçları güvenilir olmayabilir. Bu nedenle, bu seçeneği yalnızca kod oluşturma sözdizimi denetimini hatasız şekilde geçerse kullanmanızı öneririz.  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [C/C++ genel bakış için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) ve [C/C++ uyarıları için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **Kod Analizi** düğümü.  
  
4.  Seçin **genel** özellik sayfası.  
  
5.  Bir veya daha fazla değişiklik **Kod Analizi** özellikleri.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)