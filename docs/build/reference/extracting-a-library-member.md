---
title: "Kitaplık üyesini ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1c27e5c78316ec48d114bfd1715eb5874772a732
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="extracting-a-library-member"></a>Kitaplık Üyesini Ayıklama
LIB var olan bir kitaplık üyesi bir kopyasını içeren bir nesne (.obj) dosyası oluşturmak için kullanabilirsiniz. Üye bir kopyasını ayıklamak için aşağıdaki sözdizimini kullanın:  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 Bu komut adlı bir .obj dosyası oluşturur *objectfile* bir kopyasını içeren bir `member` , bir *Kitaplığı*. `member` Adı büyük küçük harfe duyarlı. Tek bir komut yalnızca bir üye ayıklayabilirsiniz. /OUT seçeneği gereklidir; Varsayılan çıkış adı yok. Bir dosya çağrıldıklarında *objectfile* belirtilen dizinde zaten var. (veya dizin yok ile belirtilmişse, geçerli dizin *objectfile*), ayıklanan *objectfile*varolan dosyanın yerini alır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LIB başvurusu](../../build/reference/lib-reference.md)