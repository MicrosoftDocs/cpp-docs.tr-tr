---
title: alloc_text | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
dev_langs:
- C++
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b93885663a3d8e037ded97fb7fd16eb5fed9bff8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="alloctext"></a>alloc_text
Belirtilen işlev tanımlarının bulunduğu kod bölümünü adlandırır. Pragma, işlev bildirimcisi ve adlandırılan işlevlerin işlev tanımı arasında gerçekleşmelidir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma alloc_text( "  
textsection  
", function1, ... )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Alloc_text** C++ üye işlevleri veya aşırı yüklenmiş işlevlerin pragma işlemez. Yalnızca C bağlantı olmadan bildirilen işlevleri için geçerli — ile bildirilen işlevler **extern "C"** bağlantı belirtimi. Bu pragmayı C++ bağlantısı olan bir işlevde kullanırsanız, bir derleyici hatası oluşturulur.  
  
 İşlev adresleme kullanarak bu yana `__based` , bölüm konumları kullanılmasını gerektiren belirtilmesi desteklenmiyor **alloc_text** pragması. Tarafından belirtilen adını *textsection* çift tırnak işaretleri içine alınması.  
  
 **Alloc_text** pragma herhangi belirtilen işlevleri ve bu işlevlerin tanımları önce bildirimlerini sonra görünmelidir.  
  
 Başvurulan işlevleri bir **alloc_text** pragma pragma aynı modüldeki tanımlanmalıdır. Bu yapılmazsa ve daha sonra farklı bir metin bölümüne tanımlanmamış bir işlev derlenirse, hatanın yakalanması kesin olmaz. Program genellikle düzgün bir şekilde çalışacak olsa da, işlev hedeflenen bölümlerde ayrılmayacaktır.  
  
 Diğer sınırlamalar **alloc_text** aşağıdaki gibidir:  
  
-   Bir işlev içinde kullanılamaz.  
  
-   İşlev bildirildikten sonra, ancak işlev tanımlanmadan önce kullanılmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)