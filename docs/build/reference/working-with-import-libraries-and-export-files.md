---
title: İçeri aktarma kitaplıkları ve dışarı aktarma dosyalarıyla çalışma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28b4b94025c813ea526964ed6395a2e6af1ac0b9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721246"
---
# <a name="working-with-import-libraries-and-export-files"></a>İçeri Aktarma Kitaplıkları ve Dışarı Aktarma Dosyalarıyla Çalışma

/ DEF seçeneği ile LIB, bir içeri aktarma kitaplığını ve dışarı aktarma dosyası oluşturmak için kullanabilirsiniz. Dışarı aktarma dosyası içeren bir program oluşturmak için bağlantı kullanır (genellikle bir dinamik bağlantı kitaplığı (DLL)) verir ve diğer programlarda bu dışarı başvurularını çözümlemek için içeri aktarma kitaplığını kullanır.

Başlangıç bir adımda, .dll oluşturmadan önce içeri aktarma kitaplığını oluşturursanız, içeri aktarma kitaplığı derlerken geçti olarak, aynı nesne dosyaları kümesini .dll oluştururken geçmesi gerektiğini unutmayın.

Çoğu durumda, LIB, içeri aktarma kitaplığı oluşturmak için kullanın gerekmez. Dışarı aktarmaları içeren bir program (bir yürütülebilir dosya veya bir DLL) bağladığınızda, bağlantı otomatik olarak dışarı aktarmaları açıklayan bir içeri aktarma kitaplığı oluşturur. Daha sonra bu dışarı aktarma başvuran bir program bağladığınızda, içeri aktarma kitaplığını belirtin.

Ayrıca alır bir programa bir DLL'nin dışa aktardığında, ancak olup doğrudan veya dolaylı olarak, LIB içeri aktarma kitaplıkları birini kullanmanız gerekir. LIB içeri aktarma kitaplığı oluşturduğunda, dışarı aktarma dosyası da oluşturur. Dışarı aktarma dosyası Ddl'lerden biri bağlanırken kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[LIB Başvurusu](../../build/reference/lib-reference.md)