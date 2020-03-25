---
title: __thiscall
ms.date: 11/04/2016
f1_keywords:
- __thiscall
- __thiscall_cpp
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
ms.openlocfilehash: 8772159dca71bb7605af5e5919425065423d503d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188161"
---
# <a name="__thiscall"></a>__thiscall

**Microsoft 'a özgü**

**__Thiscall** çağırma kuralı, üye işlevlerinde kullanılır ve değişken bağımsız değişkenleri kullanmayan üye işlevleri tarafından C++ kullanılan varsayılan çağırma kuralıdır. **__Thiscall**altında, çağrılan yığını temizler ve bu, `vararg` işlevleri için imkansızdır. Bağımsız değişkenler, yığın üzerinde değil, x86 mimarisinde, **Bu** işaretçinin yığın üzerinde değil, kayıt ecx aracılığıyla geçirilme ile sağdan sola gönderilir.

**__Thiscall** kullanmanın bir nedeni, üye işlevleri varsayılan olarak `__clrcall` kullanan sınıflarlardır. Bu durumda, bağımsız üye işlevlerini yerel koddan çağrılabilir hale getirmek için **__thiscall** kullanabilirsiniz.

[/Clr: Pure](../build/reference/clr-common-language-runtime-compilation.md)ile derlerken, aksi belirtilmediği takdirde tüm işlevler ve işlev işaretçileri `__clrcall`. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Visual Studio 2005 ' den önceki sürümlerde, **__thiscall** bir anahtar sözcük olmadığından **__thiscall** çağırma kuralı bir programda açıkça belirtilemez.

`vararg` üye işlevleri **__cdecl** çağırma kuralını kullanır. **Bu** işaretçinin sonunda yığına yerleştirilmesi ile tüm işlev bağımsız değişkenleri yığına gönderilir

Bu çağırma kuralı yalnızca için C++geçerli olduğundan, C ad düzenleme düzeni yoktur.

ARM ve x64 makinelerde **__thiscall** , derleyici tarafından kabul edilir ve yok sayılır.

Statik olmayan sınıf işlevleri için, işlev satır dışı olarak tanımlandıysa çağırma kuralı değiştiricinin satır dışı tanımda belirtilmesi gerekmez. Diğer bir deyişle, statik olmayan üye sınıfı yöntemler için tanım noktasında bildirim sırasında belirtilen çağırma kuralı kabul edilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları](../cpp/argument-passing-and-naming-conventions.md)
