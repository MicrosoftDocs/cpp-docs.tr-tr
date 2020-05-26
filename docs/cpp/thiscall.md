---
title: __thiscall
ms.date: 05/22/2020
f1_keywords:
- __thiscall
- __thiscall_cpp
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
ms.openlocfilehash: b9edc2cd8caa5fd5458f6a53c5fdb1f8a5e69914
ms.sourcegitcommit: 5bb421fdf61d290cac93a03e16a6a80959accf6d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83854820"
---
# `__thiscall`

**Microsoft 'a özgü** **`__thiscall`** çağırma kuralı, x86 mimarisinde C++ sınıf üye işlevlerinde kullanılır. Bu, değişken bağımsız değişkenleri (işlevler) kullanmayan üye işlevleri tarafından kullanılan varsayılan çağırma kuralıdır `vararg` .

' In altında, **`__thiscall`** çağrılan yığını temizler, bu işlevler için imkansız olur `vararg` . Bağımsız değişkenler yığından sağdan sola gönderilir. **`this`** İşaretçi yığın üzerinde değil, kayıt ECX aracılığıyla geçirilir.

ARM, ARM64 ve x64 makinelerinde, **`__thiscall`** derleyici tarafından kabul edilir ve yok sayılır. Bunun nedeni, varsayılan olarak bir Register tabanlı çağırma kuralı kullandıklarından oluşur.

Kullanmanın bir nedeni **`__thiscall`** , üye işlevleri varsayılan olarak kullanılan sınıflardır **`__clrcall`** . Bu durumda, **`__thiscall`** bağımsız üye işlevlerini yerel koddan çağrılabilir hale getirmek için ' i kullanabilirsiniz.

İle derlerken [**`/clr:pure`**](../build/reference/clr-common-language-runtime-compilation.md) tüm işlevler ve işlev işaretçileri, aksi belirtilmediği **`__clrcall`** takdirde. **`/clr:pure`** Ve **`/clr:safe`** derleyici seçenekleri visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

`vararg`üye işlevleri **`__cdecl`** çağırma kuralını kullanır. Tüm işlev bağımsız değişkenleri yığında **`this`** en son yığına yerleştirilmiş şekilde yığına gönderilir.

Bu çağırma kuralı yalnızca C++ için geçerli olduğundan, C adı düzenleme düzenine sahip değildir.

Statik olmayan bir sınıf üye işlevini satır dışı tanımladığınızda, yalnızca bildirimde çağırma kuralı değiştiricisini belirtin. Satırı satır dışı tanımda tekrar belirtmeniz gerekmez. Derleyici, tanım noktasındaki bildirim sırasında belirtilen çağırma kuralını kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız değişkeni geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md)
