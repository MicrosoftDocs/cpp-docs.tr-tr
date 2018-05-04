---
title: -E (Stdout'a Önişle) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f9105c5c75bc4695d0b00debdff49acf78690b1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
  
 `int main` Test2.cpp içinde yanlış olacak `intmain`.  
  
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