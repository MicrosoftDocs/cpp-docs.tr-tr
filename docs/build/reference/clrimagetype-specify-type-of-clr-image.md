---
title: "-CLRIMAGETYPE (CLR görüntü türünü belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs: C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6f11684f71e874d2dbb439ed1f9dfc46b543a63e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (CLR Görüntü Türünü Belirt)
```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlayıcı yerel nesneleri kabul eder ve ayrıca kullanarak derlenen MSIL nesneleri [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), / CLR: pure, veya/CLR: safe. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı. Karma nesneleri aynı derlemede geçirildiğinde, sonuçta elde edilen çıktı dosyası verifiability, varsayılan olarak, en düşük düzeyde verifiability giriş modüllerin eşit olur. Örneğin, hem güvenli hem de saf modülü bağlayıcıya geçirirseniz, çıktı dosyası saf olacaktır. Yerel görüntü ve karma mod görüntü geçirirseniz (kullanarak derlenmiş **/CLR**), elde edilen görüntü bir karma mod görüntüsü olacaktır.  
  
 Bu ihtiyacınız olursa, /CLRIMAGETYPE verifiability, daha düşük düzeyde belirtmek için kullanabilirsiniz.  
  
 .NET 4.5 içinde /CLRIMAGETYPE SAFE32BITPREFERRED seçeneğini destekler. Bu ayarlar — görüntünün PE üstbilgisinde — MSIL nesneleri güvenli ve olabilir belirten bayrakları 32-bit yürütme ortamı tercih edilen ancak bu tüm platformlarda çalıştırın. Bu seçenek, ARM platformda çalışacak bir uygulama sağlar ve ayrıca, 64-bit Yürütme Ortamı'nı kullanarak yerine 64 bit işletim sistemlerinde WOW64 altında çalışması gerektiğini belirtir.  
  
 Kullanarak derlenen bir .exe, **/CLR** veya **/CLR: pure** çalıştırılan bir 64-bit işletim sisteminde 64-bit işletim sisteminde çalıştırmak bir 32 bit uygulama etkinleştirir WOW64 altında uygulamayı çalıştırın. Varsayılan olarak, kullanarak derlenmiş bir .exe **/CLR: safe** işletim sisteminin 64-bit desteği altında çalıştırın. Ancak, güvenli uygulamanız bir 32 bit bileşeni yükler mümkündür. Bu durumda, 32 bit uygulama yüklendiğinde işletim sisteminin 64-bit desteği altında çalışan güvenli bir görüntü başarısız olur. Güvenli bir görüntü bir 64-bit işletim sisteminde 32 bit bileşen yüklenirken çalışmaya devam ettiğinden emin olmak için /CLRIMAGETYPE:SAFE32BITPREFERRED seçeneğini kullanın. Kodunuzu ARM platformda çalışacak yoksa /CLRIMAGETYPE belirtebilirsiniz: meta veriler (.corflags) değiştirmek için saf seçeneği WOW64 altında çalıştırılması için İşaretleme (ve kendi giriş simge değiştirerek):  
  
 **cl/CLR: safe t.cpp/Link /clrimagetype: Saf /entry:?main@@$$HYMHXZ /subsystem:console**  
  
 Bir dosya CLR görüntü türünü belirleme hakkında daha fazla bilgi için bkz: [/CLRHEADER](../../build/reference/clrheader.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **Gelişmiş** özellik sayfası.  
  
5.  Değiştirme **CLR görüntü türünü** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)