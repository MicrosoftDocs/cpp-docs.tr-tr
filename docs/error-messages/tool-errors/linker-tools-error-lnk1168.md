---
title: Bağlayıcı araçları hatası LNK1168 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1168
dev_langs:
- C++
helpviewer_keywords:
- LNK1168
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc3a7c06779cb409a39a930080199b3caf6891ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302428"
---
# <a name="linker-tools-error-lnk1168"></a>Bağlayıcı Araçları Hatası LNK1168
yazma için dosya adı açılamıyor  
  
 Bağlayıcı yazılamıyor `filename`. Dosya kullanımda olabilir ve kendi dosya tanıtıcısı başka bir işlem tarafından kilitli olabilir ya da dosya için veya içinde bulunduğu dizin ya da ağ paylaşımı için yazma izniniz olmayabilir. Bu hata genellikle geçici bir koşul tarafından kaynaklanır — Örneğin, bir kilit bir virüsten koruma programı tarafından tutulan bir dosya aramak dizin oluşturma işlemi, veya bir kilidi serbest bir gecikme tutulan tarafından [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] oluşturma sistemi.  
  
 Bu sorunu gidermek için aşağıdakileri doğrulayın `filename` dosya tanıtıcısı kilitli ve dosya için yazma izniniz olduğunu. Yürütülebilir bir dosya ise, zaten yürütülmekte olmadığını doğrulayın.  
  
 Windows SysInternals yardımcı programları kullanabilirsiniz [işlemek](http://technet.microsoft.com/sysinternals/bb896655.aspx) veya [işlem Gezgini'ni](http://technet.microsoft.com/sysinternals/bb896653) hangi işlemin üzerinde kilit işlemek bir dosya var belirlemek için `filename`. Process Explorer'ı, açık dosya tanıtıcılarındaki kilitleri serbest bırakmak için de kullanabilirsiniz. Bu yardım programlarının nasıl kullanılacağıyla ilgili bilgi için, beraberinde gelen Yardım dosyalarına göz atın.  
  
 Dosya, virüsten koruma programı tarafından kilitlenmişse, virüs koruma programıyla yapı çıktı dizinlerinizi otomatik taramanın dışında tutarak bu sorunu çözebilirsiniz. Anti-virüs tarayıcıları çoğunlukla dosya sisteminde yeni dosyaların oluşturulmasıyla tetiklenir ve tarama devam ederken kilitleri dosyalar üzerinde tutar. Belirli dizinleri taramanın dışında nasıl tutacağınız hakkındaki ayrıntılar için, virüsten koruma programı belgelerinize bakın.  
  
 Dosya, arama dizinleme hizmeti tarafından kilitlenmişse, yapı çıktı dizinlerinizi otomatik dizinlemenin dışında tutarak bu sorunu giderebilirsiniz. Daha fazla bilgi için dizinleme hizmetiyle ilgili belgelere başvurun. Dizin Oluşturma Hizmeti Windows arama değiştirmek için kullanın **dizin oluşturma seçenekleri** Windows **Denetim Masası**. Daha fazla bilgi için bkz: [artırmak Windows dizini kullanarak arar: sık sorulan sorular](http://windows.microsoft.com/en-us/windows/improve-windows-searches-using-index-faq#1TC=windows-7).  
  
 Yürütülebilir dosyanızın üzerine yapı işlemi tarafından yazılamıyorsa, dosyanız Dosya Gezgini tarafından kilitlenmiş olabilir. Varsa **uygulama deneyimi** hizmeti devre dışı bırakıldı, dosya Gezgini bir yürütülebilir dosya tanıtıcısı kilit uzun bir süre tutun. Bu sorunu gidermek için Çalıştır **services.msc** ve ardından açın **özellikleri** iletişim kutusu için **uygulama deneyimi** hizmet. Değişiklik **başlangıç türü** gelen **devre dışı** için **el ile**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir çözüm veya Visual C++'ta ActiveX projesi oluşturmak çalıştığınızda bir "hatası PRJ0008" veya "Önemli hatası LNK1168" hata iletisini alabilirsiniz](http://support.microsoft.com/kb/308358)