---
title: Kitaplık üyesini ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0dc0dc67a6d9e4a3ff61aa3b82ac10b9eabcb94b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371248"
---
# <a name="extracting-a-library-member"></a>Kitaplık Üyesini Ayıklama
LIB var olan bir kitaplık üyesi bir kopyasını içeren bir nesne (.obj) dosyası oluşturmak için kullanabilirsiniz. Üye bir kopyasını ayıklamak için aşağıdaki sözdizimini kullanın:  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 Bu komut adlı bir .obj dosyası oluşturur *objectfile* bir kopyasını içeren bir `member` , bir *Kitaplığı*. `member` Adı büyük küçük harfe duyarlı. Tek bir komut yalnızca bir üye ayıklayabilirsiniz. /OUT seçeneği gereklidir; Varsayılan çıkış adı yok. Bir dosya çağrıldıklarında *objectfile* belirtilen dizinde zaten var. (veya dizin yok ile belirtilmişse, geçerli dizin *objectfile*), ayıklanan *objectfile*varolan dosyanın yerini alır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LIB Başvurusu](../../build/reference/lib-reference.md)