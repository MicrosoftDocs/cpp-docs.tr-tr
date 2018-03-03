---
title: "İçeri aktarma kitaplıkları ve dışarı aktarma dosyalarıyla çalışma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e0d60eed00abc60c09e03838a113c424d8f173a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="working-with-import-libraries-and-export-files"></a>İçeri Aktarma Kitaplıkları ve Dışarı Aktarma Dosyalarıyla Çalışma
/ DEF seçeneği ile LIB içeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturmak için kullanabilirsiniz. Dışarı aktarma dosyasını içeren bir program oluşturmak için bağlantı kullanır (genellikle bir dinamik bağlantı kitaplığı (DLL)) dışa aktarır ve diğer programlarla bu dışarı başvuruları çözümlemek için içeri aktarma kitaplığını kullanır.  
  
 .dll oluşturmadan önce ilk adım, içeri aktarma kitaplığını oluşturursanız, içeri aktarma kitaplığını oluştururken geçirilen gibi aynı nesne dosyaları kümesini .dll oluştururken geçmesi gerektiğini unutmayın.  
  
 Çoğu durumda, içeri aktarma kitaplığını oluşturmak üzere LIB kullanmak gerekmez. Dışarı aktarmaları içeren bir program (yürütülebilir bir dosyanın veya bir DLL) bağladığınızda, bağlantı otomatik olarak dışarı aktarmaları açıklayan içeri aktarma kitaplığı oluşturur. Daha sonra bu dışarı aktarma başvuruda bulunan bir program bağladığınızda, içeri aktarma kitaplığı belirtin.  
  
 Bu ayrıca alır bir programa bir DLL dışarı aktarmaları, ancak, olup doğrudan veya dolaylı olarak, LIB içeri aktarma kitaplıkları birini oluşturmak için kullanmanız gerekir. LIB içeri aktarma kitaplığı oluşturduğunda, ayrıca bir dışarı aktarma dosyası oluşturur. Dışa aktarma dosyası Ddl'lerden biri bağlarken kullanmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LIB Başvurusu](../../build/reference/lib-reference.md)