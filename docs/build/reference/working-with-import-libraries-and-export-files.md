---
description: 'Hakkında daha fazla bilgi edinin: Içeri aktarma kitaplıkları ve dışarı aktarma dosyaları ile çalışma'
title: İçeri Aktarma Kitaplıkları ve Dışarı Aktarma Dosyalarıyla Çalışma
ms.date: 11/04/2016
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
ms.openlocfilehash: b6e1664aedf5fa87d269e0ff250e6c52d9d18259
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258804"
---
# <a name="working-with-import-libraries-and-export-files"></a>İçeri Aktarma Kitaplıkları ve Dışarı Aktarma Dosyalarıyla Çalışma

İçeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturmak için LıB 'i/DEF seçeneğiyle birlikte kullanabilirsiniz. BAĞLANTı, dışarı aktarmalar (genellikle dinamik bağlantı kitaplığı (DLL)) içeren bir program oluşturmak için dışa aktarma dosyasını kullanır ve diğer programlarda bu dışarı aktarmalar için başvuruları çözümlemek üzere içeri aktarma kitaplığını kullanır.

İçeri aktarma kitaplığınızı bir ön adımda oluşturursanız,. dll 'nizi oluşturmadan önce, içeri aktarma kitaplığını oluştururken geçirdiğiniz gibi,. dll dosyasını oluştururken aynı nesne dosyaları kümesini geçirmeniz gerekir.

Çoğu durumda, içeri aktarma kitaplığınızı oluşturmak için LIB kullanmanız gerekmez. Dışarı aktarmaları içeren bir programı (yürütülebilir dosya veya DLL) bağladığınızda, bağlantı dışarı aktarmaları açıklayan bir içeri aktarma kitaplığı otomatik olarak oluşturur. Daha sonra, bu dışarı aktarımlara başvuran bir programı bağladığınızda içeri aktarma kitaplığını belirtirsiniz.

Ancak, bir DLL ' den içeri aktardığı bir programa dışarı aktardığında, doğrudan veya dolaylı olarak, içeri aktarma kitaplıklarından birini oluşturmak için LıB kullanmanız gerekir. LıB bir içeri aktarma kitaplığı oluşturduğunda, bir dışa aktarma dosyası da oluşturur. Dll 'Lerden birini bağlarken dışarı aktarma dosyasını kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[LıB başvurusu](lib-reference.md)
