---
title: sonra | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.once
- once_CPP
dev_langs:
- C++
helpviewer_keywords:
- once pragma
- pragmas, once
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b0e0b2b3667d4a33709caa643e4d26ed70b2990
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912933"
---
# <a name="once"></a>once
Bir kaynak kodu dosyasını derlerken dosyanın (açık) yalnızca bir kez derleyici tarafından dahil olacağını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma once  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanımını `#pragma once` derleyici değil açın ve sonra ilk dosyayı okuma gibi yapı kez azaltabilirsiniz # çeviri biriminde dosyasının include. Bu olarak adlandırılır *en iyi duruma getirme birden çok dahil*. Benzer bir etkiye sahiptir *# koruma include* dosyasının içeriğini birden çok dahil edilmesi önlemek için önişlemci makrosu tanımları kullanır deyim. Bu ayrıca ihlalleri önlemeye yardımcı olur *bir tanım kuralını*— tüm şablonları, türü, İşlevler ve nesneler birden fazla tanım kodunuzda sahip gereksinimi.  
  
 Örneğin:  
  
```  
// header.h  
#pragma once  
// Code placed here is included only once per translation unit  
  
```  
  
 Öneririz `#pragma once` önişlemci sembolü ile genel ad alanı pollute değil çünkü yönergesi için yeni kod. Daha az yazarak gerektirir, daha az dağıtıyor ve sembol çakışmalarına neden olamaz — farklı üstbilgi dosyaları koruma değeri olarak aynı önişlemci sembolü kullandığınızda hatalardır. C++ standart bir parçası değil, ancak birçok ortak derleyicileri tarafından temelinizi uygulanır.  
  
 Her ikisi de kullanmak için herhangi bir avantaj sağlamaz # koruma deyim include ve `#pragma once` aynı dosyada. Derleyicisi tanır # koruma deyim ve birden çok dahil en iyi duruma getirme aynı şekilde uygular include `#pragma once` açıklama olmayan kod veya önişlemci yönergesi önce veya sonra deyim standart biçiminde geliyorsa yönergesi:  
  
```  
// header.h  
// Demonstration of the #include guard idiom.  
// Note that the defined symbol can be arbitrary.  
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_  
#define HEADER_H_  
// Code placed here is included only once per translation unit  
#endif // HEADER_H_  
  
```  
  
 Öneririz # kod uygulamayan derleyicileri taşınabilir koruma deyim include `#pragma once` varolan koduyla tutarlılığını korumak için yönergesi veya birden çok dahil en iyi duruma getirme imkansızdır. Dosya sistemi yumuşatma ya da diğer eklediğinizde bu yollar önlemek tanımlayan gelen aynı derleyici karmaşık projelerinde oluşabilir kurallı yoluyla dosyaları içerir.  
  
 Kullanma konusunda dikkatli olun `#pragma once` veya # önişlemci sembolleri etkilerini kontrol kullanmayı tasarlanmış birden çok kez dahil edilmek üzere üstbilgi dosyalarına koruma deyim include. Bu tasarım örneği için bkz: \<assert.h > Üstbilgi dosyası. Ayrıca yönetmek dikkatli olun boşa çıkarabilir eklenen dosyalar için birden fazla yol oluşturmamak için yol eklemeyi iyileştirme için her ikisini birden çok dahil # koruyucuları include ve `#pragma once`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)