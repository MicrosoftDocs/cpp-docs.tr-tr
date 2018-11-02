---
title: İçeri Aktarma Kitaplığını ve Dışarı Aktarma Dosyasını Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- circular exports
- import libraries, using
- export files
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
ms.openlocfilehash: e23b729bdca102ec24c4426e9784e3aab267bff2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484974"
---
# <a name="using-an-import-library-and-export-file"></a>İçeri Aktarma Kitaplığını ve Dışarı Aktarma Dosyasını Kullanma

İkiden fazla programlar hem vermek ve birbirinden alırsanız, bu programlar bağlamak için komutları dairesel dışarı aktarmalar uyum veya bir program, ayrıca alır başka bir program için (bir yürütülebilir dosya veya bir DLL) verir.

Dairesel dışarı aktarmalar olmadan bir durumda kullanan bir program bağlama başka bir programdan verdiğinde içeri aktarma kitaplığı verme programı belirtmeniz gerekir. İçeri aktarma kitaplığı verme programı, bu dışarı aktarma programı bağladığınızda oluşturulur. Bu nedenle, içeri aktarma programı önce dışa aktarma programı bağlamanız gerekir. TWO.dll ONE.dll aktarırsa, örneğin, önce ONE.dll bağlamak ve içeri aktarma kitaplığını ONE.lib alın. Ardından, ONE.lib TWO.dll bağlarken belirtin. Bağlayıcı TWO.dll oluşturduğunda, ayrıca TWO.lib, içeri aktarma kitaplığı oluşturur. TWO.dll alma programları bağlantılandırma TWO.lib kullanın.

Ancak, döngüsel verme durumunda, bu programlardan içeri aktarma kitaplıkları kullanarak tüm bağımlı programları bağlamak mümkün değildir. TWO.dll ONE.dll için de dışarı aktarır, TWO.dll için içeri aktarma kitaplığı var olmaz henüz ONE.dll bağlı olduğunda daha önce bahsedilen örnekte. Dairesel dışarı aktarmalar varsa, içeri aktarma kitaplığı oluşturma ve programlardan birini dosyasını dışarı aktarmak için LIB kullanmanız gerekir.

Başlamak için LIB çalıştırılacağı programlardan birini seçin. LIB komutunun tüm nesneleri ve kitaplıkları için program listesi ve /DEF. belirtin Program bir .def dosyası ya da/Export belirtimleri kullanıyorsa, bunlar da belirtin.

İçeri aktarma kitaplık (.lib) ve dışarı aktarma dosyası (.exp) programı oluşturduktan sonra bir programı veya programları bağlarken içeri aktarma kitaplığını kullanın. BAĞLANTI bir içeri aktarma kitaplığını yapıların her dışarı aktarılırken bir program oluşturur. LIB nesneleri ve dışarı aktarma için ONE.dll çalıştırırsanız, örneğin, ONE.lib ve ONE.exp oluşturun. TWO.dll bağlarken artık ONE.lib kullanabilirsiniz; Bu adım ayrıca TWO.lib içeri aktarma kitaplığı oluşturur.

Son olarak, programın başlamış bağlayın. Bağlantı komut içinde nesneleri ve kitaplıkları LIB program ve içeri aktarma kitaplığı için oluşturulan .exp dosyası program veya program tarafından kullanılan dışarı aktarmaları için kitaplıkları belirtin. Örnek devam etmek için ONE.dll için bağlantı komut ONE.exp ve TWO.lib, yanı sıra nesneleri ve ONE.dll Git kitaplıkları içerir. .Def dosyası ya da/Export belirtimleri bağlantı komutta belirtmeyin; .exp dosyası dışarı aktarma tanımları içerdiğinden bu, gerekli değildir. .Exp dosyası kullanılıyor bağladığınızda, bağlantı içeri aktarma kitaplığı oluşturmaz, bunun varsayar çünkü .exp dosyası oluşturulurken oluşturulmuştur.

## <a name="see-also"></a>Ayrıca Bkz.

[İçeri Aktarma Kitaplıkları ve Dışarı Aktarma Dosyalarıyla Çalışma](../../build/reference/working-with-import-libraries-and-export-files.md)