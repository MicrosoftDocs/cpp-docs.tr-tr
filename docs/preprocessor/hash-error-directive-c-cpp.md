---
title: "#<a name=\"error-directive-cc--microsoft-docs\"></a>hata yönergesi (C/C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#error'
dev_langs: C++
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5bb05612ed7262b9daf287793c93ccce654306d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="error-directive-cc"></a>#error Yönergesi (C/C++)
`#error` yönergesi kullanıcı tarafından tanımlanan bir hata iletisini derleme zamanında yayar ve derlemeyi sona erdirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#errortoken-string  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yönerge yayar gelen hata mesajında *belirteci dize* parametresi. `token-string` parametresi için makro genişletme uygulanmaz. Bu yönerge, programdaki tutarsızlıkları ya da bir kısıtlamanın ihlalini geliştiriciye bildirmek için ön işleme sırasında en çok yararlı yönergedir. Aşağıdaki örnek, ön işleme sırasında hatanın işleyişini gösterir:  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)