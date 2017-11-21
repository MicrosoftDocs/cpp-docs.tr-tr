---
title: "-Tanılama (tanılama derleyici seçenekleri) | Microsoft Docs"
ms.custom: 
ms.date: 11/11/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
dev_langs: C++
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4034e875c2feb52f938edeb4b05383d954476a21
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/Diagnostics (tanılama derleyici seçenekleri)  
  
Kullanım **/diagnostics** derleyici seçeneği hata ve uyarı konum bilgileri görüntüsünü belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/diagnostics:{caret|classic|column}
```  

## <a name="remarks"></a>Açıklamalar  
**/Diagnostics** derleyici seçeneği hata ve uyarı bilgilerini görünümünü denetler.  
  
**/Diagnostics:classic** sorun bulunduğu satır numarası raporları varsayılan seçenektir.  
  
**/Diagnostics:column** seçenek de sorun bulunduğu sütun içerir. Bu belirli bir dil yapı veya soruna neden olan karakter belirlemenize yardımcı olabilir.  
  
**/Diagnostics:caret** seçenek, burada sorunu bulundu ve bir şapka (^) burada sorunu algılandı kod satırı altında konuma yerleştirir sütun içerir.  
  
Bazı durumlarda, bir sorunun nerede oluştuğunu derleyici algılamaz unutmayın. Örneğin, diğer, beklenmeyen simgeleri karşılaştı kadar eksik noktalı algılanamayabilir. Sütun bildirilir ve düzeltme işareti burada derleyici bir şey her zaman, düzeltme yapmanız gereken burada olmayan yanlış olduğunu algılandı yerleştirilir.  
  
**/Diagnostics** Visual Studio 2017 başlangıç seçeneği kullanılabilir.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1. Projenizin açmak **özellik sayfaları** iletişim kutusu.   
  
2. Altında **yapılandırma özellikleri**, genişletin **C/C++** klasör ve **genel** özellik sayfası.  
  
3. Açılır liste denetiminde kullanmak **tanılama biçimi** alan bir tanılama seçmek için görüntü seçeneği. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydetmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)