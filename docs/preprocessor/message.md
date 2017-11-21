---
title: ileti | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- message_CPP
- vc-pragma.message
dev_langs: C++
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3b62961ebd1327e8f8a844482b1490b21b4e9c34
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="message"></a>iletisi
Derlemeyi sonlandırmadan standart çıktıya bir dize sabiti gönderir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma message( messagestring )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tipik bir kullanımını **ileti** pragma olan derleme zamanında bilgilendirici iletileri görüntülemek için.  
  
 *Messagestring* parametresi bir dize sabit değeri genişletir makrosu olabilir ve bu tür makroları herhangi bir arada dize değişmez değerleri ile birleştirme.  
  
 Önceden tanımlanmış makro kullanırsanız **ileti** pragma, makrosu bir dize döndürmelidir, başka bir dizeye makrosu çıktısını dönüştürmeniz gerekir.  
  
 Aşağıdaki kod parçası kullanan **ileti** pragma derleme sırasında iletileri görüntülemek için:  
  
```  
// pragma_directives_message1.cpp  
// compile with: /LD  
#if _M_IX86 >= 500  
#pragma message("_M_IX86 >= 500")  
#endif  
  
#pragma message("")  
  
#pragma message( "Compiling " __FILE__ )   
#pragma message( "Last modified on " __TIMESTAMP__ )  
  
#pragma message("")  
  
// with line number  
#define STRING2(x) #x  
#define STRING(x) STRING2(x)  
  
#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")  
  
#pragma message("")  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)