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
ms.workload: cplusplus
ms.openlocfilehash: a14786834843046fc1e6cf551eaf95d1b28a8624
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)