---
title: ileti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- message_CPP
- vc-pragma.message
dev_langs:
- C++
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3ce9091fe380f7d255dd321dbb9eb5ca7134b8d
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465361"
---
# <a name="message"></a>iletisi
Derlemeyi sonlandırmadan standart çıktıya bir dize sabiti gönderir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma message( messagestring )  
```  
  
## <a name="remarks"></a>Açıklamalar  

Tipik bir kullanımı, **ileti** pragması, derleme zamanında bilgi iletileri görüntülemek için.  
  
*Messagestring* parametresi bir dize sabiti olarak genişleyen bir makro olabilir ve bu tür makroları dize herhangi bir birleşimini bitiştirebilirsiniz.  
  
Önceden tanımlanmış bir makro kullanırsanız **ileti** pragması, makro bir dize döndürmelidir, aksi takdirde makronun çıktısını bir dizeye dönüştürmek gerekir.  
  
Aşağıdaki kod parçası kullanan **ileti** pragması, derleme sırasında iletileri görüntülemek için:  
  
```cpp  
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
 
[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)