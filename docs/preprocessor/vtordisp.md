---
title: vtordisp pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
ms.openlocfilehash: 3c676ab2bfee1b6cf3caff3ab456a4f23f2744c3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216486"
---
# <a name="vtordisp-pragma"></a>vtordisp pragması

**C++Belirli**

Gizli `vtordisp` oluşturma/yok etme yer değiştirme üyesinin eklenmesini denetler.

## <a name="syntax"></a>Sözdizimi

> **#pragma vtordisp (** [ **push,** ] *n* **)** \
> **vtordisp (pop) #pragma**\
> **#pragma vtordisp ()** \
> **#pragma vtordisp (** [ **push,** ] { **on** | **off** } **)**

### <a name="parameters"></a>Parametreler

**hareketle**\
İç derleyici yığınında `vtordisp` geçerli ayarı iter ve yeni `vtordisp` ayarı *n*olarak ayarlar.  *N* belirtilmezse, geçerli `vtordisp` ayar değiştirilmez.

**cağımız**\
İç derleyici yığınından en üstteki kaydı kaldırır ve `vtordisp` ayarı kaldırılan değere geri yükler.

*No*\
`vtordisp` Ayar için yeni değeri belirtir. Olası değerler `/vd0`, `/vd1`, ve `/vd2` derleyici seçeneklerine karşılık gelen 0, 1 veya 2 ' dir. Daha fazla bilgi için bkz. [/vd (yapı yerini devre dışı bırakma)](../build/reference/vd-disable-construction-displacements.md).

**dayanır**\
İle `#pragma vtordisp(1)`eşdeğerdir.

**dışına**\
İle `#pragma vtordisp(0)`eşdeğerdir.

## <a name="remarks"></a>Açıklamalar

**Vtordisp** pragması yalnızca sanal tabanların kullanıldığı kodla uygulanabilir. Türetilmiş bir sınıf sanal temel sınıftan devraldığı sanal bir işlevi geçersiz kılarsa ve türetilmiş sınıfın oluşturucusu veya yıkıcısı sanal temel sınıfın işaretçisini kullanarak bu işlevi çağırırsa, derleyici sanal temelleri olan sınırlara ek gizli `vtordisp` alanları sunabilir.

**Vtordisp** pragma, kendisini izleyen sınıfların yerleşimini etkiler. `/vd0`, Veseçenekleri`/vd2` , tüm modüller için aynı davranışı belirtir. `/vd1` 0 veya **off** belirtildiğinde gizli `vtordisp` Üyeler bastırır. Yalnızca sınıfın oluşturucuların ve yıkıcılarının `this` işaretçi tarafından işaret edilen nesne üzerinde sanal işlevleri çağırması olasılığı yoksa **vtordisp** 'ı kapatın.

Varsayılan olarak 1 veya **üzerinde**belirtildiğinde, gerekli oldukları gizli `vtordisp` Üyeler etkinleştirilir.

2 belirtmek, sanal işlevler `vtordisp` ile tüm sanal tabanların gizli üyelerini mümkün bir şekilde sunar.  `#pragma vtordisp(2)`kısmen oluşturulmuş bir nesne üzerinde **dynamic_cast** performansının doğru olmasını sağlamak için gerekli olabilir. Daha fazla bilgi için bkz. [Derleyici Uyarısı (düzey 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).

`#pragma vtordisp()`bağımsız değişken olmadan, `vtordisp` ayarı ilk ayarına geri yükler.

```cpp
#pragma vtordisp(push, 2)
class GetReal : virtual public VBase { ... };
#pragma vtordisp(pop)
```

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
