---
title: vtordisp
ms.date: 10/18/2018
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
ms.openlocfilehash: 67c6c329bcee75012f6075334760925eca945501
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034384"
---
# <a name="vtordisp"></a>vtordisp

**C++ özgü**

Gizli vtordisp oluşturma/yıkma yer değiştirme üyesinin eklenmesini denetler.

## <a name="syntax"></a>Sözdizimi

```cpp
#pragma vtordisp([push,] n)
#pragma vtordisp(pop)
#pragma vtordisp()
#pragma vtordisp([push,] {on | off})
```

### <a name="parameters"></a>Parametreler

*push*<br/>
İç derleyici yığınındaki geçerli vtordisp ayarını gönderir ve yeni vtordisp ayarını ayarlar *n*.  Varsa *n* belirtilmezse, geçerli vtordisp ayarı değiştirilmez.

*POP*<br/>
İç derleyici yığınından en üst kaydı kaldırır ve vtordisp ayarını kaldırılan değere geri yükler.

*n*<br/>
vtordisp ayarı için yeni değeri belirtir. Olası değerler: 0, 1 veya 2, karşılık gelen `/vd0`, `/vd1`, ve `/vd2` derleyici seçenekleri. Daha fazla bilgi için [/vd (oluşturma yer değiştirmelerini devre dışı bırak)](../build/reference/vd-disable-construction-displacements.md).

*on*<br/>
Eşdeğer `#pragma vtordisp(1)`.

*kapalı*<br/>
Eşdeğer `#pragma vtordisp(0)`.

## <a name="remarks"></a>Açıklamalar

**Vtordisp** pragması, yalnızca sanal temeller kullanan koda uygulanabilir. Türetilmiş bir sınıf sanal temel sınıftan devraldığı sanal bir işlev geçersiz kılar ve bir oluşturucu veya yıkıcı için türetilmiş bir sınıf sanal temel sınıfın işaretçisi kullanarak bu işlevi çağırırsa, derleyici ek gizli yapabilecek**vtordisp** sanal temellere sahip sınıflara alanlarına.

**Vtordisp** pragması, onu izleyen sınıfların düzenini etkiler. `/vd0`, `/vd1`, Ve `/vd2` seçenekleri, tam modüller için aynı davranışı belirtin. 0 belirtme veya *kapalı* gizli bastırır **vtordisp** üyeleri. Devre dışı **vtordisp** işaret ettiği nesne üzerinde işlevler sınıfın oluşturucularının ve yıkıcılarının sanal çağıran olasılığı varsa yalnızca **bu** işaretçi.

1 belirtme veya *üzerinde*, varsayılan olarak etkinleştirir gizli **vtordisp** gerekli nerede üyeleri.

2 sağlayan gizli belirtme **vtordisp** üyeleri sanal işlevleri olan tüm sanal temeller için.  `vtordisp(2)` doğru performansını sağlamak gerekli olabilir **dynamic_cast** üzerinde oluşturulmuş bir nesne. Daha fazla bilgi için [Derleyici Uyarısı (düzey 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).

`#pragma vtordisp()`, bağımsız değişken olmadan, vtordisp ayarını başlangıç ayarına geri yükler.

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

**END C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)