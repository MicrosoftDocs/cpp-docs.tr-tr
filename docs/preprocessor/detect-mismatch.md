---
title: detect_mismatch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 90f4013606ba94c6ea18aa4369bb2e3298034081
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="detectmismatch"></a>detect_mismatch
Bir kayıt nesneyi yerleştirir. Bağlayıcı olası eşleşmeler bu kayıtları denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma detect_mismatch( "name", "value"))  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Proje bağladığınızda, bağlayıcı oluşturur bir `LNK2038` proje aynı olan iki nesne içeriyorsa hata `name` ancak her farklı bir sahip `value`. Bu pragma bağlamadan tutarsız nesne dosyaları engellemek için kullanın.  
  
 Hem adı hem de değeri dize değişmez değerleri ve dize değişmez değerleri kaçış karakterleri ve birleştirme göre kurallarını uymaktadır. Büyük küçük harfe duyarlıdır ve virgül, eşittir, tırnak işareti içeremez veya `null` karakter.  
  
## <a name="example"></a>Örnek  
 Bu örnek aynı sürüm etiketi için farklı bir sürüm numarasına sahip iki dosya oluşturur.  
  
```  
// pragma_directive_detect_mismatch_a.cpp  
#pragma detect_mismatch("myLib_version", "9")  
int main ()  
{  
   return 0;  
}  
  
// pragma_directive_detect_mismatch_b.cpp  
#pragma detect_mismatch("myLib_version", "1")  
```  
  
 Bu dosyaların her ikisini de komut satırını kullanarak derleme yaparsanız `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp`, hatasıyla karşılaşırsınız `LNK2038`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)