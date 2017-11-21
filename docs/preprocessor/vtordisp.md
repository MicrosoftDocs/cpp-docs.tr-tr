---
title: vtordisp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b9341221ecafc6204a9f126ea50eb22d54ffec35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vtordisp"></a>vtordisp
**C++ özel**  
  
 Gizli vtordisp oluşturma/yıkma yer değiştirme üyesinin eklenmesini denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
#pragma vtordisp([push,] n)  
#pragma vtordisp(pop)  
#pragma vtordisp()  
#pragma vtordisp([push,] {on | off})  
```  
  
#### <a name="parameters"></a>Parametreler  
 `push`  
 İç derleyici yığınındaki geçerli vtordisp ayarını gönderir ve yeni vtordisp ayarını `n` olarak ayarlar.  `n` belirtilmezse, geçerli vtordisp ayarı değiştirilmez.  
  
 `pop`  
 İç derleyici yığınından en üst kaydı kaldırır ve vtordisp ayarını kaldırılan değere geri yükler.  
  
 `n`  
 vtordisp ayarı için yeni değeri belirtir. Olası değerler /vd0, /vd1 ve /vd2 derleyici seçeneklerine karşılık gelen 0, 1 veya 2'dir. Daha fazla bilgi için bkz: [/VD (yapı yer devre dışı bırak) değiştirmelerini](../build/reference/vd-disable-construction-displacements.md).  
  
 `on`  
 Eşdeğer `#pragma vtordisp(1)`.  
  
 `off`  
 Eşdeğer `#pragma vtordisp(0)`.  
  
## <a name="remarks"></a>Açıklamalar  
 `vtordisp` pragması, yalnızca sanal temeller kullanan koda uygulanabilir. Türetilmiş bir sınıf sanal temel sınıftan devraldığı sanal bir işlevi geçersiz kılarsa ve türetilmiş sınıfın oluşturucusu veya yıkıcısı sanal temel sınıfın işaretçisini kullanarak bu işlevi çağırırsa, derleyici sanal temelleri olan sınırlara ek gizli `vtordisp` alanları sunabilir.  
  
 `vtordisp` pragması, onu izleyen sınıfların düzenini etkiler. /vd0, /vd1 ve /vd2 seçenekleri, tam modüller için aynı davranışı belirtir. `0` veya `off` belirtilirse, gizli `vtordisp` üyeleri engellenir. `vtordisp` öğesini yalnızca sınıfın oluşturucularının ve yıkıcılarının `this` işaretçisi tarafından işaret edilen nesne üzerindeki sanal işlevleri çağırma olasılığı yoksa kapatın.  
  
 Varsayılan olan `1` veya `on` değerlerinin belirtilmesi, gizli `vtordisp` üyelerini gerektiklerinde etkinleştirir.  
  
 Belirtme `2` gizli etkinleştirir `vtordisp` sanal işlevlere sahip tüm sanal temelleri için üyeleri.  `vtordisp(2)`doğru performansını sağlamak gerekli olabilir `dynamic_cast` kısmen oluşturulan bir nesne üzerinde. Daha fazla bilgi için bkz: [Derleyici Uyarısı (düzey 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).  
  
 Bağımsız değişkeni olmayan `#pragma vtordisp()`, vtordisp ayarını başlangıç ayarına geri yükler.  
  
```  
#pragma vtordisp(push, 2)  
class GetReal : virtual public VBase { ... };  
#pragma vtordisp(pop)  
```  
  
 **Son C++ özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)