---
title: "-Yu (önceden derlenmiş başlık dosyasını) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /yu
dev_langs: C++
helpviewer_keywords:
- Yu compiler option [C++]
- /Yu compiler option [C++]
- -Yu compiler option [C++]
- PCH files, use existing
- .pch files, use existing
- precompiled header files, use existing
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c83f159882b9ed6fcfe5557c150413303c401dda
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="yu-use-precompiled-header-file"></a>/Yu (Önceden Derlenmiş Üst Bilgi Dosyasını Kullanma)
Geçerli derlemedeki varolan önceden derlenmiş üst bilgi (.pch) dosyasını kullanmak için derleyicisi bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Yu[filename]  
```  
  
## <a name="arguments"></a>Arguments  
 *Dosya adı*  
 Kullanılarak kaynak dosyasında bulunan bir üstbilgi dosyası adı bir **#include** önişlemci yönergesi.  
  
## <a name="remarks"></a>Açıklamalar  
 İçerme dosyası adını her ikisi için aynı olmalıdır **/Yc** önceden derlenmiş üst bilgi ve tüm oluşturur seçeneği sonraki **/Yu** önceden derlenmiş üst bilgi kullanımını gösteren seçeneği.  
  
 İçin **/Yc**, `filename` noktada belirtir hangi ön derlemesi durdurur; ancak tüm kod derleyici işlemini gerçekleştirir `filename` ve içerme dosyası ve bir uzantı temel adı kullanılarak elde edilen önceden derlenmiş üst bilgi adları .PCH.  
  
 .Pch dosyası kullanılarak oluşturulmuş olması gerekir **/Yc**.  
  
 Derleyici .h dosyası olarak derlenmiş önce gerçekleşen tüm kodu değerlendirir. Bunu yalnızca ötesine atlar **#include** .h dosyayla ilişkili yönergesi .pch dosyasında yer alan kodu kullanır ve sonra tüm kodu derler `filename`.  
  
 Komut satırında arasında boşluk bulunmamalıdır **/Yu** ve `filename`.  
  
 Belirttiğinizde **/Yu** seçeneği olmadan bir dosya adı, kaynak programınızı içermelidir bir [#pragma hdrstop](../../preprocessor/hdrstop.md) pragma .pch dosyası önceden derlenmiş üst bilgi dosya adını belirtir. Bu durumda, derleyici tarafından adlı önceden derlenmiş üst bilgi (.pch dosyası Adlandır) kullanacağı [/Fp (adı. PCH dosyası)](../../build/reference/fp-name-dot-pch-file.md). Derleyici bu pragma konuma atlar, pragma tarafından belirtilen önceden derlenmiş üst bilgi dosyasından derlenmiş durumunu geri yükler ve pragma aşağıdaki kodu derler. Varsa **#pragma hdrstop** , temel bir .pch uzantısına sahip kaynak dosya adını türetilmiş bir ada sahip bir dosya derleyici arar bir dosya adı belirtmiyor. Aynı zamanda **/Fp** seçeneği farklı .pch dosyası belirtin.  
  
 Belirtirseniz **/Yu** seçeneği bir dosya adı ve belirtmek başarısız bir **hdrstop** pragma, bir hata iletisi oluşturulur ve derleme başarısız olur.  
  
 Varsa **/Yc** `filename` ve **/Yu** `filename` seçenekleri aynı komut satırında oluşur ve her ikisi de aynı dosya adına başvuru **/Yc** `filename` alır Öncelik, kadar tüm kodu önceden derlemek ve adlandırılmış dosya dahil olmak üzere. Bu özellik, derleme görevleri dosyaları yazma basitleştirir.  
  
 .PCH dosyaları makine ortamı hakkında bilgi bilgilerinin yanı sıra bellek adresi program içerdiğinden, yalnızca oluşturulduğu makinedeki bir pch dosyası kullanmanız gerekir.  
  
 Önceden derlenmiş üst bilgileri hakkında daha fazla bilgi için bkz:  
  
-   [/Y (önceden derlenmiş başlıklar)](../../build/reference/y-precompiled-headers.md)  
  
-   [Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Belirtin [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) projenizdeki .cpp dosyada.  
  
2.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
3.  Tıklatın **C/C++** klasör.  
  
4.  Tıklatın **önceden derlenmiş üstbilgiler** özellik sayfası.  
  
5.  Değiştirme **aracılığıyla PCH dosya oluştur/kullan** özelliği veya **Oluştur/Kullan önceden derlenmiş üstbilgi** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki kod:  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 komut satırı ile derlenmiş `CL /YuMYAPP.H PROG.CPP`, derleyici üç işlemez deyimleri ancak kullanan önceden derlenmiş kod MYAPP.pch, böylece dosyaları (ve bunların içerebilir dosyaları) üçünü önişlemde söz konusu zaman kaydetme içermiyor.  
  
 Kullanabileceğiniz [/Fp (adı. PCH dosyası)](../../build/reference/fp-name-dot-pch-file.md) seçeneğini **/Yu** adı ya da dosya adı bağımsız değişkeni'den farklı ise .pch dosyası adını belirtmek için seçeneği **/Yc** veya kaynak dosyasının içinde olarak temel adı Aşağıdaki:  
  
```  
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP  
```  
  
 Bu komut MYPCH.pch adlı bir önceden derlenmiş üst bilgi dosyası belirtir. Derleyici içeriğinin tüm kadar üstbilgi dosyaları ve dahil olmak üzere MYAPP.h önceden derlenmiş durumunu geri yüklemek için kullanır. Derleyici sonra MYAPP.h sonra gerçekleşir kodu derler **dahil** deyimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)