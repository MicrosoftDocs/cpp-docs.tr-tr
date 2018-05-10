---
title: '#undef yönergesi (C/C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#undef'
dev_langs:
- C++
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16b8c937ad62ddc6738c626543dab2d4e5453bc5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="undef-directive-cc"></a>#undef Yönergesi (C/C++)
Daha önce `#define` ile oluşturulmuş bir adı kaldırır (tanımsız hale getirir).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#undef   
identifier  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `#undef` Yönergesi kaldırır geçerli tanımı *tanımlayıcısı*. Sonuç olarak, sonraki oluşumları *tanımlayıcısı* önişlemci tarafından göz ardı edilir. Makro tanımı kullanarak kaldırmak için `#undef`, yalnızca makrosu vermek *tanımlayıcısı* ; parametre listesi vermeyin.  
  
 Ayrıca `#undef` yönergesini daha önce bir tanımı bulunmayan tanımlayıcılar için de uygulayabilirsiniz. Bu tanımlayıcının tanımsız hale gelmesini sağlar. `#undef` deyimleri içinde makro değişikliği gerçekleştirilmez.  
  
 Bir kaynak programda, bir tanımlayıcının özel anlama sahip olduğu bir bölge oluşturmak için `#undef` yönergesi genellikle bir `#define` yönergesi ile eşleştirilir. Örneğin, kaynak programın belirli bir işlevi, programın geri kalanını etkilemeyen ortama özgü değerler tanımlamak için bildirim sabitleri kullanabilir. `#undef` yönergesi, kaynak programın koşullu derlemesini denetlemek için `#if` yönergesi ile de çalışır. Bkz: [#if, #elif, #else ve #endif yönergeleri](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) daha fazla bilgi için.  
  
 Aşağıdaki örnekte, `#undef` yönergesi sembolik bir sabitin ve bir makronun tanımlarını kaldırır. Yalnızca makronun tanımlayıcısının belirtildiğine dikkat edin.  
  
```  
#define WIDTH 80  
#define ADD( X, Y ) ((X) + (Y))  
.  
.  
.  
#undef WIDTH  
#undef ADD  
```  
  
 **Microsoft özel**  
  
 Makroların tanımlarını kaldırmak için komut satırında /U seçeneğini kullanın ve ardından tanımı kaldırılacak makro adlarını belirtin. Bu komutu gönderdikten etkisini için bir dizi eşdeğerdir `#undef` *makro adını* dosyasının başında deyimleri.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)