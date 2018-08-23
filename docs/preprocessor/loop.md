---
title: döngü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- loop_CPP
- vc-pragma.loop
dev_langs:
- C++
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e4881dfdcb92e778501982482abc13cc91836b0
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465414"
---
# <a name="loop"></a>loop
Döngü kodunun otomatik paralel hale getirici tarafından nasıl kullanılacağını denetler ve/veya bir döngünün otomatik vektör hale getirici tarafından dikkate alınmamasını sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma loop( hint_parallel(n) )  
```  
  
```  
#pragma loop( no_vector )  
```  
  
```  
#pragma loop( ivdep )  
```  
  
### <a name="parameters"></a>Parametreler  
*hint_parallel(n)*  
Arasında Bu döngü paralelleştirildi derleyici için ipuçları *n* iş parçacıkları, burada *n* bir pozitif tamsayı değişmez değeri ya da sıfırdır. Varsa *n* sıfırsa, çalışma zamanında iş parçacığı sayısı kullanılır. Bu komut değil derleyici için yol gösteren bir ipucudur ve döngünün paralel hale getirileceğinin garantisi yoktur. Döngüde veri bağımlılıkları veya yapısal sorunlar varsa (örneğin, döngü, döngü gövdesinin dışında kullanılan bir skalara depoluyor), döngü paralel hale getirilmez.  
  
Derleyici bu seçeneği yoksayar [/Qpar](../build/reference/qpar-auto-parallelizer.md) derleyici anahtarı belirtilmezse.  
  
*no_vector*  
Varsayılan olarak, otomatik vektör hale getirici açıktır ve ondan yararlanıyor olarak değerlendirdiği tüm döngüleri vektör hale getirmeye çalışır. Kendisini takip eden döngü için, otomatik vektör hale getiriciyi devre dışı bırakmak üzere bu pragmayı belirtin.  
  
*ivdep*  
Bu döngü için vektör bağımlılıklarını yoksayma konusunda derleyici için ipuçları. Bu ile birlikte kullanarak *hint_parallel*.  
  
## <a name="remarks"></a>Açıklamalar  
 
Kullanılacak **döngü** pragması, hemen öncesine yerleştirin — değil; bir döngü tanımının. Pragma, onu takip eden döngü kapsamı için etkili olur. Bir döngüye herhangi bir sırada birden fazla pragma uygulayabilirsiniz, ancak her birini ayrı bir pragma deyimi içinde belirtmelisiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Otomatik Paralelleştirme ve otomatik Vektörleştirme](../parallel/auto-parallelization-and-auto-vectorization.md)   
[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)