---
description: 'Hakkında daha fazla bilgi edinin: Içeri aktarma kitaplığı ve dışarı aktarma dosyası kullanma'
title: İçeri Aktarma Kitaplığını ve Dışarı Aktarma Dosyasını Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- circular exports
- import libraries, using
- export files
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
ms.openlocfilehash: f42a98ebe19cb32fb77964f26c37928776b5b30c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247026"
---
# <a name="using-an-import-library-and-export-file"></a>İçeri Aktarma Kitaplığını ve Dışarı Aktarma Dosyasını Kullanma

Bir program (bir yürütülebilir dosya veya DLL), aynı zamanda içeri aktardığı başka bir programa dışarı aktardığında ya da ikiden fazla program her ikisi de dışarı aktarıp içeri aktarıldığında, bu programları bağlama komutları döngüsel dışarı aktarmaları sağlamalıdır.

Döngüsel dışarı aktarmalar olmadan bir durumda, başka bir programdan dışarı aktarmalar kullanan bir programı bağlarken dışarı aktarma programı için içeri aktarma kitaplığını belirtmeniz gerekir. Dışarı aktarma programı için içeri aktarma kitaplığı, bu dışarı aktarma programını bağladığınızda oluşturulur. Bu nedenle, dışa aktarma programını içe aktarma programından önce bağlamanız gerekir. Örneğin, ONE.dll TWO.dll içeri aktarıldığında, önce ONE.dll bağlamanız ve içeri aktarma kitaplığını BIR. lib almanız gerekir. Sonra, TWO.dll bağlarken BIR. lib belirtirsiniz. Bağlayıcı TWO.dll oluşturduğunda içeri aktarma kitaplığı, ıkı. lib de oluşturulur. TWO.dll içeri aktarılan programları bağlarken ıkı. lib kullanın.

Ancak, döngüsel bir dışarı aktarma durumunda, diğer programlardan içeri aktarma kitaplıklarını kullanarak birbirine bağlı tüm programları bağlamak mümkün değildir. Daha önce açıklanan örnekte, TWO.dll Ayrıca ONE.dll dışarı aktardığında, ONE.dll bağlandığında TWO.dll için içeri aktarma kitaplığı henüz olmaz. Döngüsel dışarı aktarmalar mevcut olduğunda, programlardan biri için bir içeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturmak üzere LIB ' i kullanmanız gerekir.

Başlamak için, LıB 'in çalıştırılacağı programlardan birini seçin. LıB komutunda, program için tüm nesneleri ve kitaplıkları listeleyin ve/DEF. belirtin. Program bir. def dosyası ya da/EXPORT belirtimleri kullanıyorsa, bunları da belirtin.

Program için içeri aktarma kitaplığını (. lib) ve dışarı aktarma dosyasını (. exp) oluşturduktan sonra, diğer program veya programları bağlarken içeri aktarma kitaplığını kullanırsınız. BAĞLANTı, oluşturduğu her dışarı aktarma programı için bir içeri aktarma kitaplığı oluşturur. Örneğin, nesneler üzerinde LIB çalıştırırsanız ve ONE.dll için dışarı aktardıysanız BIR. LIB ve bır. exp oluşturursunuz. Artık TWO.dll bağlarken BIR. lib kullanabilirsiniz; Bu adım Ayrıca içeri aktarma kitaplığını ıkı. lib de oluşturur.

Son olarak, ile başlayan programı bağlayın. BAĞLANTı komutunda, program için nesne ve kitaplıkları, program için LıB 'in oluşturduğu. exp dosyasını ve program tarafından kullanılan dışarı aktarmalar için içeri aktarma kitaplığını veya kitaplıklarını belirtin. Örneğe devam etmek için, ONE.dll için bağlantı komutu BIR. exp ve ıkı. lib içerir, Ayrıca, ONE.dll olan nesne ve kitaplıkları içerir. LINK komutunda. def dosyasını veya/EXPORT belirtimlerini belirtmeyin; dışarı aktarma tanımları. exp dosyasında bulunduğundan bunlar gerekli değildir. Bir. exp dosyası kullanarak bağladığınızda, bağlantı bir içeri aktarma kitaplığı oluşturmaz, çünkü. exp dosyası oluşturulduğunda oluşturulduğu varsayılır.

## <a name="see-also"></a>Ayrıca bkz.

[Içeri aktarma kitaplıkları ve dışarı aktarma dosyalarıyla çalışma](working-with-import-libraries-and-export-files.md)
