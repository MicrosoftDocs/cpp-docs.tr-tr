---
description: 'Şu konuda daha fazla bilgi edinin: vtordisp Pragma'
title: vtordisp pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
ms.openlocfilehash: 2cbb8b09584224a454dfe23d5dfd4500f09a1d9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149649"
---
# <a name="vtordisp-pragma"></a>vtordisp pragması

**C++ özel**

Gizli `vtordisp` oluşturma/yok etme yer değiştirme üyesinin eklenmesini denetler.

## <a name="syntax"></a>Syntax

> **#pragma vtordisp (** [ **push,** ] *n* **)**\
> **vtordisp (pop) #pragma**\
> **#pragma vtordisp ()**\
> **#pragma vtordisp (** [ **push,** ] { **on**  |  **off** } **)**

### <a name="parameters"></a>Parametreler

**hareketle**\
`vtordisp`İç derleyici yığınında geçerli ayarı iter ve yeni `vtordisp` ayarı *n* olarak ayarlar.  *N* belirtilmezse, geçerli `vtordisp` ayar değiştirilmez.

**cağımız**\
İç derleyici yığınından en üstteki kaydı kaldırır ve `vtordisp` ayarı kaldırılan değere geri yükler.

*No*\
Ayar için yeni değeri belirtir `vtordisp` . Olası değerler `/vd0` ,, `/vd1` ve derleyici seçeneklerine karşılık gelen 0, 1 veya 2 ' dir `/vd2` . Daha fazla bilgi için bkz. [/vd (yapı yerini devre dışı bırakma)](../build/reference/vd-disable-construction-displacements.md).

**dayanır**\
İle eşdeğerdir `#pragma vtordisp(1)` .

**dışına**\
İle eşdeğerdir `#pragma vtordisp(0)` .

## <a name="remarks"></a>Açıklamalar

**Vtordisp** pragması yalnızca sanal tabanların kullanıldığı kodla uygulanabilir. Türetilmiş bir sınıf sanal temel sınıftan devraldığı sanal bir işlevi geçersiz kılarsa ve türetilmiş sınıfın oluşturucusu veya yıkıcısı sanal temel sınıfın işaretçisini kullanarak bu işlevi çağırırsa, derleyici sanal temelleri olan sınırlara ek gizli `vtordisp` alanları sunabilir.

**Vtordisp** pragma, kendisini izleyen sınıfların yerleşimini etkiler. `/vd0`, `/vd1` Ve seçenekleri, `/vd2` tüm modüller için aynı davranışı belirtir. 0 veya **off** belirtildiğinde gizli Üyeler bastırır `vtordisp` . Yalnızca sınıfın oluşturucuların ve yıkıcılarının işaretçi tarafından işaret edilen nesne üzerinde sanal işlevleri çağırması olasılığı yoksa **vtordisp** 'ı kapatın **`this`** .

Varsayılan olarak 1 veya **üzerinde** belirtildiğinde, `vtordisp` gerekli oldukları gizli Üyeler etkinleştirilir.

2 belirtmek, `vtordisp` sanal işlevler ile tüm sanal tabanların gizli üyelerini mümkün bir şekilde sunar.  `#pragma vtordisp(2)` kısmen oluşturulmuş bir nesne üzerinde doğru performansı sağlamak için gerekli olabilir **`dynamic_cast`** . Daha fazla bilgi için bkz. [Derleyici Uyarısı (düzey 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).

`#pragma vtordisp()`bağımsız değişken olmadan, `vtordisp` ayarı ilk ayarına geri yükler.

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
