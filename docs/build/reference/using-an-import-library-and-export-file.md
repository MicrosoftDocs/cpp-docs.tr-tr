---
title: "İçeri aktarma kitaplığı ve dışarı aktarma dosyasını kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- circular exports
- import libraries, using
- export files
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5c056907716f95a82fde01847485837fcba96f66
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-an-import-library-and-export-file"></a>İçeri Aktarma Kitaplığını ve Dışarı Aktarma Dosyasını Kullanma
Bir program, ayrıca alır başka bir programa (yürütülebilir bir dosyanın veya bir DLL) verir veya ikiden fazla programlar hem vermek ve birbirlerinden alırsanız, bu programlar bağlamak için komutları dairesel dışarı aktarmalar uyum gerekir.  
  
 Dairesel dışarı aktarmalar olmadan bir durumda kullanan bir programı bağlama başka bir programda verdiğinde içeri aktarma kitaplığını dışarı aktarma programı belirtmeniz gerekir. Bu verme program bağladığınızda, içeri aktarma kitaplığını dışarı aktarma programı için oluşturulur. Bu nedenle, dışa aktarma program alma program çalıştırılmadan önce bağlanmanız gerekir. ONE.dll TWO.dll alır, örneğin, öncelikle ONE.dll bağlamak ve içeri aktarma kitaplığını ONE.lib alın. Ardından, ONE.lib TWO.dll bağlarken belirtin. Bağlayıcı TWO.dll oluşturduğunda, ayrıca, içeri aktarma kitaplığını TWO.lib oluşturur. TWO.dll alma programları bağlantılandırma TWO.lib kullanın.  
  
 Ancak, döngüsel verme durumunda, bu tüm diğer programları alma kitaplıklarından kullanarak birbirine programları bağlamak mümkün değil. TWO.dll ONE.dll için aynı zamanda aktarır, TWO.dll için içeri aktarma kitaplığı var olmaz henüz ONE.dll zaman bağlı daha önce açıklanan örnekte. Dairesel dışarı aktarmalar varsa, içeri aktarma kitaplığı oluşturun ve programları biri için dışarı aktarmak için LIB kullanmanız gerekir.  
  
 Başlamak için program LIB çalıştırılacağı birini seçin. LIB komutta, tüm nesneleri ve program için kitaplıkları listelemek ve /DEF. belirtin Program .def dosyası ya da/Export belirtimleri kullanıyorsa, bu da belirtin.  
  
 (.Lib) içeri aktarma kitaplığı ve dışarı aktarma dosyası (.exp) programı oluşturduktan sonra başka bir programı veya programları bağlarken içeri aktarma kitaplığını kullanın. BAĞLANTI yapıların verme her program için içeri aktarma kitaplığı oluşturur. LIB nesneleri ve dışarı aktarma için ONE.dll çalıştırırsanız, örneğin, ONE.lib ve ONE.exp oluşturun. Artık TWO.dll bağlanırken ONE.lib kullanabilirsiniz; Bu adım ayrıca TWO.lib içeri aktarma kitaplığı oluşturur.  
  
 Son olarak, programın ile başlamıştır bağlayın. BAĞLANTI komutta, nesneleri ve kitaplıkları LIB program ve içeri aktarma kitaplığı için oluşturulan .exp dosyası programı veya program tarafından kullanılan dışarı kitaplığı belirtin. Örnek devam etmek için nesneleri ve ONE.dll gidin kitaplıkları yanı sıra ONE.exp ve TWO.lib, ONE.dll bağlantı komutu içerir. .Def dosyası ya da/Export belirtimleri bağlantı komutta belirtmeyin; Verme tanımları .exp dosyasında bulunan çünkü bunlar, gerekli değildir. Bir .exp dosyası kullanarak bağladığınızda, bağlantı içeri aktarma kitaplığı oluşturmaz, .exp dosyasını oluştururken bir kabul ettiği için oluşturulmuştur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçeri aktarma kitaplıkları ve dışarı aktarma dosyalarıyla çalışma](../../build/reference/working-with-import-libraries-and-export-files.md)