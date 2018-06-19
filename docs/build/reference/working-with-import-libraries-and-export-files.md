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
ms.openlocfilehash: bc2e5b6b1f2a459d7a00e48ff1aaafff38803871
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377938"
---
# <a name="working-with-import-libraries-and-export-files"></a>İçeri Aktarma Kitaplıkları ve Dışarı Aktarma Dosyalarıyla Çalışma
/ DEF seçeneği ile LIB içeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturmak için kullanabilirsiniz. Dışarı aktarma dosyasını içeren bir program oluşturmak için bağlantı kullanır (genellikle bir dinamik bağlantı kitaplığı (DLL)) dışa aktarır ve diğer programlarla bu dışarı başvuruları çözümlemek için içeri aktarma kitaplığını kullanır.  
  
 .dll oluşturmadan önce ilk adım, içeri aktarma kitaplığını oluşturursanız, içeri aktarma kitaplığını oluştururken geçirilen gibi aynı nesne dosyaları kümesini .dll oluştururken geçmesi gerektiğini unutmayın.  
  
 Çoğu durumda, içeri aktarma kitaplığını oluşturmak üzere LIB kullanmak gerekmez. Dışarı aktarmaları içeren bir program (yürütülebilir bir dosyanın veya bir DLL) bağladığınızda, bağlantı otomatik olarak dışarı aktarmaları açıklayan içeri aktarma kitaplığı oluşturur. Daha sonra bu dışarı aktarma başvuruda bulunan bir program bağladığınızda, içeri aktarma kitaplığı belirtin.  
  
 Bu ayrıca alır bir programa bir DLL dışarı aktarmaları, ancak, olup doğrudan veya dolaylı olarak, LIB içeri aktarma kitaplıkları birini oluşturmak için kullanmanız gerekir. LIB içeri aktarma kitaplığı oluşturduğunda, ayrıca bir dışarı aktarma dosyası oluşturur. Dışa aktarma dosyası Ddl'lerden biri bağlarken kullanmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LIB Başvurusu](../../build/reference/lib-reference.md)