---
title: "-E (Stdout'a Önişle) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /e
dev_langs:
- C++
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed083c960421ce17c0ce61036cd05191fc12c797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="e-preprocess-to-stdout"></a>/E (stdout'a Önişle)
C ve C++ kaynak dosyalarını preprocesses ve standart çıktı aygıtına önceden işlenmiş dosyalarını kopyalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/E  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlem, tüm önişlemci yönergeleri gerçekleştirilir, makrosu genişletmeleri gerçekleştirilir ve açıklamaları kaldırılır. Önceden işlenmiş çıkış açıklamaları korumak için kullanmak [/C (korumak açıklamaları sırasındaki)](../../build/reference/c-preserve-comments-during-preprocessing.md) derleyici seçeneği.  
  
 **/E** ekler `#line` başlangıcını ve bitişini eklenen her dosya ve koşullu derleme için önişlemci yönergeleri tarafından kaldırılan satırları geçici çıktıyı yönergeleri. Bu yönergeleri önceden işlenmiş dosyasındaki satırları numaralandırmak. Sonuç olarak, özgün kaynak dosyası yerine önceden işlenmiş dosyasına satır satır numaralarını işleme sonraki aşamaları sırasında oluşturulan hatalar bakın.  
  
 **/E** seçeneği derleme gizler. Derleme önceden işlenmiş dosyayı yeniden göndermeniz gerekir. **/E** de çıktı dosyalarını bastırır **/FA**, **/Fa**, ve **/Fm** seçenekleri. Daha fazla bilgi için bkz: [/FA, /Fa (listeleme dosyası)](../../build/reference/fa-fa-listing-file.md) ve [(/FM eşlem dosyasını Adlandır)](../../build/reference/fm-name-mapfile.md).  
  
 Gizlemek için `#line` yönergeleri kullanın [/EP (#line yönergeleri olmadan stdout'ta Önişle)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) bunun yerine seçeneği.  
  
 Bir dosyaya çok yerine önceden işlenmiş çıkış göndermek için `stdout`, kullanın [/P (dosyaya Önişle)](../../build/reference/p-preprocess-to-a-file.md) bunun yerine seçeneği.  
  
 Gizlemek için `#line` yönergeleri ve gönderme önceden işlenmiş çıktıyı bir dosyaya kullanmak **/P** ve **/EP** birlikte.  
  
 Önceden derlenmiş üst bilgileri ile kullanamazsınız **/E** seçeneği.  
  
 Ayrı bir dosyaya ön işlemesi tıklattığınızda alanları belirteçleri sonra gösterilen değil olduğunu unutmayın. Bu neden geçersiz bir programda veya sahip istenmeyen yan etkiler. Aşağıdaki programı başarıyla derler:  
  
```  
#define m(x) x  
m(int)main( )  
{  
   return 0;  
}  
```  
  
 Ancak, ile derleme yaparsanız:  
  
```  
cl -E test.cpp > test2.cpp  
```  
  
 `int main`Test2.cpp içinde yanlış olacak `intmain`.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler**kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırını preprocesses `ADD.C`, Yorumlar korur, ekler `#line` yönergeleri ve standart çıktı aygıtında sonucu görüntüler:  
  
```  
CL /E /C ADD.C  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)