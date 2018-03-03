---
title: "Visual C++ ActiveX denetimlerini yeniden dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], redistributing
- controls [C++], distributing
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c520d365a259c36baab8edeb9049aab9ac89925a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-visual-c-activex-controls"></a>Visual C++ ActiveX Denetimlerini Yeniden Dağıtma
Visual C++ 6.0 sonra dağıtmanız uygulamalarda kullanabileceğiniz ActiveX denetimleri sağlar. Bu denetimler, artık Visual c++'ta dahil edilir. Visual C++ 6.0 için lisans sözleşmelerine göre Visual c++'ta geliştirilen uygulamaları ile bu denetimleri dağıtabilirsiniz.  
  
> [!NOTE]
>  Visual C++ 6.0 artık Microsoft tarafından desteklenir.  
  
 Yeniden dağıtılabilir Visual C++ 6.0 ActiveX denetimlerinin listesi için Visual C++ 6.0 ürün CD'sinin disk 1 üzerinde Common\Redist\Redist.txt bakın.  
  
 Uygulamaları dağıtırken, yüklemeniz ve .ocx (Regsvr32.exe kullanarak) ActiveX denetimi için kaydetmeniz gerekir. Ayrıca, hedef bilgisayarda (yıldız dosyanın kaydedilmesi gerekiyor gösterir) aşağıdaki sistem dosyalarının geçerli sürümlerinin olduğundan emin olmanız gerekir:  
  
-   Asycfilt.dll  
  
-   Comcat.dll *  
  
-   Oleaut32.dll *  
  
-   Olepro32.dll *  
  
-   Stdole2.tlb  
  
 Bu DLL'ler hedef sistemde mevcut değilse, bunlara karşılık gelen işletim sistemini güncelleştirmek için öngörülen mekanizmasını kullanarak güncelleştirilmiş almanız gerekir. Windows işletim sistemleri için en son hizmet paketleri indirebilirsiniz [http://windowsupdate.microsoft.com](http://windowsupdate.microsoft.com).  
  
 Uygulamanız bir veritabanına bağlanan ActiveX denetimlerini kullanıyorsa, Microsoft Data Access Components (MDAC) hedef sistemde yüklü olması gerekir. Daha fazla bilgi için bkz: [veritabanı destek dosyalarını yeniden dağıtma](../ide/redistributing-database-support-files.md).  
  
 Bir veritabanına bağlanan bir ActiveX denetimini kullanırken, ayrıca veri kaynağı adı hedef bilgisayarda çoğaltmanız gerekir. Bu program aracılığıyla işlevleriyle gibi yapabileceğiniz `ConfigDSN`.  
  
 Bazı yeniden dağıtılabilir ActiveX denetimlerinin ek bağımlılıkları vardır. Her .ocx dosyası için Os\System klasöründe Visual C++ 6.0 ürün CD'sindeki, ayrıca bir.DEP dosyası vardır. Yeniden dağıtmak istediğiniz her .ocx dosyası için ilgili .dep dosyasında bir veya daha fazla kullanır girdilerini arayın. Bir dosya listeleniyorsa, dosyanın hedef bilgisayarda olduğundan emin olmalısınız. Doğrudan destekleyen bir .ocx dosyasının DLL'lerin kayıtlı olması gerekir. (Başarılı olması Regsvr32.exe için hedef bilgisayarı ilk tüm denetim statik olarak yüklediği tüm DLL'leri içermesi gerekir.) Ayrıca, bir bağımlılık olarak listelenen bir DLL de bir.DEP dosyası Visual C++ 6.0 CD'sindeki Os\System klasöründe varsa, bu .dep dosyasında kullanır girişler için de araştırmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Dosyalarını Yeniden Dağıtma](../ide/redistributing-visual-cpp-files.md)