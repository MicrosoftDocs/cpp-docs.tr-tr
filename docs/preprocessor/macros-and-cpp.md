---
title: Makrolar ve C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 746b04113e4cb49716e0c1fa6dee69a250bded42
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849619"
---
# <a name="macros-and-c"></a>Makrolar ve C++
C++, bazıları ANSI C önişlemcisi tarafından sunulanların yerini alan yeni işlevler sunmaktadır. Bu yeni işlevler tür güvenliğini ve dilin öngörülebilirliğini geliştirir:  
  
-   C++'da, nesneleri olarak bildirilebilir. **const** sabit ifadeler kullanılabilir. Bu, programların tür ve değer bilgilerine sahip sabitler ve hata ayıklayıcıyla sembolik olarak görüntülenebilen numaralandırmalar bildirmelerine olanak verir. Önişlemci `#define` yönergesini kullanarak sabitleri tanımlamak çok kesin sonuç veren bir işlem değildir. Depolama için ayrılmış bir **const** adresini alır bir ifade programda bulunan sürece nesne.  
  
-   C++ satır içi işlev özelliği, işlev türündeki makroların yerini alır. Makrolara göre satır içi işlevleri kullanmanın yararları şunlardır:  
  
    -   Tür güvenliği. Satır içi işlevler normal işlevlerle aynı tür denetimine tâbidir. Makrolar tür bakımdan güvenli değildir.  
  
    -   Yan etkisi olan bağımsız değişkenlerin doğru işlenmesi. Satır içi işlevler, sağlanan ifadeleri işlev gövdesine girmeden önce bağımsız değişkenler olarak değerlendirir. Bu nedenle, yan etkileri olan bir ifadenin güvenilir olmayacağı konusunda hiç olasılık yoktur.  
  
 Satır içi işlevler hakkında daha fazla bilgi için bkz: [satır içi, __inline, \__forceinline](../cpp/inline-functions-cpp.md).  
  
 Geriye dönük uyumluluk için, ANSI C ve önceki C++'ta varolan tüm önişlemci özellikleri Microsoft C++ için korunur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Önceden tanımlı makrolar](../preprocessor/predefined-macros.md)   
 [Makrolar (C/C++)](../preprocessor/macros-c-cpp.md)