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
ms.openlocfilehash: 58f3be857e0a77a62a5f2d4d1d0b650f02fd391b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425528"
---
# <a name="macros-and-c"></a>Makrolar ve C++
C++, bazıları ANSI C önişlemcisi tarafından sunulanların yerini alan yeni işlevler sunmaktadır. Bu yeni işlevler tür güvenliğini ve dilin öngörülebilirliğini geliştirir:  
  
- C++'olarak bildirilen nesneler **const** sabit ifadelerde kullanılabilir. Bu, programların tür ve değer bilgilerine sahip sabitler ve hata ayıklayıcıyla sembolik olarak görüntülenebilen numaralandırmalar bildirmelerine olanak verir. Önişlemci `#define` yönergesini kullanarak sabitleri tanımlamak çok kesin sonuç veren bir işlem değildir. Hiçbir depolama için ayrılmış bir **const** programda, adresini alan bir ifade bulunmadığı sürece nesne.  
  
- C++ satır içi işlev özelliği, işlev türündeki makroların yerini alır. Makrolara göre satır içi işlevleri kullanmanın yararları şunlardır:  
  
    - Tür güvenliği. Satır içi işlevler normal işlevlerle aynı tür denetimine tâbidir. Makrolar tür bakımdan güvenli değildir.  
  
    - Yan etkisi olan bağımsız değişkenlerin doğru işlenmesi. Satır içi işlevler, sağlanan ifadeleri işlev gövdesine girmeden önce bağımsız değişkenler olarak değerlendirir. Bu nedenle, yan etkileri olan bir ifadenin güvenilir olmayacağı konusunda hiç olasılık yoktur.  
  
Satır içi işlevleri hakkında daha fazla bilgi için bkz. [satır içi, __inline, \__forceinline](../cpp/inline-functions-cpp.md).  
  
Geriye dönük uyumluluk için, ANSI C ve önceki C++'ta varolan tüm önişlemci özellikleri Microsoft C++ için korunur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Önceden Tanımlanmış Makrolar](../preprocessor/predefined-macros.md)<br/>
[Makrolar (C/C++)](../preprocessor/macros-c-cpp.md)