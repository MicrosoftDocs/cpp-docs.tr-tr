---
title: '#hata yönergesi (C/C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#error'
dev_langs:
- C++
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2da939fe52e41e122ecd4926e34fb9c4be735ae
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42466443"
---
# <a name="error-directive-cc"></a>#error Yönergesi (C/C++)
**#Error** yönergesi, bir kullanıcı tarafından belirtilen hata iletisini derleme zamanında yayar ve derlemeyi sona erdirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#errortoken-string  
```  
  
## <a name="remarks"></a>Açıklamalar  
 
Bu yönergenin yaydığı hata iletisi içerir *belirteç dizesinde* parametresi. *Belirteç dizesinde* parametresi makro genişletme uygulanmaz değil. Bu yönerge, programdaki tutarsızlıkları ya da bir kısıtlamanın ihlalini geliştiriciye bildirmek için ön işleme sırasında en çok yararlı yönergedir. Aşağıdaki örnek, ön işleme sırasında hatanın işleyişini gösterir:  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)