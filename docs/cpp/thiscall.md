---
title: __thiscall | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __thiscall
- __thiscall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9dccd9e80a23b1636bd869d406824c9997f4cdef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="thiscall"></a>__thiscall
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 `__thiscall` Çağırma üye işlevlerini kullanılır ve değişken bağımsız değişken kullanmayın C++ üye işlevleri tarafından kullanılan varsayılan çağırma. Altında `__thiscall`, aranan olanaksız yığını temizler `vararg` işlevleri. Bağımsız değişkenler kalan yığında sağdan sola, ile `this` kayıt ECX aracılığıyla ve yığında x86 değil, geçirilen işaretçi mimarisi.  
  
 Kullanmak için bir neden `__thiscall` olan üye işlevlerini kullanmak sınıflarda olduğu `__clrcall` varsayılan olarak. Bu durumda, kullanabileceğiniz `__thiscall` tek tek üye işlevleri yerel koddan aranabilir yapma.  
  
 İle derleme yapılırken [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md), tüm işlevleri ve işlev işaretçileri `__clrcall` aksi belirtilmediği sürece. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 Visual C++ 2005 önce sürümlerde çağırma thiscall açıkça bir programda çünkü belirlenemedi `thiscall` bir anahtar sözcük değildi.  
  
 `vararg` üye işlevlerini kullanmak `__cdecl` çağırma. Tüm işlev bağımsız değişkenleri, ile yığına `this` işaretçi yerleştirilen yığında son  
  
 Bu çağırma yalnızca C++ için geçerli olduğundan, hiçbir C adı decoration düzeni yoktur.  
  
 ARM üzerinde ve [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] makineler, `__thiscall` kabul edilir ve derleyici tarafından yoksayıldı.  
  
 Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)