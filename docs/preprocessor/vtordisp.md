---
description: Microsoft C++ ' da vtordisp hakkında daha fazla bilgi edinin pragma
title: vtordisp pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragma, vtordisp
- vtordisp pragma
no-loc:
- pragma
ms.openlocfilehash: f8956aa892aae0472001b007137e6f978d91500e
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713148"
---
# <a name="vtordisp-no-locpragma"></a>`vtordisp` pragma

Gizli `vtordisp` oluşturma/yok etme yer değiştirme üyesinin eklenmesini denetler. `vtordisp` pragma C++ özgüdür.

## <a name="syntax"></a>Syntax

> **`#pragma vtordisp(`**[ **`push,`** ] *n***`)`**\
> **`#pragma vtordisp(pop)`**\
> **`#pragma vtordisp()`**\
> **`#pragma vtordisp(`** [ **`push,`** ] { **`on`** | **`off`** } **`)`**

### <a name="parameters"></a>Parametreler

**`push`**\
`vtordisp`İç derleyici yığınında geçerli ayarı iter ve yeni `vtordisp` ayarı *n* olarak ayarlar.  *N* belirtilmezse, geçerli `vtordisp` ayar değiştirilmez.

**`pop`**\
İç derleyici yığınından en üstteki kaydı kaldırır ve `vtordisp` ayarı kaldırılan değere geri yükler.

*No*\
Ayar için yeni değeri belirtir `vtordisp` . Olası değerler,,, **`0`** **`1`** **`2`** **`/vd0`** **`/vd1`** ve **`/vd2`** derleyici seçeneklerine karşılık gelir. Daha fazla bilgi için bkz. [ `/vd` (oluşturma yerini devre dışı bırakma)](../build/reference/vd-disable-construction-displacements.md).

**`on`**\
İle eşdeğerdir `#pragma vtordisp(1)` .

**`off`**\
İle eşdeğerdir `#pragma vtordisp(0)` .

## <a name="remarks"></a>Açıklamalar

**`vtordisp`** pragma Yalnızca sanal tabanları kullanan kod için geçerlidir. Türetilmiş bir sınıf sanal bir temel sınıftan devraldığı sanal bir işlevi geçersiz kılıyorsa ve türetilmiş sınıf için bir Oluşturucu veya yıkıcı, sanal temel sınıfa yönelik bir işaretçi kullanarak bu işlevi çağırırsa, derleyici, `vtordisp` sanal tabanlara sahip olan sınıflara ek gizli alanlar getirebilir.

, **`vtordisp`** pragma Kendisini izleyen sınıfların yerleşimini etkiler. **`/vd0`**, **`/vd1`** Ve **`/vd2`** derleyici seçenekleri, tüm modüller için aynı davranışı belirtir. **`0`** **`off`** Gizli üyeleri belirtme veya gösterme `vtordisp` . **`vtordisp`** Yalnızca, sınıfın oluşturucuların ve yıkıcılarının işaretçi tarafından işaret edilen nesnedeki sanal işlevleri çağırmasını sağlamak için devre dışı bırakın **`this`** .

Ya da belirtildiğinde, **`1`** **`on`** Varsayılan olarak, `vtordisp` gerekli oldukları yerde gizli üyeleri etkinleştirilir.

Belirtme **`2`** , `vtordisp` sanal işlevleri olan tüm sanal tabanların gizli üyelerini mümkün bir şekilde sunar. `#pragma vtordisp(2)` kısmen oluşturulmuş bir nesne üzerinde doğru performansı sağlamak için gerekli olabilir **`dynamic_cast`** . Daha fazla bilgi için bkz. [Derleyici Uyarısı (düzey 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).

`#pragma vtordisp()`bağımsız değişken olmadan, `vtordisp` ayarı ilk ayarına geri yükler.

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
