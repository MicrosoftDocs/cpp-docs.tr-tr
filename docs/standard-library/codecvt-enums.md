---
title: "&lt;codecvt&gt; numaralandırmaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 287f25eb023d00d8cff6ce39992affa39687f721
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt; numaralandırmaları
  
##  <a name="codecvt_mode"></a>  codecvt_mode numaralandırması  
 Yapılandırma bilgilerini belirtir [yerel](../standard-library/locale-class.md) yönü.  
  
```  
enum codecvt_mode {  
    consume_header = 4,  
    generate_header = 2,  
    little_endian = 1  
 };  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Numaralandırma bildirilen yerel modelleri için yapılandırma bilgilerini sağlamanız üç sabitleri tanımlar [ \<codecvt >](../standard-library/codecvt.md). Farklı değerleri şunlardır:  
  
- `consume_header`, birden çok baytlı bir sıra okunurken ilk üstbilgi dizisi kullanabilir ve okumak için sonraki birden çok baytlı dizisi endianness belirlemek için  
  
- `generate_header`, yazılacak sonraki birden çok baytlı dizisi endianness tanıtmak için birden çok baytlı dizisi yazarken ilk üstbilgi dizisi oluşturmak için  
  
- `little_endian`, varsayılan big endian sırası aksine little endian sırayla birden çok baytlı dizisi oluşturmak için  
  
 Bu sabitleri bölümleri birlikte rasgele bileşimlerde olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<codecvt>](../standard-library/codecvt.md)

